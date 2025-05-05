<script>
  import { onMount } from 'svelte';
  import { initializeApp } from 'firebase/app';
  import {
    getStorage,
    ref,
    uploadBytesResumable,
    getDownloadURL,
    listAll,
  } from 'firebase/storage';

  const firebaseConfig = {
    apiKey: "AIzaSyASEzzy6b5Uy_8iveg-I4f6kAv05ujRcOk",
    authDomain: "tsaopaofenghsiung2025.firebaseapp.com",
    databaseURL: "https://tsaopaofenghsiung2025-default-rtdb.firebaseio.com",
    projectId: "tsaopaofenghsiung2025",
    storageBucket: "tsaopaofenghsiung2025.firebasestorage.app",
    messagingSenderId: "467198654620",
    appId: "1:467198654620:web:20cfc39ad125c698cb9559",
    measurementId: "G-3ND8H6KNXP"
  };

  const app = initializeApp(firebaseConfig);
  const storage = getStorage(app);

  let fileInput;
  let videoUrl = '';
  let fileName = '';
  let fileList = [];
  let uploadStatus = '';
  let uploadProgress = 0;

  onMount(() => {
    listAllFiles();
  });

  function handleFileChange(event) {
    const file = event.target.files[0];
    if (file) {
      fileName = file.name;
      uploadVideoToFirebase(file);
    }
  }

  function uploadVideoToFirebase(file) {
    const storageRef = ref(storage, 'videos/' + file.name);
    const uploadTask = uploadBytesResumable(storageRef, file);

    uploadStatus = '上傳中...';
    uploadProgress = 0;

    uploadTask.on(
      'state_changed',
      (snapshot) => {
        uploadProgress = Math.round((snapshot.bytesTransferred / snapshot.totalBytes) * 100);
      },
      (error) => {
        console.error('Upload error:', error);
        uploadStatus = '❌ 上傳失敗：' + error.message;
      },
      async () => {
        uploadStatus = '✅ 上傳成功';
        uploadProgress = 100;
        await listAllFiles();
      }
    );
  }

  async function listAllFiles() {
    const listRef = ref(storage, 'videos/');
    try {
      const res = await listAll(listRef);
      fileList = await Promise.all(
        res.items.map(async (itemRef) => {
          const url = await getDownloadURL(itemRef);
          return { name: itemRef.name, url };
        })
      );
    } catch (error) {
      console.error('Error listing files:', error);
    }
  }

  function playVideo(url, name) {
    videoUrl = url;
    fileName = name;
  }
</script>

<h1>動畫新番片頭曲片尾曲</h1>

<input type="file" accept="video/*" bind:this={fileInput} on:change={handleFileChange} />

<!-- 上傳進度狀態 -->
{#if uploadStatus}
  <p><strong>{uploadStatus}</strong></p>
{/if}
{#if uploadProgress > 0 && uploadProgress < 100}
  <progress value={uploadProgress} max="100">{uploadProgress}%</progress>
  <span>{uploadProgress}%</span>
{/if}

<!-- 影片播放器 -->
{#if videoUrl}
  <p><strong>正在播放：</strong> {fileName}</p>
  <video src={videoUrl} controls width="333"></video>
{/if}

<!-- 已上傳影片列表 -->
<h2>Uploaded Videos:</h2>
<ul>
  {#each fileList as file}
    <li>
      <a href="javascript:void(0)" on:click={() => playVideo(file.url, file.name)}>
        {file.name}
      </a>
    </li>
  {/each}
</ul>
