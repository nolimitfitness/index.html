<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>No Limit Fitness – Link in Bio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Oswald:wght@500;700&display=swap" rel="stylesheet">
<style>
:root {
  color-scheme: dark;
  --bg: #0b0b0c;
  --card: #151517;
  --line: #2c2c31;
  --tx: #f2f2f2;
  --mut: #9a9aa3;
  --gold: #d4af37;
  --gold2: #f1d77a;
  --silver: #c8ccd2;
  --err: #ff6b6b;
  --hd: Oswald, "Arial Narrow", Impact, sans-serif;
  box-sizing: border-box;
  padding-top: env(safe-area-inset-top, 0px);
  padding-bottom: env(safe-area-inset-bottom, 0px);
}

*, *::before, *::after { box-sizing: inherit; }
html { scroll-padding-top: env(safe-area-inset-top, 0px); background: var(--bg); }
body { margin: 0; background: var(--bg); color: var(--tx); font: 16px/1.5 -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }

.wrap { max-width: 480px; margin: 0 auto; padding: 24px 16px 40px; min-height: 100vh; display: flex; flex-direction: column; justify-content: space-between; }
.main-content { width: 100%; }

/* Profile Header Styles for IG Link-in-Bio */
.profile-header { text-align: center; padding: 12px 0 24px; }
.avatar-container { position: relative; width: 92px; height: 92px; margin: 0 auto 16px; border-radius: 50%; padding: 3px; background: linear-gradient(135deg, var(--gold), var(--gold2)); box-shadow: 0 8px 24px rgba(212, 175, 55, 0.2); }
.avatar { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; background: #0d0d0f; display: flex; align-items: center; justify-content: center; font: 700 32px var(--hd); color: var(--gold); }
.logo { font: 700 24px/1.1 var(--hd); letter-spacing: .12em; background: linear-gradient(90deg, var(--gold), var(--gold2), var(--gold)); -webkit-background-clip: text; background-clip: text; color: transparent; text-transform: uppercase; }
.sub { color: var(--silver); letter-spacing: .2em; font-size: 11px; text-transform: uppercase; margin-top: 6px; }
.bio { color: var(--mut); font-size: 14px; margin-top: 10px; line-height: 1.4; padding: 0 10px; }

/* Bio Link Buttons */
.links-stack { display: flex; flex-direction: column; gap: 12px; margin-bottom: 24px; }
.bio-btn { display: flex; align-items: center; justify-content: space-between; width: 100%; padding: 16px 20px; background: var(--card); border: 1px solid var(--line); border-radius: 14px; color: var(--tx); font: 700 15px var(--hd); letter-spacing: .08em; text-transform: uppercase; text-decoration: none; cursor: pointer; transition: all .2s ease; box-shadow: 0 4px 12px rgba(0,0,0,0.3); }
.bio-btn:hover, .bio-btn:focus-visible { border-color: var(--gold); background: #1a1a1e; transform: translateY(-2px); outline: none; }
.bio-btn.highlight { background: linear-gradient(135deg, var(--gold), var(--gold2)); color: #111; border: 0; box-shadow: 0 6px 20px rgba(212, 175, 55, 0.35); }
.bio-btn svg { width: 20px; height: 20px; fill: currentColor; flex-shrink: 0; }

/* Questionnaire View Container */
#questionnaire-container { display: none; margin-top: 10px; animation: fadeIn .3s ease; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: translateY(0); } }

.track { height: 4px; background: var(--line); border-radius: 4px; overflow: hidden; margin-bottom: 16px; }
#bar { height: 100%; width: 0; background: linear-gradient(90deg, var(--gold), var(--gold2)); transition: width .3s; }
.card { background: var(--card); border: 1px solid var(--line); border-radius: 16px; padding: 20px; box-shadow: 0 8px 30px rgba(0,0,0,0.4); }

.back-hub-row { display: flex; justify-content: space-between; align-items: center; margin-bottom: 16px; }
.back-hub-btn { background: transparent; border: 1px solid var(--line); color: var(--silver); padding: 8px 14px; border-radius: 8px; font-size: 13px; font-weight: 600; cursor: pointer; text-transform: uppercase; letter-spacing: .05em; }
.back-hub-btn:hover { border-color: var(--gold); color: var(--gold); }

h2 { font: 700 20px var(--hd); letter-spacing: .06em; text-transform: uppercase; color: var(--gold); margin: 0 0 4px; }
.note { color: var(--mut); font-size: 13px; margin: 0 0 16px; }

.f { margin-bottom: 16px; }
.lb { display: block; font-weight: 600; color: var(--silver); margin-bottom: 6px; font-size: 14px; }
input, textarea { width: 100%; background: #0d0d0f; color: var(--tx); border: 1px solid var(--line); border-radius: 10px; padding: 12px; font: inherit; font-size: 15px; }
input:focus, textarea:focus, .chip:focus-visible, .btn:focus-visible { outline: 2px solid var(--gold); outline-offset: 1px; }

.chips { display: flex; flex-wrap: wrap; gap: 8px; }
.chip { background: #0d0d0f; color: var(--tx); border: 1px solid var(--line); border-radius: 999px; padding: 8px 14px; font: inherit; font-size: 13px; cursor: pointer; transition: all .15s; }
.chip[aria-pressed=true] { background: var(--gold); color: #111; border-color: var(--gold); font-weight: 600; }
.hint { color: var(--mut); font-size: 12px; margin-top: 6px; }

.err .lb { color: var(--err); }
.err input, .err textarea { border-color: var(--err); }
.msg { color: var(--err); font-size: 12px; margin-top: 4px; }

.nav { display: flex; gap: 10px; margin-top: 16px; }
.btn { flex: 1; padding: 14px; border-radius: 12px; font: 700 14px var(--hd); letter-spacing: .1em; text-transform: uppercase; cursor: pointer; border: 1px solid var(--gold); background: transparent; color: var(--gold); text-align: center; text-decoration: none; display: inline-flex; align-items: center; justify-content: center; transition: all .2s; }
.btn.p { background: linear-gradient(135deg, var(--gold), var(--gold2)); color: #111; border: 0; }

textarea.sum { height: 240px; font: 12px/1.5 ui-monospace, Menlo, monospace; color: var(--silver); }
.foot { text-align: center; color: var(--mut); font-size: 11px; margin-top: 24px; letter-spacing: .05em; text-transform: uppercase; }
</style>
</head>
<body>
<div class="wrap">
  <div class="main-content">
    
    <!-- Instagram Bio Hub View -->
    <div id="hub-view">
      <header class="profile-header">
        <div class="avatar-container">
          <div class="avatar">NLF</div>
        </div>
        <div class="logo">No Limit Fitness</div>
        <div class="sub">Elite Online Coaching</div>
        <div class="bio">Transform your physique with science-backed training & custom nutrition. Take the intake quiz below to get started.</div>
      </header>

      <div class="links-stack">
        <!-- Questionnaire Link Button -->
        <button class="bio-btn highlight" id="open-quiz-btn" type="button">
          <span>Start Client Questionnaire</span>
          <svg viewBox="0 0 24 24"><path d="M5 13h11.86l-5.6 5.6 1.42 1.42L21.34 12l-7.72-8-1.42 1.42L16.86 11H5v2z"/></svg>
        </button>

        <!-- Direct WhatsApp Coaching Link (Replace YOUR_PHONE_NUMBER with your international format number e.g. 447123456789) -->
        <a class="bio-btn" href="https://wa.me/YOUR_PHONE_NUMBER?text=Hi%20No%20Limit%20Fitness,%20I'm%20ready%20to%20start%20coaching!" target="_blank" rel="noopener">
          <span>Chat on WhatsApp</span>
          <svg viewBox="0 0 24 24"><path d="M12.04 2c-5.46 0-9.91 4.45-9.91 9.91 0 1.75.46 3.45 1.32 4.95L2 22l5.25-1.38c1.45.79 3.08 1.21 4.79 1.21 5.46 0 9.91-4.45 9.91-9.91 0-2.65-1.03-5.14-2.9-7.01A9.816 9.816 0 0 0 12.04 2zm0 1.83c2.19 0 4.25.85 5.8 2.4 1.55 1.55 2.4 3.61 2.4 5.8 0 4.53-3.69 8.22-8.22 8.22-1.48 0-2.92-.39-4.18-1.13l-.3-.18-3.11.82.83-3.03-.2-.31a8.164 8.164 0 0 1-1.25-4.39c0-4.53 3.69-8.22 8.22-8.22zm4.5 10.13c-.25-.13-1.48-.73-1.71-.82-.23-.09-.4-.13-.57.13-.17.25-.66.82-.81.99-.15.17-.31.19-.56.06-.25-.13-1.05-.39-2-1.23-.74-.66-1.24-1.48-1.39-1.73-.15-.25-.02-.38.11-.51.11-.11.25-.31.37-.47.12-.16.16-.27.24-.45.08-.18.04-.34-.02-.47-.06-.13-.57-1.38-.79-1.89-.21-.5-.43-.43-.59-.44h-.5c-.17 0-.44.06-.67.31-.23.25-.88.86-.88 2.1 0 1.24.9 2.44 1.02 2.61.12.17 1.76 2.69 4.27 3.77.6.26 1.07.41 1.44.53.61.19 1.17.16 1.61.1.49-.07 1.48-.6 1.69-1.18.21-.58.21-1.08.15-1.18-.06-.1-.23-.16-.48-.29z"/></svg>
        </a>
      </div>
    </div>

    <!-- Questionnaire View -->
    <div id="questionnaire-container">
      <div class="back-hub-row">
        <button class="back-hub-btn" id="back-to-hub-btn" type="button">← Back to Link Hub</button>
        <span style="font-size:12px;color:var(--mut);" id="step-indicator">Step 1 of 7</span>
      </div>
      <div class="track"><div id="bar"></div></div>
      <div class="card" id="app"></div>
    </div>

  </div>

  <div class="foot">No Limit Fitness © 2026. All rights reserved.</div>
</div>

<script>
const S = [
  {t:"About You",n:"Takes about 5 minutes. Honest answers mean a plan built for you.",q:[
    {id:"name",l:"Full name",k:"text",r:1},
    {id:"email",l:"Email",k:"email",r:1},
    {id:"age",l:"Age",k:"number"},
    {id:"height",l:"Height",k:"text",p:"e.g. 175 cm or 5 ft 9 in"},
    {id:"weight",l:"Starting weight",k:"text",r:1,p:"e.g. 185 lb or 84 kg"},
    {id:"goalw",l:"Goal weight (if you have one)",k:"text"},
    {id:"ig",l:"Instagram handle",k:"text",p:"@yourhandle"},
    {id:"found",l:"How did you find us?",k:"radio",o:["Instagram","Friend or referral","TikTok","Google","Other"]}
  ]},
  {t:"Your Goals",n:"Let’s get clear on where you’re headed.",q:[
    {id:"goal",l:"Main goal",k:"radio",r:1,o:["Lose fat","Build muscle","Both (recomp)","Boost performance","General health"]},
    {id:"time",l:"Target timeline",k:"radio",o:["4–8 weeks","3 months","6 months","12+ months"]},
    {id:"why",l:"Why now? What does success look like for you?",k:"area"},
    {id:"block",l:"What has held you back before?",k:"multi",o:["Time","Motivation","Injuries","Nutrition","No clear plan","Accountability","Stress"]},
    {id:"commit",l:"How committed are you right now?",k:"scale10",r:1,h:"1 = not very · 10 = all in"},
    {id:"ten",l:"What would make it a 10?",k:"area"}
  ]},
  {t:"Training",n:"Your experience, schedule and setup.",q:[
    {id:"exp",l:"Training experience",k:"radio",r:1,o:["Beginner","Intermediate","Advanced"]},
    {id:"days",l:"Days per week you can train",k:"radio",r:1,o:["2","3","4","5","6"]},
    {id:"len",l:"Time per session",k:"radio",o:["30 min","45 min","60 min","75+ min"]},
    {id:"where",l:"Where will you train?",k:"multi",o:["Full gym","Home gym","Minimal equipment","Outdoors"]},
    {id:"style",l:"Training you enjoy",k:"multi",o:["Strength","Hypertrophy","HIIT","Steady cardio","Sports","Mobility"]},
    {id:"cur",l:"Current routine (if any)",k:"area"},
    {id:"inj",l:"Injuries or movements to avoid",k:"area"}
  ]},
  {t:"Nutrition",n:"How you eat right now, no judgment.",q:[
    {id:"meals",l:"Meals per day",k:"radio",o:["1–2","3","4","5+"]},
    {id:"diet",l:"Dietary preferences",k:"multi",o:["None","Vegetarian","Vegan","Keto","Halal","Kosher","Gluten-free","Dairy-free"]},
    {id:"allergy",l:"Food allergies or intolerances",k:"text"},
    {id:"dislike",l:"Foods you dislike or won’t eat",k:"text"},
    {id:"track",l:"Have you tracked food before?",k:"radio",o:["Never","Sometimes","Consistently"]},
    {id:"cook",l:"How do you usually eat?",k:"radio",o:["Cook most meals","A mix","Mostly takeout or convenience"]},
    {id:"water",l:"Daily water intake",k:"radio",o:["Under 1 L","1–2 L","2–3 L","3 L+"]},
    {id:"alc",l:"Alcohol per week",k:"radio",o:["None","1–3 drinks","4–7 drinks","8+ drinks"]},
    {id:"supp",l:"Supplements you take",k:"text"}
  ]},
  {t:"Lifestyle",n:"Recovery and daily habits drive results.",q:[
    {id:"sleep",l:"Average sleep per night",k:"radio",r:1,o:["Under 5 h","5–6 h","7–8 h","9+ h"]},
    {id:"stress",l:"Stress level",k:"scale",h:"1 = calm · 5 = overwhelmed"},
    {id:"energy",l:"Energy level",k:"scale",h:"1 = drained · 5 = great"},
    {id:"steps",l:"Typical daily steps",k:"radio",o:["Under 3k","3–6k","6–10k","10k+"]},
    {id:"job",l:"Your day-to-day activity",k:"radio",o:["Desk job","Mixed","On my feet","Physical work"]},
    {id:"bm",l:"Bowel movements",k:"radio",o:["Daily","Most days","Irregular","Rarely"]}
  ]},
  {t:"Starting Point",n:"Your starting photos and weight are needed to track your progress.",q:[
    {id:"waist",l:"Waist measurement (optional)",k:"text",p:"e.g. 82 cm or 32 in"},
    {id:"chest",l:"Chest measurement (optional)",k:"text"},
    {id:"hips",l:"Hips measurement (optional)",k:"text"},
    {id:"photos",l:"Starting photos",k:"radio",r:1,o:["I’ll send front, side and back photos on WhatsApp straight after this"]},
    {id:"cday",l:"Preferred weekend call day",k:"radio",r:1,o:["Saturday","Sunday","Either"]},
    {id:"ctime",l:"Preferred call time",k:"text",p:"e.g. 10am"}
  ]},
  {t:"Health & Wrap-up",n:"Helps your coach keep you safe.",q:[
    {id:"screen",l:"Do any of these apply to you?",k:"multi",r:1,o:["Chest pain when active","Dizziness or fainting","Heart condition","High blood pressure","Joint or bone problems","None of these"]},
    {id:"ec",l:"Emergency contact (name and number)",k:"text",r:1},
    {id:"med",l:"Medical conditions or medications your coach should know about",k:"area"},
    {id:"doc",l:"Has a doctor ever advised you to limit exercise?",k:"radio",r:1,o:["No","Yes","Not sure"]},
    {id:"more",l:"Anything else you want your coach to know?",k:"area"}
  ]}
];

const $ = (t, c, x) => {
  const e = document.createElement(t);
  if (c) e.className = c;
  if (x != null) e.textContent = x;
  return e;
};

let A = {}, step = 0;
try { A = JSON.parse(localStorage.getItem("nlf-intake") || "{}"); } catch (e) {}
const save = () => { try { localStorage.setItem("nlf-intake", JSON.stringify(A)); } catch (e) {} };
const empty = q => { const v = A[q.id]; return Array.isArray(v) ? !v.length : !(v || "").trim(); };

function field(q) {
  const f = $("div", "f"); f.id = "f-" + q.id;
  const lb = $("label", "lb", q.l + (q.r ? " *" : "")); lb.htmlFor = q.id; f.append(lb);
  if (q.k === "area") {
    const t = $("textarea"); t.id = q.id; t.rows = 3; t.value = A[q.id] || "";
    t.oninput = () => { A[q.id] = t.value; save(); }; f.append(t);
  } else if (q.k === "text" || q.k === "email" || q.k === "number") {
    const i = $("input"); i.id = q.id; i.type = q.k; i.value = A[q.id] || ""; i.placeholder = q.p || "";
    if (q.k === "number") i.inputMode = "numeric";
    i.oninput = () => { A[q.id] = i.value; save(); }; f.append(i);
  } else {
    const row = $("div", "chips");
    const opts = q.k === "scale" ? ["1", "2", "3", "4", "5"] : q.k === "scale10" ? ["1", "2", "3", "4", "5", "6", "7", "8", "9", "10"] : q.o;
    const on = o => q.k === "multi" ? (A[q.id] || []).includes(o) : A[q.id] === o;
    const paint = () => row.querySelectorAll("button").forEach(b => b.setAttribute("aria-pressed", on(b.textContent)));
    opts.forEach(o => {
      const b = $("button", "chip", o); b.type = "button";
      b.onclick = () => {
        if (q.k === "multi") {
          const a = A[q.id] || [];
          A[q.id] = a.includes(o) ? a.filter(x => x !== o) : [...a, o];
        } else {
          A[q.id] = A[q.id] === o ? "" : o;
        }
        save(); paint();
      };
      row.append(b);
    });
    paint(); f.append(row);
    if (q.h) f.append($("div", "hint", q.h));
  }
  return f;
}

function summary() {
  let s = "NO LIMIT FITNESS – CLIENT QUESTIONNAIRE\n";
  S.forEach(x => {
    s += "\n== " + x.t.toUpperCase() + " ==\n";
    x.q.forEach(q => { let v = A[q.id]; if (Array.isArray(v)) v = v.join(", "); s += q.l + ": " + (v || "—") + "\n"; });
  });
  return s;
}

function go(n) { step = n; render(); window.scrollTo(0, 0); }

function next() {
  const miss = S[step].q.filter(q => q.r && empty(q));
  document.querySelectorAll(".msg").forEach(m => m.remove());
  document.querySelectorAll(".err").forEach(e => e.classList.remove("err"));
  if (miss.length) {
    miss.forEach(q => { const f = document.getElementById("f-" + q.id); f.classList.add("err"); f.append($("div", "msg", "Required")); });
    document.getElementById("f-" + miss[0].id).scrollIntoView({ block: "center" });
    return;
  }
  go(step + 1);
}

function render() {
  const app = document.getElementById("app"); app.textContent = "";
  const progressPercent = ((step + 1) / (S.length + 1) * 100);
  document.getElementById("bar").style.width = progressPercent + "%";
  document.getElementById("step-indicator").textContent = `Step ${step + 1} of ${S.length}`;
  
  const nav = $("div", "nav");
  if (step < S.length) {
    const s = S[step];
    app.append($("h2", null, s.t), $("p", "note", s.n));
    s.q.forEach(q => app.append(field(q)));
    if (step > 0) {
      const b = $("button", "btn", "Back"); b.type = "button"; b.onclick = () => go(step - 1); nav.append(b);
    }
    const n = $("button", "btn p", step === S.length - 1 ? "Review" : "Next"); n.type = "button"; n.onclick = next; nav.append(n);
    app.append(nav);
  } else {
    app.append($("h2", null, "Review & Send"), $("p", "note", "Tap the green button to send your answers on WhatsApp, then attach your front, side and back starting photos in the same chat."));
    const t = $("textarea", "sum"); t.readOnly = true; t.value = summary(); app.append(t);
    const msg = $("div", "hint", ""); msg.style.margin = "10px 0"; app.append(msg);
    
    const b = $("button", "btn", "Back"); b.type = "button"; b.onclick = () => go(step - 1);
    const c = $("button", "btn p", "Copy answers"); c.type = "button";
    c.onclick = async () => {
      try {
        await navigator.clipboard.writeText(t.value);
        msg.textContent = "Copied ✓ Paste it into a message to your coach.";
      } catch (e) {
        t.focus(); t.select();
        try { document.execCommand("copy"); msg.textContent = "Copied ✓ Paste it into a message to your coach."; }
        catch (e2) { msg.textContent = "Select the text above and copy it manually."; }
      }
    };
    
    const w = $("a", "btn p", "Send to my coach on WhatsApp");
    w.href = "https://wa.me/YOUR_PHONE_NUMBER?text=" + encodeURIComponent(t.value);
    w.target = "_blank"; w.rel = "noopener";
    w.style.cssText = "display:flex; text-align:center; text-decoration:none; margin-bottom:10px; background:#25D366; color:#111; border:0;";
    
    app.append(w); c.className = "btn";
    nav.append(b, c); app.append(nav);
    
    if (navigator.share) {
      const sh = $("button", "btn", "Share questionnaire"); sh.type = "button";
      sh.style.marginTop = "10px"; sh.style.width = "100%";
      sh.onclick = () => { navigator.share({ title: "My NLF Questionnaire", text: t.value }).catch(() => {}); };
      app.append(sh);
    }
    
    const r = $("button", "btn", "Start over"); r.type = "button";
    r.style.cssText = "margin-top:10px; width:100%; border-color:var(--line); color:var(--mut);";
    r.onclick = () => { A = {}; try { localStorage.removeItem("nlf-intake"); } catch (e) {} go(0); };
    app.append(r);
  }
}

// Toggle Views between Link Hub and Questionnaire
const hubView = document.getElementById("hub-view");
const questionnaireContainer = document.getElementById("questionnaire-container");

document.getElementById("open-quiz-btn").onclick = () => {
  hubView.style.display = "none";
  questionnaireContainer.style.display = "block";
  render();
  window.scrollTo(0, 0);
};

document.getElementById("back-to-hub-btn").onclick = () => {
  questionnaireContainer.style.display = "none";
  hubView.style.display = "block";
  window.scrollTo(0, 0);
};
</script>
</body>
</html>
