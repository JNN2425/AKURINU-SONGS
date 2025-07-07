# AKURINU-SONGS
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AKURINU SONGS</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      background: linear-gradient(to right, #fef08a, #1e3a8a);
      color: #000;
    }
    .hidden { display: none; }
  </style>
</head>
<body class="px-4">

  <!-- Banner -->
  <div class="text-center bg-yellow-400 text-black py-3 text-2xl font-bold">
    The Home Of Spiritual Songs
  </div>

  <!-- Navbar -->
  <nav class="flex flex-wrap justify-between items-center p-4 bg-blue-900 text-white">
    <div class="text-2xl font-bold text-yellow-300">AKURINU SONGS</div>
    <ul class="flex flex-wrap space-x-6 mt-2 sm:mt-0">
      <li><button onclick="showSection('home')" class="hover:underline">Home</button></li>
      <li><button onclick="showSection('about')" class="hover:underline">About</button></li>
      <li><button onclick="showSection('login')" class="hover:underline">Login</button></li>
      <li><button onclick="showSection('upload')" class="hover:underline">Upload</button></li>
    </ul>
  </nav>

  <!-- Sections -->
  <section id="about" class="p-6 hidden">
    <h2 class="text-2xl font-bold mb-2">About AKURINU SONGS</h2>
    <p class="bg-white p-4 rounded shadow-md text-gray-800">
      A home for Akurinu songs, sharing spiritual messages through praise and worship music, from the old to the new generations.
    </p>
  </section>

  <section id="login" class="p-6 hidden">
    <h2 class="text-2xl font-bold mb-2">Login</h2>
    <form onsubmit="handleLogin(event)" class="bg-white p-4 rounded shadow-md space-y-4 max-w-md mx-auto">
      <input type="text" placeholder="Your Name" class="w-full p-2 border rounded text-black" required />
      <input type="tel" placeholder="Phone Number" class="w-full p-2 border rounded text-black" required />
      <button type="submit" class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700">Log In</button>
    </form>
  </section>

  <section id="upload" class="p-6 hidden">
    <h2 class="text-xl font-semibold mb-4">Upload Video</h2>
    <form class="bg-white p-4 rounded shadow-md space-y-4 max-w-lg mx-auto">
      <input type="file" class="w-full p-2 border rounded text-black" />
      <select class="w-full p-2 border rounded text-black">
        <option value="">Select Category</option>
        <option value="israel">Akurinu Israel</option>
        <option value="kigooco">Kigooco</option>
      </select>
      <button type="submit" class="bg-green-600 text-white px-4 py-2 rounded hover:bg-green-700">Upload</button>
    </form>
  </section>

  <!-- Home Section -->
  <section id="home" class="p-6">
    <div class="mb-6">
      <input
        type="text"
        id="searchInput"
        onkeyup="searchSongs()"
        placeholder="Search by song or artist..."
        class="w-full max-w-lg p-2 mx-auto block border rounded text-black shadow"
      />
    </div>

    <div class="flex flex-col lg:flex-row gap-6">
      <!-- Main Video Player -->
      <div class="flex-1">
        <div id="mainVideoContainer" class="bg-white p-4 rounded shadow relative">
          <h3 id="mainVideoTitle" class="text-lg font-semibold text-blue-800 mb-2">Click a video to play</h3>
          <video id="mainVideo" class="w-full rounded" controls>
            <source id="mainVideoSource" src="" type="video/mp4" />
          </video>
        </div>
      </div>

      <!-- Related Videos -->
      <div class="w-full lg:w-1/3 space-y-4" id="relatedVideos">
        <!-- Template Card -->
        <div class="song relative bg-white p-3 rounded shadow flex gap-3 cursor-pointer" 
             data-title="Nigukwagira" 
             data-artist="Loise Mwangi" 
             data-src="loise-mwangi--nigukwagira.mp4">
          <video class="w-24 h-16 rounded object-cover" muted>
            <source src="loise-mwangi--nigukwagira.mp4" type="video/mp4" />
          </video>
          <div class="flex-1">
            <h4 class="font-semibold text-blue-800 text-sm">Nigukwagira</h4>
            <p class="text-gray-600 text-xs">Loise Mwangi</p>
          </div>

          <!-- 3-Dot Menu -->
          <div class="relative">
            <button onclick="toggleMenu(this)" class="text-gray-700 text-xl font-bold px-2">⋮</button>
            <div class="menu hidden absolute right-0 mt-1 bg-white border rounded shadow-md z-50 text-sm">
              <a href="loise-mwangi--nigukwagira.mp4" download class="block px-4 py-2 hover:bg-gray-100">Download</a>
              <button onclick="shareVideo('loise-mwangi--nigukwagira.mp4')" class="block w-full text-left px-4 py-2 hover:bg-gray-100">Share</button>
              <button class="block w-full text-left px-4 py-2 hover:bg-gray-100">👍 Like</button>
              <textarea class="block w-full p-2 border-t text-xs" placeholder="Comment..."></textarea>
            </div>
          </div>
        </div>


        <div class="song relative bg-white p-3 rounded shadow flex gap-3 cursor-pointer" 
             data-title="muhoreria-makumbi" 
             data-artist="Martin Janet" 
             data-src="muhoreria-makumbi-new-official-video---martin-janet-hsc.mp4">
          <video class="w-24 h-16 rounded object-cover" muted>
            <source src="muhoreria-makumbi-new-official-video---martin-janet-hsc.mp4" type="video/mp4" />
          </video>
          <div class="flex-1">
            <h4 class="font-semibold text-blue-800 text-sm">muhoreria-makumbi</h4>
            <p class="text-gray-600 text-xs">Martin Janet</p>
          </div>
          <div class="relative">
            <button onclick="toggleMenu(this)" class="text-gray-700 text-xl font-bold px-2">⋮</button>
            <div class="menu hidden absolute right-0 mt-1 bg-white border rounded shadow-md z-50 text-sm">
              <a href="muhoreria-makumbi-new-official-video---martin-janet-hsc.mp4" download class="block px-4 py-2 hover:bg-gray-100">Download</a>
              <button onclick="shareVideo('muhoreria-makumbi-new-official-video---martin-janet-hsc.mp4')" class="block w-full text-left px-4 py-2 hover:bg-gray-100">Share</button>
              <button class="block w-full text-left px-4 py-2 hover:bg-gray-100">👍 Like</button>
              <textarea class="block w-full p-2 border-t text-xs" placeholder="Comment..."></textarea>
            </div>
          </div>
        </div>

        <div class="song relative bg-white p-3 rounded shadow flex gap-3 cursor-pointer" 
             data-title="ndungiringithanika" 
             data-artist="Daudi Wene" 
             data-src="ndungiringithanika-by-daudi-wene--video-4k--mutheekiengei8690-inoorotvkenya-dadasarah5360.mp4">
          <video class="w-24 h-16 rounded object-cover" muted>
            <source src="ndungiringithanika-by-daudi-wene--video-4k--mutheekiengei8690-inoorotvkenya-dadasarah5360.mp4" type="video/mp4" />
          </video>
          <div class="flex-1">
            <h4 class="font-semibold text-blue-800 text-sm">ndungiringithanika</h4>
            <p class="text-gray-600 text-xs">Daudi Wene</p>
          </div>
          <div class="relative">
            <button onclick="toggleMenu(this)" class="text-gray-700 text-xl font-bold px-2">⋮</button>
            <div class="menu hidden absolute right-0 mt-1 bg-white border rounded shadow-md z-50 text-sm">
              <a href="ndungiringithanika-by-daudi-wene--video-4k--mutheekiengei8690-inoorotvkenya-dadasarah5360.mp4" download class="block px-4 py-2 hover:bg-gray-100">Download</a>
              <button onclick="shareVideo('ndungiringithanika-by-daudi-wene--video-4k.mp4')" class="block w-full text-left px-4 py-2 hover:bg-gray-100">Share</button>
              <button class="block w-full text-left px-4 py-2 hover:bg-gray-100">👍 Like</button>
              <textarea class="block w-full p-2 border-t text-xs" placeholder="Comment..."></textarea>
            </div>
          </div>
        </div>
        
        
        <div class="song relative bg-white p-3 rounded shadow flex gap-3 cursor-pointer" 
             data-title="karia-ini" 
             data-artist="Sam K" 
             data-src="karia-ini-by-sam-k.mp4">
          <video class="w-24 h-16 rounded object-cover" muted>
            <source src="karia-ini-by-sam-k.mp4" type="video/mp4" />
          </video>
          <div class="flex-1">
            <h4 class="font-semibold text-blue-800 text-sm">karia-ini</h4>
            <p class="text-gray-600 text-xs">Sam K</p>
          </div>
          <div class="relative">
            <button onclick="toggleMenu(this)" class="text-gray-700 text-xl font-bold px-2">⋮</button>
            <div class="menu hidden absolute right-0 mt-1 bg-white border rounded shadow-md z-50 text-sm">
              <a href="karia-ini-by-sam-k.mp4" download class="block px-4 py-2 hover:bg-gray-100">Download</a>
              <button onclick="shareVideo('karia-ini-by-sam-k.mp4')" class="block w-full text-left px-4 py-2 hover:bg-gray-100">Share</button>
              <button class="block w-full text-left px-4 py-2 hover:bg-gray-100">👍 Like</button>
              <textarea class="block w-full p-2 border-t text-xs" placeholder="Comment..."></textarea>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <footer class="text-center p-4 mt-10 bg-blue-900 text-white">
    &copy; 2025 AKURINU SONGS. All rights reserved.
  </footer>

  <!-- Scripts -->
  <script>
    function showSection(id) {
      document.querySelectorAll("section").forEach(s => s.classList.add("hidden"));
      document.getElementById(id).classList.remove("hidden");
    }

    function handleLogin(e) {
      e.preventDefault();
      alert("You are now logged in.");
      showSection("home");
    }

    function searchSongs() {
      const input = document.getElementById("searchInput").value.toLowerCase();
      const songs = document.querySelectorAll(".song");
      songs.forEach(song => {
        const title = song.dataset.title.toLowerCase();
        const artist = song.dataset.artist.toLowerCase();
        song.style.display = (title.includes(input) || artist.includes(input)) ? "flex" : "none";
      });
    }

    document.addEventListener("DOMContentLoaded", () => {
      const songs = document.querySelectorAll(".song");
      const mainVideo = document.getElementById("mainVideo");
      const mainVideoSource = document.getElementById("mainVideoSource");
      const mainVideoTitle = document.getElementById("mainVideoTitle");

      songs.forEach(song => {
        song.addEventListener("click", () => {
          const src = song.dataset.src;
          const title = song.dataset.title;
          const artist = song.dataset.artist;
          mainVideoSource.src = src;
          mainVideoTitle.textContent = `${title} by ${artist}`;
          mainVideo.load();
          mainVideo.play();
        });
      });
    });

    function toggleMenu(button) {
      const menu = button.nextElementSibling;
      document.querySelectorAll('.menu').forEach(m => {
        if (m !== menu) m.classList.add('hidden');
      });
      menu.classList.toggle('hidden');
    }

    function shareVideo(fileName) {
      const url = window.location.origin + '/' + fileName;
      navigator.clipboard.writeText(url).then(() => {
        alert('Link copied to clipboard: ' + url);
      });
    }
  </script>
</body>
</html>

