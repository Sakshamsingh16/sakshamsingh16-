<!-- Created by Amardeep kesharwani -->

<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1"/>
<meta name="author" content="sheikh toufeeq">
<title>Solo Music</title>
<link href="https://fonts.googleapis.com/css2?family=Open+Sans&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
<style>
/*
 app name: solo music,
 create by : sheikh toufeeq,
 date : 24-june-2020
*/
:root {
 --primary:#f33449;
 --white:#fff;
 --grey:#555;
}
*{
margin:0;
padding:0;
box-sizing:border-box;
}
body {
font-family: 'Open Sans', sans-serif;
font-size:1rem;
background:#000;
}
body.dark {
 --white:#000;
 --grey:#fff;
}
a,a:hover {
text-decoration:none;
}
img{
 max-width:100%;
}
p{
 color:var(--grey);
}
.sec {
 background:var(--white);
 width:100%;
 min-height:100vh;
 max-width:460px;
 margin:auto;
 animation:fadeIn 0.5s ease;
}
@keyframes fadeIn{
 0%{
  opacity:0;
 }
 100%{
 opacity:1;
 }
}
button{
 display:inline-block;
 outline:none;
 border:none;
 background:transparent;
}
.sec-1 {
 padding:20px;
 display:flex;
 justify-content: center;
 text-align: center;
 min-height:100vh;
}

.sec-1 svg {
 width:90%;
}
.sec-1 h1 {
  font-size:2.5rem;
}
.sec-1 h1 > span {
 color:#dd5790;
}
.sec-1 p {
 margin:10px 0 25px;
 color:#666;
 font-size:14px;
}
.sec-1 button {
 padding:12px 25px;
 background:#dd5790;
 color:#fff;
 border-radius:30px;
}
.hide {
 display:none;
}
.header {
 margin:0 10px;
 padding:8px 10px;
 display:flex;
 justify-content:space-between;
 border-bottom:2px solid #ccc;
 color:var(--grey);
}
.header button {
 color:var(--white);
 padding:6px 10px;
 font-size:14px;
 cursor:pointer;
 background:#dd5790;
 border-radius:30px;
}
.header button:hover {
 opacity:0.7;
}
body.dark .header button {
 background:#fff;
}
.music-list {
 padding-bottom:70px;
}
.music {
 padding:10px 10px;
 display:flex;
 align-items: center;
 width:100%;
 border-bottom:1px solid #dedede;
 cursor:pointer;
 color:var(--grey);
}
.music.active {
 color:var(--primary);
}
.list-thumbnail {
 height:60px;
 width:60px;
 border-radius:4px;
 overflow:hidden;
}
.list-content {
 flex:1;
 padding:0 15px;
}
.list-btn {
 width:50px;
 height:50px;
}
.list-btn > i {
 font-size:40px;
 color:var(--grey);
}
.music.active .list-btn > i {
 display:none;
}
.music .equalize {
 display:none;
}
.music.active .equalize {
 display:block;
}
.music-list .equalize span {
 display:inline-block;
 height:18px;
 width:3px;
 margin:1px;
 background:var(--primary);
 animation:equalize 1s linear infinite;
 transform-origin: bottom;
}
 .equalize.pause span {
  animation-play-state:paused!important;
}
.equalize span:nth-child(2) {
 animation-delay:.3s;
} 
.equalize span:nth-child(3) {
 animation-delay:.6s;
} 
@keyframes equalize {
 0%, 100%{
  transform:scaleY(1);
 }
 50%{
  transform:scaleY(0.3);
 }
}

.players {
 position:fixed;
 width:100%;
 max-width:460px;
 left:0;
 bottom:0;
 z-index:5;
 background:var(--white);
 color:#555;
 transition:300ms;
}
.players.active {
 height:100vh;
 top:0;
 text-align:center;
 padding:0 20px;
 overflow-y:scroll;
 animation:fadeIn 0.5s ease;
 animation-fill-mode:both;
}
.bottom {
 display:flex;
 align-items: center;
 height:70px;
 padding:5px 10px;
 border-top:1px solid #ccc;
}
.players.active .bottom {
 display:block;
 border-top:none;
 height:auto;
 padding:0;
 margin-bottom:25px;
}
.thumbnail {
 height:60px;
 width:60px;
 overflow:hidden;
 border-radius:4px;
}
.players.active .thumbnail{
 width:220px;
 margin:40px auto;
 height:220px;
 border-radius:50%;
 background:#000;
 box-shadow:0 4px 10px rgba(0,0,0,0.2);
}

.players.active .thumbnail.spin {
 box-shadow: none;
 animation:spin 4s linear infinite;
}
.players.active .thumbnail.spin:hover {
 animation-play-state:paused;
 transition:200ms;
}
.players.active .thumbnail.spin.pause{
 animation-play-state:paused;
}
@keyframes spin {
 to{
 transform:rotate(360deg); 
 }
}
.thumbnail img {
 object-fit:cover;
}

.content {
 flex:1;
 padding:0 15px;
 color:var(--grey);
}
.btn-group .material-icons {
 font-size:40px;
}
.btn-group button {
 color:var(--primary);
 cursor:pointer;
 height:60px;
 width:60px;
 border-radius:50%;
 cursor:pointer;
}
.playBtn {
 z-index:6;
}

.back-btn {
 position:absolute;
 top:10px;
 left:10px;
 height:40px;
 width:40px;
 cursor:pointer;
 border-radius:20px;
}
.dark-mode-btn {
position:absolute;
 top:10px;
 right:10px;
 height:40px;
 width:40px;
 cursor:pointer;
 border-radius:20px;
}

.back-btn:hover {
 background:rgba(255,0,0,0.2);
}
.back-btn .material-icons {
  font-size:40px;
}
body.dark .players .material-icons {
 color:#fff;
}
body.dark .players .material-icons.active  {
 color:var(--primary);
}
.prevBtn, .nextBtn, .tools , .progress-box, .back-btn, .dark-mode-btn {
 display:none;
}
.players.active .nextBtn,
.players.active .prevBtn,
.players.active .back-btn,
.players.active .dark-mode-btn {
 display:inline-block;
}
.players.active .progress-box,
.players.active .tools {
 display:flex;
}
.tools {
 width:100%;
 margin:30px 0;
 justify-content: space-evenly;
}
.tools .material-icons {
 font-size:30px;
 color:#555;
 cursor:pointer;
}
.tools .material-icons.active {
 color:var(--primary);
}
.players.active .playBtn {
 margin:0 25px;
 background:rgba(255,0,0,0.2);
 transition:0.3s;
}
.players.active .playBtn:hover {
 background:var(--primary);
 color:#fff;
}
.players.active .content h3{
 font-size:24px;
 color:var(--primary);
}
.progress-box {
 position:relative;
 margin-bottom:30px;
 display:none;
 width:100%;
 justify-content:space-between;
 font-size:14px;
}
.players.active .progress-box {
 display:flex;
}
.progress-bar {
    -webkit-appearance: none;
    appearance: none;
    position: absolute;
    z-index: 4;
    height: 5px;
    background: #ccc;
    width: 100%;
    border-radius: 30px;
    top:-10px;
}
.progress-bar::-webkit-slider-thumb {
    -webkit-appearance: none;
    height: 15px;
    width: 15px;
    border: 0;
    background: var(--primary);
    border-radius:50%;
    cursor: pointer;
} 
  
.volume-box {
 display:none;
}
.players.active .volume-box {
 transform:translateY(15px);
 display: none;
}
.players.active .volume-box.show {
 display: block;
}

.volume-box .progress-bar {
 position:relative;
 width:60%;
}
.volume-box > span {
 display:inline-block;
 height:30px;
 width:30px;
 margin:0 5px;
 cursor:pointer;
 transition:200ms;
}
.volume-box > span:hover {
 color:var(--primary);
}
#audio {
 display:none;
}
</style>
</head>
<body>
<section class="sec sec-1" id="sec-1">
  <div>
   <svg id="Capa_1" enable-background="new 0 0 512 512" height="350" viewBox="0 0 512 512" width="300" xmlns="http://www.w3.org/2000/svg"><g><g><g><path d="m473.088 266.293h-57.622v-36.494c0-87.93-71.536-159.466-159.466-159.466s-159.465 71.536-159.465 159.465v36.494h-57.623v-36.494c0-119.703 97.385-217.088 217.087-217.088 119.703 0 217.088 97.385 217.088 217.088v36.495z" fill="#407093"/></g></g><g><g><path d="m256 12.711c-5.024 0-10.006.186-14.946.524 112.757 7.705 202.143 101.885 202.143 216.563v36.494h29.892v-36.494c-.001-119.702-97.386-217.087-217.089-217.087z" fill="#2b4d66"/></g></g><g><circle cx="256" cy="411.198" fill="#dd5790" r="88.091"/></g><g><path d="m304.699 337.796c9.275 13.951 14.69 30.69 14.69 48.699 0 48.651-39.44 88.091-88.091 88.091-18.009 0-34.748-5.415-48.699-14.69 15.781 23.739 42.759 39.392 73.402 39.392 48.651 0 88.091-39.44 88.091-88.091-.001-30.642-15.654-57.619-39.393-73.401z" fill="#da387d"/></g><g><path d="m67.12 439.174h-34.12c-18.225 0-33-14.775-33-33v-125.547c0-18.225 14.775-33 33-33h34.12z" fill="#dae7ef"/></g><g><path d="m444.88 247.627h34.12c18.225 0 33 14.775 33 33v125.547c0 18.225-14.775 33-33 33h-34.12z" fill="#dae7ef"/></g><path d="m33 247.627c-2.349 0-4.639.25-6.849.716v148.55c0 8.284-6.716 15-15 15h-10.647c2.709 15.498 16.222 27.281 32.496 27.281h34.12v-191.547z" fill="#c1d5e4"/><path d="m484.291 248.054c.278 1.723.428 3.489.428 5.291v125.547c0 18.225-14.775 33-33 33h-6.839v27.281h34.12c18.225 0 33-14.775 33-33v-125.546c0-16.424-12-30.04-27.709-32.573z" fill="#c1d5e4"/><g><g><path d="m194.242 274.47c-4.263 0-7.717-3.455-7.717-7.717v-62.53c0-4.262 3.455-7.717 7.717-7.717s7.717 3.455 7.717 7.717v62.53c0 4.262-3.455 7.717-7.717 7.717z" fill="#dd5790"/></g><g><path d="m348.638 263.683c-4.263 0-7.717-3.455-7.717-7.717v-40.957c0-4.262 3.455-7.717 7.717-7.717 4.263 0 7.717 3.455 7.717 7.717v40.957c0 4.262-3.454 7.717-7.717 7.717z" fill="#dd5790"/></g><g><path d="m225.121 291.84c-4.263 0-7.717-3.455-7.717-7.717v-97.27c0-4.262 3.455-7.717 7.717-7.717 4.263 0 7.717 3.455 7.717 7.717v97.27c0 4.261-3.455 7.717-7.717 7.717z" fill="#dd5790"/></g><g><path d="m256 283.155c-4.263 0-7.717-3.455-7.717-7.717v-79.9c0-4.262 3.455-7.717 7.717-7.717 4.263 0 7.717 3.455 7.717 7.717v79.9c0 4.261-3.455 7.717-7.717 7.717z" fill="#dd5790"/></g><g><path d="m317.759 291.84c-4.263 0-7.717-3.455-7.717-7.717v-97.27c0-4.262 3.455-7.717 7.717-7.717s7.717 3.455 7.717 7.717v97.27c0 4.261-3.454 7.717-7.717 7.717z" fill="#dd5790"/></g><g><path d="m286.879 252.896c-4.263 0-7.717-3.455-7.717-7.717v-19.383c0-4.262 3.455-7.717 7.717-7.717s7.717 3.455 7.717 7.717v19.383c0 4.262-3.455 7.717-7.717 7.717z" fill="#dd5790"/></g><g><path d="m163.362 252.896c-4.263 0-7.717-3.455-7.717-7.717v-19.383c0-4.262 3.455-7.717 7.717-7.717s7.717 3.455 7.717 7.717v19.383c.001 4.262-3.454 7.717-7.717 7.717z" fill="#dd5790"/></g></g><g><path d="m296.022 406.002-60.913-35.168c-4-2.309-9 .577-9 5.196v70.336c0 4.619 5 7.506 9 5.196l60.913-35.168c4-2.309 4-8.083 0-10.392z" fill="#f6f9f9"/></g><g><path d="m104.487 469.944h-34.504c-8.783 0-15.903-7.12-15.903-15.903v-221.282c0-8.783 7.12-15.903 15.903-15.903h34.504c8.783 0 15.903 7.12 15.903 15.903v221.283c-.001 8.783-7.121 15.902-15.903 15.902z" fill="#dae7ef"/></g><g><path d="m407.513 216.856h34.504c8.783 0 15.903 7.12 15.903 15.903v221.283c0 8.783-7.12 15.903-15.903 15.903h-34.504c-8.783 0-15.903-7.12-15.903-15.903v-221.283c.001-8.783 7.121-15.903 15.903-15.903z" fill="#dae7ef"/></g><g fill="#c1d5e4"><path d="m104.487 216.856h-12.223v209.061c0 8.783-7.12 15.903-15.903 15.903h-22.281v12.222c0 8.783 7.12 15.903 15.903 15.903h34.504c8.783 0 15.903-7.12 15.903-15.903v-221.283c-.001-8.783-7.12-15.903-15.903-15.903z"/><path d="m442.017 216.856h-12.222v209.061c0 8.783-7.12 15.903-15.903 15.903h-22.281v12.222c0 8.783 7.12 15.903 15.903 15.903h34.504c8.783 0 15.903-7.12 15.903-15.903v-221.283c-.001-8.783-7.121-15.903-15.904-15.903z"/></g></g></svg>
<h1>Golu <span>Music</span></h1>
<p>Create by sheikh toufeeq</p>
<button onclick="showMusicList()">Let's Start</button>
  </div>
</section>
<section class="sec sec-2 hide" id="sec-2">

<header class="header">
<!-- <button onclick="filterCat('Sad')">Sad</button>
 <button onclick="filterCat('Love')">Love</button>
 <button onclick="filterCat('Dance')">Dance</button>
 <button onclick="filterCat('Romantic')">Romantic</button>
 <button onclick="filterAll()">All</button>
 -->
 <h3>All Songs</h3>
</header>

 <div class="music-list" id="music-list">
 </div>
 <audio src="" id="audio" ></audio>
 <div class="players" id="players">
   <button class="back-btn" onclick="showplayer()"><i class="material-icons" >expand_more</i></button>
   <button class="dark-mode-btn" onclick="darkMood()"><i class="material-icons" >invert_colors</i></button>
   
   <div class="bottom" >
     <div class="thumbnail" >
         <img id="thumbnail" src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQRdF1EyT4zeHHIcicA4wA8uMjxoGAblXsTIiXPhdTCzbG1YI18&usqp=CAU" alt="" >
     </div>
     <div class="content" onclick="showplayer()">
       <h3 id="name">Name</h3>
       <small id="category">Category</small>
     </div>
     
     <div class="volume-box">
     <span onclick="volumeDown()"><i class="material-icons">remove</i></span>
     
     <input type="range" class="progress-bar" id="volumeBar" step="1" value="80" min="0" max="100"
      oninput="audio.volume = this.value/100">
      
     <span onclick="volumeUp()"><i class="material-icons">add</i></span>
     </div>
     
     <div class="tools" >
       <button class="equaliser" onclick="equalizerBtn(event)">
       <i class="material-icons">equalizer</i>
       </button>
       <button class="repeat" onclick="repeat(event)">
         <i class="material-icons">repeat</i>
       </button>
       <button class="volume" onclick="volumeBox(event)">
         <i class="material-icons">volume_up</i>
       </button>  
       <button class="favorite" onclick="addFvt(event)">
         <i class="material-icons">favorite</i>
       </button>
     </div>
     <div class="progress-box" >
       <input type="range" class="progress-bar" id="progress" min="0" max="" value="0" onchange="changeProgressBar()"/>
         <div id="ctview" >00:00</div>
         <div id="ttview">00:00</div>
     </div>
     <div class="btn-group" >
       <button class="prevBtn" onclick="prevPlay()">
         <i class="material-icons">skip_previous</i>
       </button>
       <button class="playBtn"  onclick="playPause(event)">
        <i id="playBtn" class="material-icons">play_arrow</i>
       </button>
       <button class="nextBtn" onclick="nextPlay()">
         <i class="material-icons">skip_next</i>
       </button>
     </div>
   </div>
 </div>
</section>
<!-- script  -->
<script>
// amardeep kesharwani
 const playerWindow = document.getElementById("players");
 const audio = document.getElementById("audio");
 const name = document.getElementById("name");
 const category = document.getElementById("category");
 const thumbnail = document.getElementById("thumbnail");
 const playBtn = document.getElementById("playBtn");
 const progress = document.getElementById("progress");
 const ttview = document.getElementById("ttview");
 const tcview = document.getElementById("tcview");
 const volumeBar = document.getElementById("volumeBar");
 
 const musicList = document.getElementById("music-list");
 const body = document.querySelector("body");
 // variable 
 let musicData = [
 {
 id:1,
 category:"Dance",
 name:"Faded - Alan Walker",
 src:"https://2u039f-a.akamaihd.net/downloads/ringtones/files/mp3/alan-walker-faded-ringtone-30926.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQoGWmS7kOCnkLAvH9g0_fZMdKW0d-l6P-H3yZaDokzVPZ4Y4bY&usqp=CAU",
 },
 {
 id:2,
 category:"Love",
 name:"Chahun ya - Aashiqui-2",
 src:"https://2u039f-a.akamaihd.net/downloads/ringtones/files/mp3/chahun-main-ya-naa-3448.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQk-rT8uIudDAvN1p7qGBpyuLLF8DWwA_4ta7Oxtw5k6397rn2P&usqp=CAU",
 },
 {
 id:3,
 category:"Sad",
 name:"Dil ka lagana",
 src:"https://2u039f-a.akamaihd.net/downloads/ringtones/files/mp3/kya-rang-laya-dil-ka-lagana-raabta-lambiyaan-si-judaiyaan-arijit-singh-ring-29410.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQuZEhM4JWi0kLeHFQlnineERhaNlvCbjpwoHDTnemesNm5XtSh&usqp=CAU",
 },
 {
 id:4,
 category:"Love",
 name:"Tum hi ho",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/tujhe-zindagi-du-freemaza-1387.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQRdF1EyT4zeHHIcicA4wA8uMjxoGAblXsTIiXPhdTCzbG1YI18&usqp=CAU",
 },
 {
 id:5,
 category:"Love",
 name:"kaho na pyar hai",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/ringtone-kaho-naa-pyaar-hai-50104.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQ91A18HUFoYk2KmejbAnT_ULfxbYI5I-eJtqjsQmvPVghpxac7&usqp=CAU",
 },
 {
 id:6,
 category:"Love",
 name:"Love me like do",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/lovemelikeyoudonotification-9607.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSJhlenOe3XhPmFaVhs7k5LPnTdITSaNgwkJGulEoiZXMn8U5_V&usqp=CAU",
 },
 {
 id:7,
 category:"Dance",
 name:"Stereo Love",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/stereoloveringtone-5231.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSG0JnTUjKBjO-2Kg3cxd3hF5N-4pLe3F7fPGq0Z43D96mTqY0N&usqp=CAU",
 },
 {
 id:8,
 category:"Love",
 name:"Radhakrishn fluit",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/radhakrishnaringtone-43687.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTZgjJ5H3VZ78EkG88xYmNiOmONJnTUwtPRm82re6WOqfiEgMOF&usqp=CAU",
 },
 {
 id:9,
 category:"Love",
 name:"Radhakrishn Love",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/best-ringtone-krishn-70be80cb-1d27-4382-80d0-4972c8679083-45110.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcT-_7hrwqXewwE_ZOCmcf3aWwExxE1SI9HCTDai9qZPkwf7LkIu&usqp=CAU",
 },
 {
 id:10,
 category:"Sad",
 name:"Jab bna uska bna",
 src:"https://2u039f-a.akamaihd.net/downloads/ringtones/files/mp3/uska-17223.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSfJZeLuouw9kuPTZvxXsWvIJNVKWeJWGOHW_xEewWWXLg-85Dl&usqp=CAU",
 },
 {
 id:11,
 category:"Sad",
 name:"khamoshiya Aawaj hai",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/khamoshiyan-aavaj-hai-pagalworld-com-28786.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRq4Gx1TKbTydT1veGl6c2AFYpf4Wras6x-cRCKdX9MOXaZSIZZ&usqp=CAU",
 },
 {
 id:12,
 category:"Dance",
 name:"I am a Rider",
 src:"https://2u039f-a.akamaihd.net/downloads/ringtones/files/mp3/rider-mobile-ringtone-46241.mp3",
 image:"https://avatars.sololearn.com/d447897c-b803-4e6e-bd74-8ab8966ba711.jpg",
 papular:15,
 },
 {
 id:13,
 category:"Dance",
 name:"Otilia Bilioner",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/otiliabilioneraradioeditringtone-27801.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRb2Qec75WQvDv_lrJ1PHIqaWx8Ylyo7Gkpxu_ZbIEcy5yhY6on&usqp=CAU",
 },
 {
 id:14,
 category:"Love",
 name:"Tu meri Dost",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/tumeridosthainsongspkringtone-8802.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcR2X15hbWDrbxuMSJCR5-taAnulozr6FAcaoS0y-3Shjrf95X51&usqp=CAU",
 },
 {
 id:15,
 category:"Sad",
 name:"milne hai mujhe aayi",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/milne-hai-mujhse-aayi-aashiqui-2-ringtone-pagalworld-com-1454.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRyPB-mPN8VBVx98-GDHwiNfiTOsg-T4j4CUsylLfRSIyhZAd6K&usqp=CAU"
 },
 {
 id:16,
 category:"Romantic",
 name:"O Khuda - hero",
 src:"https://2u039f-a.akamaihd.net/downloads/ringtones/files/mp3/o-khuda-hero-ringtone-14026.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTVbAjmIEeDVpuIxdLKwF-e37K-4wx0EU51kIYUvV7XFTJ2P4Oj&usqp=CAU",
 },
 {
 id:17,
 category:"Dance",
 name:"Carryminati - UTuber",
 src:"https://2u039f-a.akamaihd.net/downloads/ringtones/files/mp3/carryminati-50296.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRMq9PEkWr1vaFG8e2rUyiQHeaUlaimA3JAqbOnZeU2SwilniD3&usqp=CAU",
 },
 {
 id:18,
 category:"Horror",
 name:"i am coming",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/witch-laugh-28505.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQpQhKCoX7BNDq3wUcsWEx-uJTmGVYjntpGQWIkpwymAnQKZQW3&usqp=CAU"
 },
 {
id:19,
category:"My Crush 😍😍😘😘",
name:"Befikra - Disha pathani",
src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/2befikrapagalworldinforingtone-21189.mp3",
image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRgBnbu64XmbZ9q27ZFpfuzzoFC0V3uJVXX9Q&usqp=CAU"
 },
 {
 id:20,
 category:"Romantic",
 name:"Aap mujhe achhe lgne",
 src:"https://loverays.com/ringtones/Aap_Mujhe_Achay_Lagne_Lage.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcROp4dF8PpIKNahtjyjhbpmNP8KBYFA7ZDhzILmwNonnFsVY_BK&usqp=CAU",
 },
 {
 id:21,
 category:"Romantic",
 name:"Saanson ko - zid",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/saanson-ko-zid-arijit-singh-ringtone-4555.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRqc_tcDOpYPHeqelLmzH9F8L-O2oLgTfi2g4sCORIDAIK0pPZA&usqp=CAU",
 },
{
id:22,
category:"Dance",
name:"English medium",
src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/tu-chij-lajawab-tera-koi-na-jawab-status-ringtone-sapna-choudhary-39997.mp3",
image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRmEd4bLIhrHXQj0dbB0w-5LUoZaPvpbdnC6Q&usqp=CAU"
},
 {
 id:23,
 category:"Love",
 name:"deewana Kar Raha - Raaz ",
 src:"https://d6cp9b00-a.akamaihd.net/downloads/ringtones/files/mp3/deewana-kar-raha-hai-5617.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSrqZ9q-RsTZO7cOgXA0IQe-IT-yclLI9lXUFoqDlIBKWqEnoHn&usqp=CAU",
 },
 {
 id:24,
 category:"Dance",
 name:"Let me love you",
 src:"https://2u039f-a.akamaihd.net/downloads/ringtones/files/mp3/letmeloveyoudjsnakeftjustinbieberdjjohalcomringtoneringtone-38476.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcS2ULdnCNnlxZvQNkduuTVHZjKK1yHOSFZzGZSB__hw6LMJ4XlM&usqp=CAU",
 },
 {
 id:25,
 category:"Sad",
 name:"Bhula Dena",
 src:"https://quz1yp-a.akamaihd.net/downloads/ringtones/files/mp3/bhula-dena-muskurahat-com-7597.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRhCfKXq4F7khZwqD4nsj68JHXLVNo5WUJSq3FgogLcuW5d5-aF&usqp=CAU",
 },
 {
 id:26,
 category:"Dance",
 name:"Sunny Sunny",
 src:"https://2u039f-a.akamaihd.net/downloads/ringtones/files/mp3/sunnysunny-vtaujyk4-2058.mp3",
 image:"https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRq1F69qRL2WPJ3j6fTPEyIrhB6W1rVr9t8gQ&usqp=CAU"
 },
 ]
let repeatMusic = false;
let index = 1;
let songs = musicData;

const elc = musicList.getElementsByClassName("equalize")[index-1];

const showMusicList = () => {
 document.querySelector(".sec-1").classList.add("hide");
 document.querySelector(".sec-2").classList.remove("hide");
}
const darkMood = () => {
 body.classList.toggle("dark");
}

const setActive = (i) => {
  setEqualizer()
  let a =  musicList.querySelector(".active");
  if(a !== null) {
   a.classList.remove("active");
  }
  const ele = document.getElementsByClassName("music")[i-1];
  ele.classList.add("active");
}

const setData = data => {
 name.textContent = data.name;
 category.textContent = data.category;
 thumbnail.src = data.image;
} 

const playMusic = async (i) => {
  if(i == 18 || i == 10 ) {
   body.classList.toggle("dark");
   setTimeout(() => body.classList.toggle("dark"),7000);
  }
  let data = musicData.find(m => m.id === i) || musicData[1];
  setActive(i)
  setData(data);
  playBtn.textContent = "pause";
  audio.src = data.src;
  await audio.load();
  audio.play();
}
 
 const playPause = e => {
    if(audio.paused) {
    playBtn.textContent = "pause";
    audio.play();
    setEqualizer()
   } else{
   playBtn.textContent = "play_arrow";
    audio.pause();
    setEqualizer(true)
   }
 }
 
 const showplayer = () => {
   playerWindow.classList.toggle("active");
 }
 const equalizerBtn = e => {
  e.target.classList.toggle("active");
  document.querySelector(".thumbnail").classList.toggle("spin");
 }
 const addFvt = e => {
  e.target.classList.toggle("active")
 }
 const repeat = e => {
  e.target.classList.toggle("active")
  repeatMusic = !repeatMusic;
  audio.loop = repeatMusic;
 }
 const volumeBox = e => {
  e.target.classList.toggle("active");
  document.querySelector(".volume-box").classList.toggle("show");
 }
 const nextPlay = () => {
  index++;
  if (index > musicData.length) {
   index = 1;
  }
  playMusic(index);
 }
 const prevPlay = () => {
  index--;
  if (index <= 0) {
  index = musicData.length;
  }
  playMusic(index);
 }
 // eventListners 
 audio.addEventListener("ended", () => {
  nextPlay();
 })
 audio.onloadeddata = () =>  {
 progress.max = audio.duration
 const ds = parseInt(audio.duration % 60)
 const dm = parseInt((audio.duration / 60) % 60)
 ttview.textContent = dm + ':' + ds;
 }
 audio.ontimeupdate =  () =>  { 
   progress.value = audio.currentTime 
 }
 audio.addEventListener('timeupdate', () => {
 //progress.value = audio.currentTime;
 var cs = parseInt(audio.currentTime % 60)
 var cm = parseInt((audio.currentTime / 60) % 60)
  ctview.textContent = cm + ':' + cs;
 }, false);
 
 const changeProgressBar = () => { 
   audio.currentTime = progress.value;
 }
 
/* volume control */
 const volumeDown = () => {
  volumeBar.value = Number(volumeBar.value) - 20
  audio.volume = volumeBar.value / 100
 }
 const volumeUp = () => {
  volumeBar.value = Number(volumeBar.value) + 20
  audio.volume = volumeBar.value / 100
 }
 

 const addList = (data) => {
  let div = document.createElement("div");
  div.classList.add('music');
  div.setAttribute("data-id", data.id);
  let html = `
   <div class="list-thumbnail" >
    <img src="${data.image}" alt="" >
   </div>
   <div class="list-content" >
   <h3>${data.name}</h3>
   <small>${data.category}</small>
   </div>
   <button class="list-btn" >
   <i class="material-icons">play_arrow</i>
    <div class="equalize">
    <span></span>
    <span></span>
    <span></span>
   </div>
   </button>`;
   div.innerHTML = html;
   musicList.append(div);
   div.addEventListener('click', () => {
    playMusic(data.id);
    playerWindow.classList.add("active");
    index = data.id;
   });
 }
 
 const setMusicList =  () => {
  songs.forEach(song => addList(song));
 }
 
 const FirstSetUp = () => {
  audio.src = musicData[index -1].src;
  setData(musicData[index -1]);
  setMusicList();
 }
 FirstSetUp()
 
 const filterCat = (cat) => {
  songs = musicData.filter(song => song.category == cat);
  while(musicList.hasChildNodes()){
    musicList.removeChild(musicList.firstChild);
  }
  setMusicList()
 }
 const filterAll = () => {
  songs = musicData;
  while(musicList.hasChildNodes()){
    musicList.removeChild(musicList.firstChild);
  }
  setMusicList()
 }
function setEqualizer(action = false){
 const elc = musicList.getElementsByClassName("equalize")[index-1];
 const thumb =  document.querySelector(".thumbnail");
 if(elc.classList.contains("pause")) {
   elc.classList.remove("pause")
 } else {
  if(action) {
   elc.classList.add("pause")
  }
 }
 if(thumb.classList.contains("spin") && audio.paused && action){
  thumb.classList.add("pause");
 } else if(thumb.classList.contains("spin") &&!audio.paused){
  thumb.classList.remove("pause");
 }
}
</script>
</body>
</html>
