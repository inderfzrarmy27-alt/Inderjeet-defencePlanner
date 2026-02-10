<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Student Self Study Portal</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
  margin:0;
  font-family:'Segoe UI', Arial, sans-serif;
  background:#f4f6f9;
  overflow-x:hidden;
}

/* ANIMATIONS */
@keyframes fadeSlide{
  from{opacity:0; transform:translateY(30px);}
  to{opacity:1; transform:translateY(0);}
}
@keyframes scaleIn{
  from{opacity:0; transform:scale(0.9);}
  to{opacity:1; transform:scale(1);}
}

/* LOGIN PAGE */
#loginPage{
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background:linear-gradient(135deg,#1d3557,#457b9d);
}
.login-box{
  background:#fff;
  padding:30px;
  width:330px;
  border-radius:12px;
  box-shadow:0 15px 40px rgba(0,0,0,0.25);
  animation:scaleIn 0.8s;
}
.login-box h2{
  text-align:center;
  margin-bottom:20px;
}
.login-box input{
  width:100%;
  padding:12px;
  margin:10px 0;
  border:1px solid #ccc;
  border-radius:6px;
}
.login-box button{
  width:100%;
  padding:12px;
  background:#1d3557;
  color:#fff;
  border:none;
  font-size:16px;
  border-radius:6px;
  cursor:pointer;
  transition:all 0.3s;
}
.login-box button:hover{
  background:#0f2238;
  transform:scale(1.04);
}

/* MAIN PAGE */
#mainPage{
  display:none;
  animation:fadeSlide 1s;
}

/* HEADER */
header{
  background:#1d3557;
  color:#fff;
  padding:20px;
  text-align:center;
}

/* NAVBAR */
nav{
  display:flex;
  background:#457b9d;
  flex-wrap:wrap;
}
nav button{
  flex:1;
  padding:14px;
  border:none;
  background:none;
  color:#fff;
  cursor:pointer;
  position:relative;
  transition:background 0.3s;
}
nav button::after{
  content:'';
  position:absolute;
  bottom:0;
  left:0;
  width:0;
  height:3px;
  background:#fff;
  transition:0.4s;
}
nav button:hover::after{
  width:100%;
}
nav button:hover{
  background:#1d3557;
}

/* SECTIONS */
section{
  display:none;
  padding:25px;
  animation:fadeSlide 0.6s;
}
section h2{
  color:#1d3557;
}

/* CARDS */
.card{
  background:#fff;
  padding:18px;
  margin:15px 0;
  border-radius:12px;
  box-shadow:0 8px 18px rgba(0,0,0,0.1);
  transition:all 0.4s;
}
.card:hover{
  transform:translateY(-8px);
  box-shadow:0 18px 35px rgba(0,0,0,0.18);
}
ul li{
  margin:8px 0;
}
</style>
</head>

<body>

<!-- LOGIN PAGE -->
<div id="loginPage">
  <div class="login-box">
    <h2>Student Login</h2>
    <input type="text" placeholder="Student ID">
    <input type="password" placeholder="Password">
    <button onclick="login()">Login</button>
  </div>
</div>

<!-- MAIN DASHBOARD -->
<div id="mainPage">

<header>
  <h1>Student Self Study Portal</h1>
  <p>Learn • Practice • Succeed</p>
</header>

<nav>
  <button onclick="showSection('home')">Home</button>
  <button onclick="showSection('self')">Self Study</button>
  <button onclick="showSection('subjects')">Subjects</button>
  <button onclick="showSection('planner')">Study Planner</button>
  <button onclick="showSection('tests')">Practice Tests</button>
  <button onclick="showSection('notice')">Notices</button>
</nav>

<section id="home">
  <h2>Welcome Student</h2>
  <div class="card">
    <p><b>Name:</b> Rahul Kumar</p>
    <p><b>Class:</b> 10th</p>
    <p><b>Roll No:</b> 10245</p>
    <p><b>Goal:</b> Board Exam + Competitive Exams</p>
  </div>
</section>

<section id="self">
  <h2>Self Study Resources</h2>
  <div class="card">
    <ul>
      <li>📘 Daily Concept Notes (PDF)</li>
      <li>🎥 Recorded Video Lectures</li>
      <li>📝 Topic-wise Practice Sheets</li>
      <li>📚 Previous Year Question Papers</li>
    </ul>
  </div>
</section>

<section id="subjects">
  <h2>Subjects Offered</h2>
  <div class="card">
    <b>English</b>
    <p>Grammar, Writing Skills, Reading Comprehension</p>
  </div>
  <div class="card">
    <b>Mathematics</b>
    <p>Algebra, Geometry, Trigonometry, Mensuration</p>
  </div>
  <div class="card">
    <b>Reasoning</b>
    <p>Logical Reasoning, Verbal & Non-Verbal</p>
  </div>
  <div class="card">
    <b>General Knowledge</b>
    <p>Current Affairs, History, Geography, Polity</p>
  </div>
</section>

<section id="planner">
  <h2>Weekly Study Planner</h2>
  <div class="card">
    <ul>
      <li>Monday – Mathematics Practice</li>
      <li>Tuesday – English Grammar</li>
      <li>Wednesday – GK & Current Affairs</li>
      <li>Thursday – Reasoning Practice</li>
      <li>Friday – Subject Test</li>
      <li>Saturday – Full Revision</li>
      <li>Sunday – Rest & Light Reading</li>
    </ul>
  </div>
</section>

<section id="tests">
  <h2>Practice Tests</h2>
  <div class="card">
    <ul>
      <li>English Test – 20 MCQs</li>
      <li>Mathematics Test – 25 MCQs</li>
      <li>Reasoning Test – 30 MCQs</li>
      <li>Full Length Mock Test – 90 Minutes</li>
    </ul>
  </div>
</section>

<section id="notice">
  <h2>Important Notices</h2>
  <div class="card">
    <ul>
      <li>📢 Monthly Test on 25 February</li>
      <li>📢 New Study Material Uploaded</li>
      <li>📢 Result will be declared online</li>
    </ul>
  </div>
</section>

</div>

<script>
function login(){
  document.getElementById("loginPage").style.display="none";
  document.getElementById("mainPage").style.display="block";
  showSection('home');
}
function showSection(id){
  let sections=document.querySelectorAll("section");
  sections.forEach(s=>s.style.display="none");
  document.getElementById(id).style.display="block";
}
</script>

</body>
</html>
