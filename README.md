9# student-learning-platform
A premium student learning platform offering free trials, user authentication, and subscription-based access to educational resources.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#0b1020">
<title>LearnMate AI — Learn beyond limits</title>
<style>
:root{--bg:#0b1020;--panel:#121a2e;--panel2:#17223a;--blue:#648cff;--gold:#e7c98a;--ivory:#f5f1e8;--muted:#aab4c8;--line:#2a3650}
*{box-sizing:border-box}body{margin:0;background:radial-gradient(circle at 80% 0%,#1b2b52 0,transparent 32%),var(--bg);color:var(--ivory);font-family:Inter,system-ui,-apple-system,Segoe UI,sans-serif;line-height:1.55}
a{color:inherit;text-decoration:none}.wrap{width:min(1100px,92%);margin:auto}
nav{display:flex;align-items:center;justify-content:space-between;padding:20px 0;border-bottom:1px solid #ffffff12}
.brand{font-size:1.2rem;font-weight:800;letter-spacing:.2px}.brand span{color:var(--gold)}
.navlinks{display:flex;gap:22px;color:var(--muted);font-size:.92rem}
.btn{display:inline-flex;align-items:center;justify-content:center;border:0;border-radius:12px;padding:12px 18px;font-weight:750;cursor:pointer;background:linear-gradient(135deg,#789aff,#4e70df);color:white;box-shadow:0 8px 24px #5278ed35}
.btn.secondary{background:transparent;border:1px solid #65779b;color:var(--ivory);box-shadow:none}.btn.gold{background:linear-gradient(135deg,#f1d9a6,#c9a65e);color:#171b27}
.hero{padding:78px 0 62px;display:grid;grid-template-columns:1.15fr .85fr;gap:40px;align-items:center}
.eyebrow{color:var(--gold);font-size:.8rem;letter-spacing:2px;text-transform:uppercase;font-weight:800}
h1{font-size:clamp(2.5rem,6vw,4.7rem);line-height:1.04;letter-spacing:-2px;margin:16px 0}
h1 em{font-style:normal;color:var(--gold)}.lead{color:var(--muted);font-size:1.08rem;max-width:580px}
.actions{display:flex;gap:12px;flex-wrap:wrap;margin-top:26px}
.preview{background:linear-gradient(145deg,#1b2946,#11192c);border:1px solid #ffffff1a;border-radius:24px;padding:22px;box-shadow:0 25px 70px #0006}
.preview-top{display:flex;justify-content:space-between;color:var(--muted);font-size:.8rem}.chat{margin-top:22px;display:grid;gap:13px}
.bubble{padding:13px 15px;border-radius:15px;max-width:90%;font-size:.92rem}.question{background:#25365b;margin-left:auto}.answer{background:#202b40;border:1px solid #ffffff12}
.tag{display:inline-block;color:var(--gold);font-size:.75rem;margin-bottom:5px}
section{padding:54px 0}.section-head{text-align:center;max-width:650px;margin:0 auto 30px}.section-head h2{font-size:2rem;margin:8px 0}.section-head p{color:var(--muted)}
.features,.plans{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.tile,.plan{background:linear-gradient(155deg,var(--panel2),var(--panel));border:1px solid var(--line);border-radius:18px;padding:22px}
.tile .ico{font-size:1.5rem}.tile h3,.plan h3{margin:10px 0 5px}.tile p,.plan p,.plan li{color:var(--muted);font-size:.92rem}
.plan{position:relative}.plan.featured{border-color:#d7b976;box-shadow:0 0 0 1px #d7b97622}.price{font-size:2.2rem;font-weight:850;margin:12px 0}.price small{font-size:.85rem;color:var(--muted);font-weight:500}
ul{padding-left:19px;min-height:120px}li{margin:7px 0}.plan .btn{width:100%;margin-top:10px}
.note{background:#201d19;border:1px solid #6d5833;color:#ead6ad;padding:14px 16px;border-radius:13px;font-size:.9rem;margin-top:20px}
footer{border-top:1px solid #ffffff16;padding:25px 0;color:var(--muted);font-size:.85rem}
.modal{display:none;position:fixed;inset:0;background:#050812d9;z-index:5;align-items:center;justify-content:center;padding:18px}.modal.show{display:flex}.dialog{width:min(430px,100%);background:#141e33;border:1px solid #34425f;border-radius:20px;padding:24px;position:relative}.close{position:absolute;right:15px;top:12px;background:none;border:0;color:white;font-size:1.5rem;cursor:pointer}
input{width:100%;padding:13px;margin:7px 0 14px;border:1px solid #3a4968;border-radius:10px;background:#0c1425;color:white;font:inherit}.dialog label{font-size:.88rem;color:var(--muted)}.dialog .btn{width:100%}.small{font-size:.8rem;color:var(--muted)}
#appPanel{display:none;padding:50px 0}.studybox{background:var(--panel);padding:20px;border:1px solid var(--line);border-radius:16px}
textarea{width:100%;min-height:100px;background:#0c1425;color:white;border:1px solid #3a4968;border-radius:12px;padding:13px;font:inherit}
@media(max-width:760px){.hero{grid-template-columns:1fr;padding:55px 0 35px}.features,.plans{grid-template-columns:1fr}.navlinks{display:none}h1{letter-spacing:-1px}.plan ul{min-height:0}}
</style>
</head>
<body>
<div class="wrap">
<nav><a class="brand" href="#"><span>✦</span> LearnMate AI</a><div class="navlinks"><a href="#features">Features</a><a href="#plans">Plans</a><a href="#about">About</a></div><button class="btn secondary" onclick="openAuth()">Sign in</button></nav>
<main id="landing">
<div class="hero">
<div><div class="eyebrow">Your personal AI learning companion</div><h1>Understand more.<br><em>Learn smarter.</em></h1><p class="lead">Ask questions, explore difficult topics and learn step by step with an AI study companion designed around your curiosity.</p><div class="actions"><button class="btn gold" onclick="startFree()">Try for Free&nbsp; →</button><a class="btn secondary" href="#features">Explore features</a></div><p class="small">A student-first learning experience. Start with the free demo.</p></div>
<div class="preview"><div class="preview-top"><span>✦ LEARNMATE TUTOR</span><span>● Demo</span></div><div class="chat"><div class="bubble question">Can you explain Ohm's law simply?</div><div class="bubble answer"><span class="tag">STEP-BY-STEP EXPLANATION</span><br>Ohm's law connects voltage, current and resistance.<br><br><b>V = I × R</b><br><br>Think of voltage as the push, current as the flow, and resistance as what makes the flow harder.</div><div class="bubble question">Give me a quick example.</div><div class="bubble answer">If a 2 Ω resistor has 3 A flowing through it, then V = 3 × 2 = <b>6 V</b>.</div></div></div>
</div>
<section id="features"><div class="section-head"><div class="eyebrow">Built for understanding</div><h2>More than just answers</h2><p>Tools that help students understand the reason behind every answer.</p></div><div class="features">
<div class="tile"><div class="ico">✦</div><h3>Step-by-step tutor</h3><p>Break challenging questions into clear, manageable steps.</p></div>
<div class="tile"><div class="ico">⌕</div><h3>Ask your doubts</h3><p>Type a question and explore concepts at your own pace.</p></div>
<div class="tile"><div class="ico">▤</div><h3>Learning notes</h3><p>Save important explanations and revisit them when studying.</p></div>
<div class="tile"><div class="ico">◷</div><h3>Progress tracking</h3><p>Keep track of topics explored and learning activity.</p></div>
<div class="tile"><div class="ico">◎</div><h3>Multiple explanations</h3><p>Explore simple explanations, examples and practice prompts.</p></div>
<div class="tile"><div class="ico">◇</div><h3>Visual learning</h3><p>Discover diagrams and real-world examples as the product grows.</p></div>
</div></section>
<section id="plans"><div class="section-head"><div class="eyebrow">Simple plans</div><h2>Choose your learning path</h2><p>These are proposed prices for planning. Checkout is not enabled in this demo.</p></div><div class="plans">
<div class="plan"><h3>Basic</h3><p>For everyday doubts</p><div class="price">₹99 <small>/ month · proposed</small></div><ul><li>AI tutor chat</li><li>Step-by-step explanations</li><li>Ask doubts by text</li></ul><button class="btn secondary" onclick="planInfo('Basic')">Choose Basic</button></div>
<div class="plan featured"><div class="eyebrow">Most features</div><h3>Advanced</h3><p>For organised learning</p><div class="price">₹199 <small>/ month · proposed</small></div><ul><li>Everything in Basic</li><li>Saved topic notes</li><li>Learning progress</li></ul><button class="btn gold" onclick="planInfo('Advanced')">Choose Advanced</button></div>
<div class="plan"><h3>Pro</h3><p>For visual exploration</p><div class="price">₹299 <small>/ month · proposed</small></div><ul><li>Everything in Advanced</li><li>Visual explanations</li><li>Real-life examples</li></ul><button class="btn secondary" onclick="planInfo('Pro')">Choose Pro</button></div>
</div><div class="note">Demo notice: subscriptions, AI answers, QR payments and recordings are not active yet. No payment is being collected. We will add secure payment verification before launching paid plans.</div></section>
<section id="about"><div class="section-head"><div class="eyebrow">Start learning</div><h2>Your next question could unlock a new idea.</h2><p>Try the local demo and explore the student workspace.</p><button class="btn gold" onclick="startFree()">Open free demo →</button></div></section>
</main>
<section id="appPanel"><div class="eyebrow">STUDENT WORKSPACE · DEMO</div><h2>Welcome to your learning space</h2><div class="studybox"><h3>Ask a study question</h3><p class="small">This first version demonstrates the interface. It is not connected to an AI model yet.</p><textarea id="demoQuestion" placeholder="Example: Explain Newton's second law with an example..."></textarea><button class="btn" style="margin-top:12px" onclick="demoAsk()">Ask demo tutor</button><div id="demoReply" style="margin-top:16px;color:var(--gold)"></div></div><p><button class="btn secondary" onclick="backHome()">← Back to home</button></p></section>
<footer><div style="display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap"><span>© 2026 LearnMate AI · Early prototype</span><span>Learn with curiosity. Build understanding.</span></div></footer>
</div>
<div class="modal" id="authModal"><div class="dialog"><button class="close" onclick="closeAuth()">×</button><div class="eyebrow">STUDENT ACCESS</div><h2 id="authTitle">Create your demo profile</h2><p class="small">This prototype stores no account credentials and does not provide real Google sign-in yet.</p><label for="studentName">Your first name (optional)</label><input id="studentName" placeholder="Student name"><label for="studentEmail">Email (demo only)</label><input id="studentEmail" type="email" placeholder="you@example.com"><button class="btn gold" onclick="enterDemo()">Continue to free demo</button><p class="small">Do not enter passwords or sensitive personal information in this prototype.</p></div></div>
<script>
function openAuth(){document.getElementById('authModal').classList.add('show')}
function closeAuth(){document.getElementById('authModal').classList.remove('show')}
function startFree(){openAuth()}
function enterDemo(){closeAuth();document.getElementById('landing').style.display='none';document.getElementById('appPanel').style.display='block';window.scrollTo(0,0)}
function backHome(){document.getElementById('appPanel').style.display='none';document.getElementById('landing').style.display='block';window.scrollTo(0,0)}
function planInfo(name){alert(name+' is a proposed plan. Payments are disabled in this prototype.')}
function demoAsk(){let q=document.getElementById('demoQuestion').value.trim();let r=document.getElementById('demoReply');if(!q){r.textContent='Type a question first.';return}r.textContent='Your question has been captured in this demo interface. A secure AI tutor connection will be added in the next development stage.'}
</script>
</body>
</html>

