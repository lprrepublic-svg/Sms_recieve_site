# Sms_recieve_site
Get your virtual number for free 
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Virtual Number Portal</title>
  <style>
    body{
      margin:0;font-family:system-ui,Arial;background:#0b0f14;color:#e6e9ef;
      background-image:url('https://photos.app.goo.gl/YZMVsnKCj9Bs9rcXAbackground-image:url('https://photos.app.goo.gl/YZMVsnKCj9Bs9rcXA.jpg');E.jpg'); /* replace with your photo */
      background-size:cover;background-position:center;background-attachment:fixed;
    }
    .overlay{background:rgba(11,15,20,.85);min-height:100vh}
    .card{max-width:420px;margin:40px auto;padding:20px;border-radius:14px;
      background:rgba(20,25,34,.95);box-shadow:0 10px 30px rgba(0,0,0,.5)}
    h1{font-size:22px;margin:0 0 10px}
    p{opacity:.9}
    button,select,input{width:100%;padding:12px;margin:8px 0;border-radius:10px;
      border:1px solid #2a3242;background:#111827;color:#e6e9ef}
    button{cursor:pointer;background:#2563eb;border:none}
    .ghost{background:#374151}
    .row{display:flex;gap:10px}
    .badge{display:inline-block;padding:6px 10px;border-radius:999px;background:#1f2937;margin:4px 6px 0 0}
    .num{font-weight:700;letter-spacing:.5px}
    .copy{font-size:12px}
    .hidden{display:none}
    .spinner{width:26px;height:26px;border:3px solid #334155;border-top-color:#60a5fa;border-radius:50%;animation:spin 1s linear infinite;margin:10px auto}
    @keyframes spin{to{transform:rotate(360deg)}}
    footer{opacity:.6;text-align:center;margin-top:14px;font-size:12px}
  </style>
</head>
<body>
<div class="overlay">
  <div class="card" id="step1">
    <h1>Sign up</h1>
    <input placeholder="Name" />
    <input placeholder="Email" />
    <button onclick="go(2)">Create account</button>
    <footer>create real account • real OTPs</footer>
  </div>  <div class="card hidden" id="step2">
    <h1>Select country</h1>
    <div>
      <span class="badge">🇬🇭 Ghana</span>
      <span class="badge">🇳🇬 Nigeria</span>
      <span class="badge">🇺🇸 USA</span>
    </div>
    <select id="country">
      <option>Ghana (+233)</option>
      <option>Nigeria (+234)</option>
      <option>USA (+1)</option>
    </select>
    <button onclick="go(3)">Continue</button>
  </div>  <div class="card hidden" id="step3">
    <h1>Available numbers</h1>
    <p class="num" id="num">+233 20 644 8282</p>
    <div class="row">
      <button class="ghost" onclick="copyNum()">Copy</button>
      <button onclick="go(4)">Receive OTP</button>
    </div>
    <p class="copy" id="copy"></p>
  </div>  <div class="card hidden" id="step4">
    <h1>Register with</h1>
    <select>
      <option>WhatsApp</option>
      <option>Telegram</option>
      <option>Instagram</option>
      <option>Gmail</option>
    </select>
    <button onclick="Otp()">Get OTP</button>
    <div id="load" class="hidden"><div class="spinner"></div></div>
    <input id="otp" class="hidden" placeholder="Enter OTP" />
    <button id="verify" class="hidden" onclick="verify()">Verify</button>
  </div>  <div class="card hidden" id="step5">
    <h1>Support</h1>
    <p>Report issue with number:</p>
    <input placeholder="Paste number" />
    <button onclick="reveal()">Submit</button>
    <div id="reveal" class="hidden">
      <h1>😂 PRANK REVEAL</h1>
      <p>This is a harmless demo. No real numbers, no real OTPs.</p>
    </div>
  </div>
</div>
<script>
  const nums=[
    '+233 20 644 8282','+234 80 1234 5678','+1 415 555 0132','+233 50 957 1306'
  ];
  function go(n){
    document.querySelectorAll('.card').forEach(c=>c.classList.add('hidden'));
    document.getElementById('step'+n).classList.remove('hidden');
    if(n===3){document.getElementById('num').textContent=nums[Math.floor(Math.random()*nums.length)];}
  }
  function copyNum(){navigator.clipboard.writeText(document.getElementById('num').textContent);
    document.getElementById('copy').textContent='Copied!';}
  function fakeOtp(){
    document.getElementById('load').classList.remove('hidden');
    setTimeout(()=>{
      document.getElementById('load').classList.add('hidden');
      document.getElementById('otp').classList.remove('hidden');
      document.getElementById('verify').classList.remove('hidden');
    },1500);
  }
  function verify(){go(5)}
  function reveal(){document.getElementById('reveal').classList.remove('hidden')}
</script>
</body>
</html>