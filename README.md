<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Student Wellness Monitor</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    :root{ --accent:#7c3aed; --accent2:#06b6d4; }
    body{ font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial; }
    .glass{ backdrop-filter: blur(6px); background: linear-gradient(180deg, rgba(255,255,255,0.7), rgba(255,255,255,0.55)); }
    .hero-bg{ background: radial-gradient(900px 400px at 10% 10%, rgba(124,58,237,0.12), transparent), radial-gradient(800px 350px at 90% 80%, rgba(6,182,212,0.12), transparent); }
    @media (max-width:640px){ .hide-sm{ display:none; } }
  </style>
</head>
<body class="min-h-screen bg-gradient-to-br from-sky-50 via-white to-violet-50 text-gray-800">
  <header class="max-w-6xl mx-auto p-4 flex items-center justify-between">
    <div class="flex items-center gap-3">
      <div class="w-11 h-11 rounded-lg bg-gradient-to-br from-violet-600 to-cyan-500 flex items-center justify-center text-white font-bold shadow">SW</div>
      <div>
        <div class="text-lg font-extrabold">Student Wellness Monitor</div>
        <div class="text-xs text-gray-500">Healthy habits, happy students</div>
      </div>
    </div>
    <div class="flex gap-2">
      <button id="openDemo" class="px-3 py-2 rounded-md bg-white glass text-sm">Demo</button>
      <button id="signin" class="px-3 py-2 rounded-md bg-gradient-to-r from-violet-600 to-cyan-500 text-white text-sm">Sign in</button>
    </div>
  </header>

  <!-- HERO / FRONT PAGE -->
  <section class="hero-bg py-8">
    <div class="max-w-6xl mx-auto px-4 grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
      <div class="space-y-4">
        <h1 class="text-4xl font-extrabold leading-tight text-transparent bg-clip-text bg-gradient-to-r from-violet-600 to-cyan-500">Track wellness. Build habits. Thrive at school.</h1>
        <p class="text-gray-700">A colorful, student-friendly platform to log sleep, mood, activity, attendance and nutrition — with dashboards, early alerts, AI-backed tips, and fun tools to stay motivated.</p>
        <div class="flex gap-3">
          <a href="#dashboard" class="px-5 py-3 rounded-lg bg-gradient-to-r from-violet-600 to-cyan-500 text-white font-medium">Open Dashboard</a>
          <a href="#features" class="px-5 py-3 rounded-lg border bg-white glass">See Features</a>
        </div>

        <div class="grid grid-cols-3 gap-3 mt-4 hide-sm">
          <div class="p-3 rounded-xl bg-white shadow-sm text-center">
            <div class="text-xs text-gray-400">Avg Sleep</div>
            <div class="font-bold">7.3 hrs</div>
          </div>
          <div class="p-3 rounded-xl bg-white shadow-sm text-center">
            <div class="text-xs text-gray-400">Weekly Mood</div>
            <div class="font-bold">🙂 3.9</div>
          </div>
          <div class="p-3 rounded-xl bg-white shadow-sm text-center">
            <div class="text-xs text-gray-400">Active Days</div>
            <div class="font-bold">5/7</div>
          </div>
        </div>
      </div>

      <div class="p-6 rounded-2xl shadow-xl glass">
        <div class="flex items-center justify-between mb-3">
          <div><div class="text-xs text-gray-500">Welcome back,</div><div class="font-semibold">Alex</div></div>
          <div class="text-xs text-gray-500">Demo • Local data</div>
        </div>
        <div class="grid grid-cols-2 gap-3">
          <div class="p-3 bg-white rounded-xl shadow-sm">
            <div class="text-xs text-gray-400">Sleep</div>
            <div class="font-bold text-xl">6.8 hrs</div>
            <div class="text-xs text-gray-500 mt-1">Goal: 8 hrs</div>
          </div>
          <div class="p-3 bg-white rounded-xl shadow-sm">
            <div class="text-xs text-gray-400">Stress</div>
            <div class="font-bold text-xl">6/10</div>
            <div class="text-xs text-gray-500 mt-1">Tip: 10-min breathing</div>
          </div>
          <div class="col-span-2 p-3 bg-white rounded-xl shadow-sm">
            <div class="text-xs text-gray-400">Today's Mood</div>
            <div class="flex items-center gap-3 mt-2">
              <div class="text-2xl">🙂</div>
              <div><div class="font-semibold">Okay</div><div class="text-xs text-gray-500">Notes: finished assignment</div></div>
            </div>
          </div>
        </div>

        <div class="mt-4 grid grid-cols-3 gap-2">
          <button id="openPomodoro" class="col-span-1 px-3 py-2 rounded-lg border">Pomodoro</button>
          <button id="openHabits" class="col-span-1 px-3 py-2 rounded-lg border">Habits</button>
          <button id="openChallenges" class="col-span-1 px-3 py-2 rounded-lg border">Challenges</button>
        </div>
      </div>
    </div>
  </section>

  <!-- FEATURES SUMMARY -->
  <section id="features" class="max-w-6xl mx-auto p-6 mt-6">
    <h2 class="text-2xl font-semibold mb-3">Features you'll love</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
      <div class="p-4 rounded-xl bg-white shadow-sm">
        <h4 class="font-semibold">Log & Monitor</h4>
        <p class="text-sm text-gray-500">Quick logs for sleep, attendance, stress, activity, nutrition and mood with optional notes and tags.</p>
      </div>
      <div class="p-4 rounded-xl bg-white shadow-sm">
        <h4 class="font-semibold">Dashboards & Alerts</h4>
        <p class="text-sm text-gray-500">Interactive charts, trend detection and early alert notifications for burnout risk or low engagement.</p>
      </div>
      <div class="p-4 rounded-xl bg-white shadow-sm">
        <h4 class="font-semibold">AI Suggestions</h4>
        <p class="text-sm text-gray-500">Personalized recommendations for sleep, stress reduction, time management and counseling resources.</p>
      </div>
    </div>
  </section>

  <!-- MAIN DASHBOARD + TOOLS -->
  <main id="dashboard" class="max-w-6xl mx-auto p-6">
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
      <!-- Left column: Logging + Tools -->
      <aside class="lg:col-span-1 glass p-4 rounded-2xl shadow">
        <h3 class="font-semibold mb-2">Quick Log</h3>
        <form id="logForm" class="space-y-2">
          <input id="studentName" placeholder="Your name" class="w-full p-2 rounded-lg border" />
          <div class="grid grid-cols-2 gap-2">
            <input id="sleep" type="number" min="0" max="24" step="0.5" placeholder="Sleep (hrs)" class="p-2 rounded-lg border" />
            <input id="attendance" type="number" min="0" max="100" placeholder="Attendance %" class="p-2 rounded-lg border" />
          </div>
          <div class="grid grid-cols-3 gap-2">
            <input id="stress" type="number" min="1" max="10" placeholder="Stress (1-10)" class="p-2 rounded-lg border" />
            <input id="activity" type="number" min="0" max="300" placeholder="Activity (mins)" class="p-2 rounded-lg border" />
            <select id="nutrition" class="p-2 rounded-lg border"><option>Nutrition</option><option value="1">1</option><option value="2">2</option><option value="3" selected>3</option><option value="4">4</option><option value="5">5</option></select>
          </div>
          <select id="mood" class="w-full p-2 rounded-lg border"><option>😊 Happy</option><option>🙂 Okay</option><option>😔 Sad</option><option>😠 Stressed</option><option>😴 Tired</option></select>
          <textarea id="notes" rows="2" class="w-full p-2 rounded-lg border" placeholder="Notes (optional)"></textarea>
          <div class="flex gap-2">
            <button type="submit" class="flex-1 px-3 py-2 rounded-lg bg-gradient-to-r from-violet-600 to-cyan-500 text-white">Save</button>
            <button id="exportCSV" type="button" class="px-3 py-2 rounded-lg border">Export CSV</button>
          </div>
        </form>

        <div class="mt-4">
          <h4 class="font-semibold">Gamified Tools</h4>
          <div class="flex gap-2 mt-2">
            <button id="openPomodoro2" class="px-2 py-1 rounded bg-white border">Pomodoro</button>
            <button id="openHabits2" class="px-2 py-1 rounded bg-white border">Habits</button>
            <button id="openChallenges2" class="px-2 py-1 rounded bg-white border">Challenges</button>
          </div>
          <div class="mt-3 text-sm text-gray-500">Earn badges for consistent sleep, activity & mood improvements.</div>
        </div>

        <div class="mt-4">
          <h4 class="font-semibold">Privacy</h4>
          <p class="text-xs text-gray-500">Demo stores data locally. For production add secure backend, encryption, consent, and RBAC (role-based access).</p>
        </div>
      </aside>

      <!-- Middle + Right: Charts & Recommendations -->
      <section class="lg:col-span-2 glass p-4 rounded-2xl shadow">
        <div class="flex items-center justify-between">
          <h3 class="font-semibold">Dashboard</h3>
          <div class="text-sm text-gray-500">View: <span id="currentView">Student</span></div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-3">
          <div class="p-3 bg-white rounded-xl shadow-sm">
            <h5 class="font-medium text-sm">Sleep & Stress (Last 14)</h5>
            <canvas id="sleepStressChart" height="180"></canvas>
          </div>
          <div class="p-3 bg-white rounded-xl shadow-sm">
            <h5 class="font-medium text-sm">Activity & Attendance</h5>
            <canvas id="activityChart" height="180"></canvas>
          </div>
          <div class="p-3 bg-white rounded-xl shadow-sm md:col-span-2">
            <h5 class="font-medium text-sm">Mood Timeline</h5>
            <canvas id="moodChart" height="110"></canvas>
            <div class="flex gap-4 mt-3">
              <div><div class="text-xs text-gray-400">Avg Sleep</div><div id="avgSleep" class="font-bold">--</div></div>
              <div><div class="text-xs text-gray-400">Avg Stress</div><div id="avgStress" class="font-bold">--</div></div>
              <div><div class="text-xs text-gray-400">Attendance</div><div id="avgAttendance" class="font-bold">--</div></div>
            </div>
          </div>
        </div>

        <div class="mt-4 p-3 bg-white rounded-xl shadow-sm">
          <h5 class="font-semibold">AI Recommendation Panel</h5>
          <div id="recommendations" class="grid grid-cols-1 gap-2 mt-2"></div>
        </div>

        <div class="mt-4 p-3 bg-white rounded-xl shadow-sm">
          <h5 class="font-semibold">Resources & Counseling</h5>
          <div class="grid grid-cols-1 md:grid-cols-3 gap-2 mt-2 text-sm text-gray-600">
            <div><strong>Quick exercises</strong><div>Breathing, 5-min stretch</div></div>
            <div><strong>Time tools</strong><div>Pomodoro, planning templates</div></div>
            <div><strong>Counseling</strong><div>How to request a session</div></div>
          </div>
        </div>

      </section>
    </div>

    <footer class="mt-6 text-center text-sm text-gray-500">Demo • Local data • For production, implement secure backend, consent flows, and compliance checks (e.g., COPPA, GDPR).</footer>
  </main>

  <!-- MODALS / TOOLS: Pomodoro & Habits -->
  <div id="modal" class="fixed inset-0 hidden items-center justify-center p-4 z-50">
    <div class="bg-white rounded-xl shadow-xl w-full max-w-md p-4">
      <div id="modalContent"></div>
      <div class="mt-3 text-right"><button id="closeModal" class="px-3 py-1 rounded border">Close</button></div>
    </div>
  </div>

  <script>
    // --- Storage & utils ---
    const STORAGE_KEY = 'student_wellness_v2';
    const qs = s => document.querySelector(s);
    const save = (key,val)=> localStorage.setItem(key, JSON.stringify(val));
    const load = (key)=> { const r = localStorage.getItem(key); return r? JSON.parse(r): null };

    function loadLogs(){ return load(STORAGE_KEY) || []; }
    function saveLogs(arr){ save(STORAGE_KEY, arr); }
    function addLog(entry){ const arr = loadLogs(); arr.push(entry); if(arr.length>500) arr.shift(); saveLogs(arr); renderAll(); }

    // --- Alerts & recommendations (simple demo rules + heuristics) ---
    function computeAlerts(latest){ const rules = []; if(!latest) return rules; if(latest.sleep < 5) rules.push('Low sleep: under 5 hrs'); if(latest.stress >=8) rules.push('High stress: consider counselor'); if(latest.attendance < 75) rules.push('Low attendance: talk to teacher'); if(latest.activity < 15) rules.push('Low activity'); return rules; }

    function generateRecommendations(recent){ const recs = []; if(!recent.length) return ['No data yet — log to get tips.']; const last = recent[recent.length-1]; if(last.sleep < 6) recs.push('Wind-down routine: dim lights, avoid screens 30min before bed.'); else recs.push('Good sleep — keep consistent bedtimes.'); if(last.stress >=7) recs.push('Try 10-min breathing and 25-min focused work + 5-min break (Pomodoro).'); if(last.activity < 20) recs.push('Aim for 20-30 mins of movement—walk or home workout.'); if(last.nutrition<=2) recs.push('Add a protein-rich snack and water regularly.'); if(last.mood.includes('Sad')|| last.mood.includes('Stressed')) recs.push('Consider booking a chat with a counselor or trusted adult.'); // badges
      const badges = computeBadges(recent); if(badges.length) recs.push('Badges earned: '+badges.join(', ')); return recs; }

    // --- Badges / Gamification ---
    function computeBadges(recent){ const badges = []; if(!recent.length) return badges; const last7 = recent.slice(-7); const consistentSleep = last7.filter(r=>r.sleep>=7).length >=5; if(consistentSleep) badges.push('Sleep Star'); const activeDays = last7.filter(r=>r.activity>=20).length >=4; if(activeDays) badges.push('Active Streak'); const moodUp = last7.filter(r=> r.mood.includes('Happy') || r.mood.includes('Okay')).length >=5; if(moodUp) badges.push('Mood Booster'); return badges; }

    // --- CSV Export ---
    function exportCSV(){ const rows = loadLogs(); if(!rows.length){ alert('No data to export'); return; } const keys = ['time','name','sleep','attendance','stress','activity','nutrition','mood','notes']; let csv = keys.join(',')+'
'; rows.forEach(r=>{ csv += keys.map(k=> '"'+ (r[k]??'') .toString().replace(/"/g,'""') + '"').join(',') + '
'; }); const blob = new Blob([csv],{type:'text/csv'}); const url = URL.createObjectURL(blob); const a = document.createElement('a'); a.href = url; a.download = 'wellness_export.csv'; a.click(); URL.revokeObjectURL(url); }

    // --- Charts setup ---
    let sleepStressChart, activityChart, moodChart;
    function getMoodScore(m){ if(m.includes('Happy')) return 5; if(m.includes('Okay')) return 4; if(m.includes('Tired')) return 3; if(m.includes('Sad')) return 2; if(m.includes('Stressed')) return 1; return 3; }

    function renderCharts(){ const arr = loadLogs(); const last14 = arr.slice(-14); const labels = last14.map(r=> new Date(r.time).toLocaleDateString()); const sleepData = last14.map(r=>r.sleep); const stressData = last14.map(r=>r.stress); const activityData = last14.map(r=>r.activity); const moodData = last14.map(r=>getMoodScore(r.mood)); const attendanceData = last14.map(r=>r.attendance);

      if(sleepStressChart) sleepStressChart.destroy(); const ctx1 = qs('#sleepStressChart'); sleepStressChart = new Chart(ctx1,{ type:'line', data:{ labels, datasets:[ { label:'Sleep (hrs)', data:sleepData, tension:0.3, yAxisID:'y' }, { label:'Stress (1-10)', data:stressData, tension:0.3, yAxisID:'y1' } ]}, options:{ interaction:{mode:'index',intersect:false}, scales:{ y:{ beginAtZero:true, max:12 }, y1:{ position:'right', beginAtZero:true, max:10 } } } });

      if(activityChart) activityChart.destroy(); const ctx2 = qs('#activityChart'); activityChart = new Chart(ctx2,{ type:'bar', data:{ labels, datasets:[ { label:'Activity (mins)', data:activityData }, { label:'Attendance (%)', data:attendanceData, type:'line', tension:0.3 } ]}, options:{ scales:{ y:{ beginAtZero:true } } } });

      if(moodChart) moodChart.destroy(); const ctx3 = qs('#moodChart'); moodChart = new Chart(ctx3,{ type:'line', data:{ labels, datasets:[{ label:'Mood (1-5)', data:moodData, fill:true, tension:0.4 }] }, options:{ scales:{ y:{ beginAtZero:true, min:0, max:6 } } } });

      // summary
      const all = arr; if(all.length){ qs('#avgSleep').textContent = (all.reduce((s,r)=>s+r.sleep,0)/all.length).toFixed(1)+' hrs'; qs('#avgStress').textContent = (all.reduce((s,r)=>s+r.stress,0)/all.length).toFixed(1); qs('#avgAttendance').textContent = Math.round(all.reduce((s,r)=>s+r.attendance,0)/all.length)+'%'; } else { qs('#avgSleep').textContent='--'; qs('#avgStress').textContent='--'; qs('#avgAttendance').textContent='--'; }
    }

    // --- Render recommendations & alerts ---
    function renderRecommendations(){ const arr = loadLogs(); const recs = generateRecommendations(arr); const el = qs('#recommendations'); el.innerHTML = ''; recs.forEach(r=>{ const d = document.createElement('div'); d.className='p-2 rounded border bg-gray-50 text-sm'; d.textContent = r; el.appendChild(d); }); }
    function renderAlerts(){ const arr = loadLogs(); const latest = arr[arr.length-1]; const el = qs('#alerts'); if(!el) return; el.innerHTML = ''; const rules = computeAlerts(latest); if(!latest) el.innerHTML = '<div class="text-gray-500">No logs yet.</div>'; else if(rules.length===0) el.innerHTML = '<div class="text-green-600">All good today</div>'; else rules.forEach(r=>{ const d = document.createElement('div'); d.className='text-sm text-yellow-700'; d.textContent = r; el.appendChild(d); }); }

    function renderAll(){ renderCharts(); renderRecommendations(); renderAlerts(); }

    // --- Form handling ---
    qs('#logForm').addEventListener('submit', e=>{ e.preventDefault(); const entry = { time: new Date().toISOString(), name: qs('#studentName').value || 'Student', sleep: parseFloat(qs('#sleep').value)||0, attendance: parseFloat(qs('#attendance').value)||100, stress: parseInt(qs('#stress').value)||3, activity: parseInt(qs('#activity').value)||0, nutrition: parseInt(qs('#nutrition').value)||3, mood: qs('#mood').value || '🙂 Okay', notes: qs('#notes').value || '' }; addLog(entry); qs('#logForm').reset(); alert('Saved! Check recommendations.'); });
    qs('#exportCSV').addEventListener('click', exportCSV);

    // --- Modals / Tools: Pomodoro and Habits ---
    const modal = qs('#modal'); const modalContent = qs('#modalContent'); function openModal(html){ modalContent.innerHTML = html; modal.classList.remove('hidden'); modal.style.display='flex'; }
    function closeModal(){ modal.classList.add('hidden'); modal.style.display='none'; }
    qs('#closeModal').addEventListener('click', closeModal);

    // Pomodoro tool
    function showPomodoro(){ const html = `
      <h3 class="text-lg font-semibold">Pomodoro Timer</h3>
      <div class="mt-3 text-center">
        <div id="timerDisplay" class="text-4xl font-bold">25:00</div>
        <div class="mt-3 flex gap-2 justify-center"><button id="startPom" class="px-3 py-1 rounded bg-gradient-to-r from-violet-600 to-cyan-500 text-white">Start</button><button id="stopPom" class="px-3 py-1 rounded border">Stop</button></div>
      </div>
    `; openModal(html); let timer=null, remaining=25*60; const display=modal.querySelector('#timerDisplay'); modal.querySelector('#startPom').addEventListener('click', ()=>{ if(timer) return; timer = setInterval(()=>{ remaining--; const m = String(Math.floor(remaining/60)).padStart(2,'0'); const s = String(remaining%60).padStart(2,'0'); display.textContent = `${m}:${s}`; if(remaining<=0){ clearInterval(timer); timer=null; remaining=25*60; alert('Pomodoro complete! Take 5 min break.'); } },1000); }); modal.querySelector('#stopPom').addEventListener('click', ()=>{ if(timer) clearInterval(timer); timer=null; remaining=25*60; display.textContent='25:00'; }); }

    // Habits tool (simple tracker)
    function showHabits(){ const habits = load('habits') || [{id:'sleep',name:'8+ hrs sleep'},{id:'activity',name:'20+ mins activity'},{id:'journal',name:'Daily journaling'}]; let html = `<h3 class="text-lg font-semibold">Habit Tracker</h3><div class="mt-3">`; habits.forEach(h=>{ html += `<div class="flex items-center justify-between p-2 bg-gray-50 rounded mb-2"><div>${h.name}</div><div><button data-id="${h.id}" class="markBtn px-2 py-1 rounded border">Mark today</button></div></div>`; }); html += `<div class="mt-2 text-sm text-gray-500">Streaks and badges encourage consistency.</div></div>`; openModal(html); modal.querySelectorAll('.markBtn').forEach(b=> b.addEventListener('click', ()=>{ const id = b.dataset.id; const key = 'habit_'+id; const today = new Date().toDateString(); save(key, today); alert('Marked for today!'); renderAll(); })); }

    // --- Seed demo data if none ---
    function seedDemo(){ const arr = loadLogs(); if(arr.length) return; const moods = ['😊 Happy','🙂 Okay','😔 Sad','😠 Stressed','😴 Tired']; const demo = []; for(let i=14;i>=0;i--){ demo.push({ time: new Date(Date.now()-i*24*3600*1000).toISOString(), name: 'Alex', sleep: Math.round((6+Math.random()*2.5)*10)/10, attendance: 85+Math.round(Math.random()*14), stress: 2+Math.round(Math.random()*6), activity: 10+Math.round(Math.random()*60), nutrition: 2+Math.round(Math.random()*3), mood: moods[Math.floor(Math.random()*moods.length)], notes: '' }); } saveLogs(demo); }

    // --- Button hooks ---
    qs('#openPomodoro').addEventListener('click', showPomodoro);
    qs('#openPomodoro2').addEventListener('click', showPomodoro);
    qs('#openHabits').addEventListener('click', showHabits);
    qs('#openHabits2').addEventListener('click', showHabits);

    // Demo open
    qs('#openDemo').addEventListener('click', ()=>{ window.scrollTo({top: document.querySelector('#dashboard').offsetTop, behavior:'smooth'}); });

    // init
    seedDemo(); renderAll();
    window.__WELL = { loadLogs, saveLogs, addLog, exportCSV };
  </script>
</body>
</html>

