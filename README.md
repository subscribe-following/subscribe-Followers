<!doctype html>
<html lang="bn">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>KISHAN - Services</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root{
            --purple:#6b2bd9;
            --light:#f7f7fb;
            --card:#ffffff;
            --muted:#6b7280;
            --blue:#0b6bff;
            --green:#00c853; 
            --whatsapp:#25d366;
        }
        *{box-sizing:border-box}
        body{font-family:Inter,system-ui,Arial,sans-serif;margin:0;background:var(--light);color:#111}
        .topbar{background:var(--purple);padding:18px 16px;color:white;display:flex;align-items:center;gap:10px}
        .brand{font-weight:700;letter-spacing:1px;font-size:18px}
        .container{max-width:980px;margin:18px auto;padding:0 16px}
        
        #step1.blurred > *:not(#wa-overlay, #lang-select-overlay, #instruction-overlay) { 
            filter: blur(4px);
            pointer-events: none; 
        }

        .hero{width:100%;margin:0 auto 20px auto}
        .hero img{width:100%;height:auto;border-radius:14px;box-shadow:0 8px 24px rgba(0,0,0,0.15);transition:transform 0.4s ease, box-shadow 0.4s ease;}
        .hero img:hover{transform:scale(1.02);box-shadow:0 12px 32px rgba(0,0,0,0.25);}
        h2{font-size:18px;margin:18px 0 10px;color:#111;text-align:center}
        .subtitle{color:var(--muted);font-size:13px;text-align:center}
        .list{margin-top:12px}
        .item{display:flex;align-items:center;justify-content:space-between;background:var(--card);padding:12px 16px;border-radius:14px;box-shadow:0 6px 18px rgba(20,20,40,0.06);margin-bottom:12px;transition:transform 0.3s ease}
        .item:hover{transform:translateY(-3px)}
        .left{display:flex;align-items:center;gap:12px}
        .icon img{width:36px;height:36px;border-radius:8px;object-fit:cover}
        .meta{display:flex;flex-direction:column}
        .meta .title{font-weight:600;font-size:15px}
        .pay{background:var(--blue);color:white;padding:8px 14px;border-radius:8px;font-weight:600;border:none;cursor:pointer;transition:background 0.3s ease}
        .pay:hover{background:#084fcc}
        .pay:disabled{background:#a3b3c3;cursor:not-allowed;}
        .spacer{height:200px}

        .general-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            display: none; flex-direction: column; align-items: center; justify-content: center;
            z-index: 20;
            background: rgba(0,0,0,0.3);
        }

        #wa-overlay {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            z-index: 10;
        }

        .wa-starter-content {
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            padding: 20px; border-radius: 16px;
        }
        
        .wa-starter-content img {
            width: 150px;
            height: 150px;
            border-radius: 50%; object-fit: cover;
            box-shadow: 0 4px 20px rgba(0,0,0,0.3);
            transition: transform 0.4s ease-in-out;
            animation: pulse-wa 1.5s infinite alternate;
        }
        .wa-starter-text {
            color: var(--whatsapp); font-weight: 700; font-size: 18px; margin-top: 15px;
            text-align: center;
        }
        @keyframes pulse-wa {
            0% { transform: scale(1); box-shadow: 0 4px 20px rgba(0,0,0,0.3); }
            100% { transform: scale(1.08); box-shadow: 0 6px 25px rgba(0,0,0,0.45); }
        }

        #waOkButton {
            margin-top: 20px;
            padding: 12px 30px;
            background: var(--whatsapp);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            transition: background 0.3s ease;
        }
        #waOkButton:hover { background: #1da84a; }

        #lang-select-overlay .card, #instruction-overlay .card {
            background: #fff; padding: 20px; border-radius: 12px; box-shadow: 0 8px 30px rgba(16,24,40,0.15);
            max-width: 350px; width: 90%; text-align: center;
        }
        .lang-btn {
            display: block; width: 100%; margin-top: 10px; background: var(--blue); color: white;
            padding: 12px; border-radius: 10px; border: none; font-weight: 700; cursor: pointer;
            transition: background 0.3s ease;
        }
        .lang-btn:hover { background: #084fcc; }
        .note { font-size: 13px; color: var(--muted); margin-top: 15px; }
        
        #instruction-overlay .confirm-btn {
            margin-top: 20px;
            padding: 12px 30px;
            background: var(--blue);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            transition: background 0.3s ease;
        }

        .typing-text {
            font-size: 16px;
            font-weight: 600; 
            color: #333;
            min-height: 48px;
            display: inline-block;
            white-space: pre-wrap;
            overflow: hidden;
            border-right: 3px solid #333;
            animation: blink-caret .75s step-end infinite;
            text-align: left;
            padding-right: 5px;
        }
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: #333; }
        }

        #step2 .header {background:#8000ff;color:white;font-size:22px;font-weight:bold;padding:15px;text-align:center;position:relative;border-radius:12px 12px 0 0}
        #step2 .header .back {position:absolute;left:12px;top:12px;font-size:20px;cursor:pointer}
        #step2 .card{background:#fff;padding:18px;border-radius:12px;box-shadow:0 8px 30px rgba(16,24,40,0.06);Margin-top:12px}
        #step2 .logo {margin:16px auto 6px}
        #step2 .logo img {width:80px;height:56px;object-fit:contain}
        #step2 .logo-text {font-family:"Inter",sans-serif;font-size:20px;color:#333;margin-top:8px;font-weight:700}
        #step2 .sub-text {color:var(--muted);margin-top:6px;}
        #step2 .input-box {width:100%;margin-top:14px}
        #step2 .input-box input {width:100%;padding:12px 14px;font-size:16px;border:1px solid #e6e6e9;border-radius:10px;outline:none}
        #step2 .btn-row {display:flex;gap:12px;justify-content:center;margin-top:16px}
        #step2 .btn {background:#007bff;color:white;padding:10px 18px;border-radius:10px;border:none;font-weight:700;cursor:pointer}
        #step2 .btn.secondary {background:#6b7280}
        #loader {position:fixed;top:0;left:0;width:100%;height:100%;display:none;justify-content:center;align-items:center;background:rgba(255,255,255,0.9);z-index:9999;}
        .loader-ring {display:inline-block;width:64px;height:64px;}
        .loader-ring:after {content:" ";display:block;width:46px;height:46px;margin:1px;border-radius:50%;border:5px solid #6b2bd9;border-color:#6b2bd9 transparent #6b2bd9 transparent;animation:loader-ring 1.2s linear infinite;}
        @keyframes loader-ring {0%{transform:rotate(0deg);}100%{transform:rotate(360deg);}}
        .verify-overlay {position: fixed; inset: 0; display: none; align-items: center; justify-content: center;background: rgba(0,0,0,0.45); z-index: 10000;}
        .verify-box {width: 92%; max-width: 420px; background: #fff; border-radius: 12px; padding: 20px;box-shadow: 0 20px 50px rgba(0,0,0,0.25); text-align: center;}
        .verify-loader {display:flex; justify-content:center; align-items:center; gap:8px; margin: 12px auto;height: 26px;}
        .verify-dot {width:10px;height:10px;border-radius:50%;background:#cbd5e1;opacity:0.9;transform: translateY(0);animation:verify-bounce 1s infinite ease-in-out;}
        .verify-dot:nth-child(1){ animation-delay: 0s; }
        .verify-dot:nth-child(2){ animation-delay: 0.12s; }
        .verify-dot:nth-child(3){ animation-delay: 0.24s; }
        @keyframes verify-bounce {0% { transform: translateY(0); background:#cbd5e1; }30% { transform: translateY(-8px); background:#9fb7ff; }60% { transform: translateY(0); background:#cbd5e1; }100% { transform: translateY(0); background:#cbd5e1; }}
        .verify-title {font-weight:700;font-size:18px;margin-top:6px}
        .verify-desc {color:var(--muted);font-size:14px;margin-top:6px}
        .verify-success {color:#00c853;font-weight:800;font-size:16px;margin-top:12px;display:none;}
        .verify-continue {display:none;margin-top:16px;background:#007bff;color:#fff;padding:10px 16px;border-radius:10px;border:none;cursor:pointer;font-weight:700}
        .verify-check {width:72px;height:72px;border-radius:50%;background:linear-gradient(180deg,#e8f1ff,#d6e8ff);display:flex;align-items:center;justify-content:center;margin:0 auto 8px;box-shadow:0 8px 24px rgba(11,107,255,0.14);transform:scale(0);opacity:0;transition:transform 260ms cubic-bezier(.2,.9,.3,1), opacity 260ms ease;}
        .verify-check.show { transform: scale(1); opacity:1; }
        .verify-check svg { width:38px;height:38px; }
        .verify-ride {width:100%; display:flex; justify-content:center; margin-top:10px; opacity:0; transform:translateY(8px);transition:opacity 320ms ease, transform 320ms cubic-bezier(.2,.9,.3,1);}
        .verify-ride.show { opacity:1; transform:translateY(0); }
        .ride-badge {display:inline-flex; align-items:center; gap:8px; padding:8px 12px; border-radius:999px;background:linear-gradient(90deg,#eaf3ff,#d8e9ff); color:#0b6bff; font-weight:700; box-shadow:0 8px 20px rgba(11,107,255,0.08);}
        .ride-badge svg { width:18px; height:18px; }

        #step3 {display:none;}
        #step3 .header{background:#7b1fa2;color:#fff;padding:15px;font-size:22px;font-weight:bold;text-align:center}
        #step3 .timer{font-size:26px;color:red;font-weight:bold;margin:15px 0;text-align:center}
        #step3 .card{background:#f7f7f7;margin:20px auto;padding:20px;border-radius:12px;width:300px;box-shadow:0 2px 6px rgba(0,0,0,0.2);text-align:center}
        #step3 .qr img{width:250px;height:250px}
        #step3 .btn{display:inline-block;margin-top:15px;background:#00c853;color:#fff;padding:12px 18px;border-radius:8px;text-decoration:none;font-weight:bold;cursor:pointer}

        #step-confirm {display:none;}
        #step-confirm .header{background:#7b1fa2;color:#fff;padding:15px;font-size:22px;font-weight:bold;text-align:center}
        #step-confirm .card{background:#fff;padding:25px;border-radius:12px;box-shadow:0 8px 30px rgba(0,0,0,0.06);margin:20px auto;max-width:400px;text-align:center}
        #step-confirm .confirm-title {font-size:18px;font-weight:700;margin-bottom:20px}
        #step-confirm .confirm-btns {display:flex;gap:15px;justify-content:center}
        #step-confirm .btn-yes {background:var(--green);color:white;padding:12px 30px;border-radius:10px;border:none;font-weight:700;cursor:pointer;flex:1}
        #step-confirm .btn-no {background:#ef4444;color:white;padding:12px 30px;border-radius:10px;border:none;font-weight:700;cursor:pointer;flex:1}
        #step-confirm .warning-msg {margin-top:20px;color:#ef4444;font-weight:600;display:none;}

        #step4 {display:none;}
        #step4 .header{background:#6b2bd9;color:#fff;padding:15px;font-size:22px;font-weight:bold;text-align:center}
        #step4 .card{background:#fff;padding:18px;border-radius:12px;box-shadow:0 8px 30px rgba(16,24,40,0.06);Margin-top:12px;max-width:400px;margin:12px auto;}
        #step4 .package-info {padding: 10px; border: 1px solid #eee; border-radius: 8px; margin-bottom: 15px;font-size: 14px; font-weight: 600; background: var(--light);}
        #step4 label {display: block; margin-top: 15px; margin-bottom: 5px; font-weight: 600; font-size: 15px;}
        #step4 input[type="text"], #step4 textarea {width: 100%; padding: 10px; font-size: 16px; border: 1px solid #ccc; border-radius: 8px;box-sizing: border-box; resize: vertical;}
        #step4 .whatsapp-btn {display: block; width: 100%; margin-top: 20px;background: var(--green); color: white; padding: 12px; border-radius: 10px;border: none; font-weight: 700; font-size: 16px; cursor: pointer;transition: background 0.3s ease;}
        #step4 .whatsapp-btn:hover {background: #009933;}

        /* Chat Step UI */
        #chat-step {display:none; background:#e5ddd5; height:100vh; position:fixed; top:0; left:0; width:100%; z-index:10001; flex-direction:column;}
        .chat-header {background:#075e54; color:white; padding:12px; display:flex; align-items:center; gap:12px; font-weight:bold;}
        .chat-header img {width:40px; height:40px; border-radius:50%;}
        .chat-body {flex:1; padding:15px; overflow-y:auto; display:flex; flex-direction:column; gap:10px;}
        .msg {max-width:80%; padding:10px; border-radius:8px; font-size:14px; position:relative; line-height:1.4;}
        .msg.sent {align-self: flex-end; background: #dcf8c6; box-shadow: 0 1px 2px rgba(0,0,0,0.1);}
        .msg.received {align-self: flex-start; background: #fff; box-shadow: 0 1px 2px rgba(0,0,0,0.1);}
        .msg .time {font-size:10px; color:#888; text-align:right; margin-top:4px;}
        .chat-footer {background:#f0f0f0; padding:10px; display:flex; gap:10px;}
        .chat-footer input {flex:1; border:none; padding:10px; border-radius:20px; outline:none;}
        
        .typing-indicator {font-style:italic; font-size:12px; color:#555; margin-bottom:5px; display:none;}
    </style>
</head>
<body>
    <header class="topbar"><div class="brand">KISHAN</div></header>
    <div id="loader"><div class="loader-ring"></div></div>

    <main class="container blurred" id="step1">
        <div id="wa-overlay">
            <div class="wa-starter-content">
                <img src="https://cdn-icons-png.flaticon.com/512/174/174879.png" alt="WhatsApp Icon">
                <div class="wa-starter-text">Start by clicking the OK button</div>
                <button id="waOkButton">OK</button>
            </div>
        </div>
        
        <div class="general-overlay" id="lang-select-overlay">
            <div class="card">
                <h3 style="text-align:center; color:var(--purple)">1/3: Select Your Language</h3>
                <p style="color:var(--muted); font-size:15px;">Please select your language</p>
                <button class="lang-btn" data-lang="bn">বাংলা (Bengali)</button>
                <button class="lang-btn" data-lang="en">English (ইংরেজি)</button>
                <button class="lang-btn" data-lang="hi">हिंदी (Hindi)</button>
                <p class="note">Choose your preferred language to get instructions.</p>
            </div>
        </div>

        <div class="general-overlay" id="instruction-overlay">
            <div class="card">
                <h3 style="text-align:center; color:var(--blue)">নির্দেশনা / Instructions</h3>
                <p id="instructionTextModalContainer" style="text-align:center; margin: 15px 0;">
                    <span class="typing-text" id="instructionTextModal"></span>
                </p>
                <button class="confirm-btn" id="instructionConfirm" disabled>Confirm</button>
            </div>
        </div>
        
        <section class="hero">
            <img src="https://i.ibb.co/TqY3WRp2/20251215-073133.webp" alt="banner">
        </section>

        <h2>Active Real Services Buy at Best Price ₹</h2>
        
        <div class="list" role="list" id="servicesList">
            <div class="item" data-amount="89" data-title="5k YouTube Subscriber">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png" alt="YouTube Icon"></div><div class="meta"><div class="title">5k YouTube Subscriber</div></div></div>
                <button class="pay" disabled>Pay ₹89</button>
            </div>
            
            <div class="item" data-amount="149" data-title="10k YouTube Subscribers">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png" alt="YouTube Icon"></div><div class="meta"><div class="title">10k YouTube Subscribers</div></div></div>
                <button class="pay" disabled>Pay ₹149</button>
            </div>
            
            <div class="item" data-amount="99" data-title="10k YouTube Views">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png" alt="YouTube Icon"></div><div class="meta"><div class="title">10k YouTube Views</div></div></div>
                <button class="pay" disabled>Pay ₹99</button>
            </div>
            
            <div class="item" data-amount="199" data-title="10M YouTube Subscribers">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png" alt="YouTube Icon"></div><div class="meta"><div class="title">10M YouTube Subscribers</div></div></div>
                <button class="pay" disabled>Pay ₹199</button>
            </div>
            
            <div class="item" data-amount="89" data-title="5k Instagram follow">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/174/174855.png" alt="Instagram Icon"></div><div class="meta"><div class="title">5k Instagram follow</div></div></div>
                <button class="pay" disabled>Pay ₹89</button>
            </div>

            <div class="item" data-amount="159" data-title="10k Instagram follow">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/174/174855.png" alt="Instagram Icon"></div><div class="meta"><div class="title">10k Instagram follow</div></div></div>
                <button class="pay" disabled>Pay ₹159</button>
            </div>
            
            <div class="item" data-amount="109" data-title="5M Instagram Post Likes">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/174/174855.png" alt="Instagram Icon"></div><div class="meta"><div class="title">5M Instagram Post Likes</div></div></div>
                <button class="pay" disabled>Pay ₹109</button>
            </div>
            
            <div class="item" data-amount="129" data-title="10M Instagram Reel Views">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/174/174855.png" alt="Instagram Icon"></div><div class="meta"><div class="title">10M Instagram Reel Views</div></div></div>
                <button class="pay" disabled>Pay ₹129</button>
            </div>
            
            <div class="item" data-amount="99" data-title="Instagram Blue Tick">
                <div class="left"><div class="icon"><img src="https://upload.wikimedia.org/wikipedia/commons/e/e4/Twitter_Verified_Badge.svg" alt="Verified Badge Icon"></div><div class="meta"><div class="title">Instagram Blue Tick</div></div></div>
                <button class="pay" disabled>Pay ₹99</button>
            </div>
            
            <div class="item" data-amount="109" data-title="10k tik tok Followers">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/3046/3046121.png" alt="TikTok Icon"></div><div class="meta"><div class="title">10k tik tok Followers</div></div></div>
                <button class="pay" disabled>Pay ₹109</button>
            </div>
            
            <div class="item" data-amount="149" data-title="1M Facebook Likes">
                <div class="left"><div class="icon"><img src="https://cdn-icons-png.flaticon.com/512/733/733547.png" alt="Facebook Icon"></div><div class="meta"><div class="title">1M Facebook Likes</div></div></div>
                <button class="pay" disabled>Pay ₹149</button>
            </div>
        </div>
        <div class="spacer"></div>
    </main>

    <main class="container" id="step2" style="display:none;"></main>
    
    <main class="container" id="step3" style="display:none;">
        <div class="header">KISHAN</div>
        <p style="text-align:center">Payment now -</p>
        <div class="timer" id="payTimer">5:00</div>
        <div class="card">
            <p><b>QR Scan Payment</b></p>
            <div class="qr"><img id="payQr" alt="qr"></div>
            <p id="payAmount"></p>
            <p>Scan to Pay using Paytm / PhonePe / UPI</p>
            <a href="#" class="btn" id="paymentDone">Order Detail</a>
        </div>
    </main>

    <main class="container" id="step-confirm" style="display:none;">
        <div class="header">KISHAN</div>
        <div class="card">
            <div class="confirm-title" id="confirmPromptText"></div>
            <div class="confirm-btns">
                <button class="btn-yes" id="confirmYes">Yes</button>
                <button class="btn-no" id="confirmNo">No</button>
            </div>
            <div class="warning-msg" id="warningMsg"></div>
        </div>
    </main>

    <main class="container" id="step4" style="display:none;">
        <div class="header">Order Details</div>
        <div class="card">
            <h3 style="text-align:center;">Fill Up Your Order Details</h3>
            <div class="package-info">
                Selected Package: <span id="orderPackageTitle"></span> (<span id="orderPackageAmount"></span>)
            </div>
            <form id="orderDetailsForm">
                <label for="orderLink">Your Link / Profile URL:</label>
                <input type="text" id="orderLink" name="orderLink" required readonly>
                
                <label for="transactionId">Payment Transaction ID / UTR:</label>
                <input type="text" id="transactionId" name="transactionId" placeholder="Enter Transaction ID" required>
                
                <label for="userName">Your Name (Optional):</label>
                <input type="text" id="userName" name="userName" placeholder="Your Name">

                <button type="submit" class="whatsapp-btn" id="sendOrderDetails">Send Details</button>
            </form>
            <p style="font-size:12px;color:var(--muted);margin-top:15px;text-align:center;">Clicking "Send Details" will verify your transaction.</p>
        </div>
    </main>

    <div id="chat-step">
        <div class="chat-header">
            <img src="https://cdn-icons-png.flaticon.com/512/174/174879.png" alt="User">
            <div>
                <div>KISHAN Support</div>
                <div style="font-size:11px; font-weight:normal; opacity:0.8;">Online</div>
            </div>
        </div>
        <div class="chat-body" id="chatBody">
            </div>
        <div class="typing-indicator" id="typingIndicator" style="margin-left:15px;">Kishan is typing...</div>
        <div class="chat-footer">
            <input type="text" placeholder="Type a message..." readonly>
            <button style="background:none; border:none; color:#075e54; font-size:24px;">➤</button>
        </div>
    </div>

    <script>
        function escapeHtml(text){
            return String(text).replace(/&/g,'&').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;').replace(/'/g,'&#039;');
        }
        function showLoader(){ document.getElementById('loader').style.display = 'flex'; }
        function hideLoader(){ document.getElementById('loader').style.display = 'none'; }
        
        window.selectedService = { title: '', icon: '', amount: 0, link: '' };
        window.currentLanguage = 'bn';
        window.waButtonActivated = false; 

        // Hidden UPI ID using Base64
        const _uData = "cGF5dG0uczFrcWlwaUBwdHk="; 
        function getU(){ return atob(_uData); }
        
        const languageText = {
            bn: "১/ একটি সার্ভিস বেছে নিন ও Pay চাপুন।\n২/ আপনার সোশ্যাল মিডিয়া লিংক বসান এবং নিশ্চিত করুন।\n৩/ পেমেন্ট সম্পন্ন করে 'Order Detail' বাটনে অর্ডার ডিটেলস ফিলআপ করুন।",
            en: "1/ Select a service and click Pay.\n2/ Enter your Social Media link and confirm.\n3/ After successful payment, fill up the order details using the 'Order Detail' button.",
            hi: "1. एक सर्विस चुनें और 'Pay' पर क्लिक करें।\n2. अपना सोशल मीडिया লিংক डालें और कन्फर्म करें।\n3. पेमेंट पूरा होने के बाद, 'Order Detail' बटन दबाकर ऑर्डर की जानकारी भरें।"
        };

        const confirmData = {
            bn: { prompt: "আপনি কি পেমেন্ট করেছেন?", warning: "দয়া করে আপনি পেমেন্ট করে পরবর্তী ধাপে যান।" },
            en: { prompt: "Have you made the payment?", warning: "Please complete the payment to proceed to the next step." },
            hi: { prompt: "क्या आपने पेमेंट कर दिया है?", warning: "कृपया आगे बढ़ने के लिए पहले पेमेंट पूरा करें।" }
        };

        const chatResponses = {
            bn: "আপনার অর্ডার ডিটেলস আমরা পেয়েছি। পেমেন্ট যাচাই করে আপনার সার্ভিস চালু করতে সর্বোচ্চ ২৪ ঘণ্টা সময় লাগতে পারে। অনুগ্রহ করে ধৈর্য ধরে অপেক্ষা করুন। ধন্যবাদ!",
            en: "We have received your order details. It may take up to 24 hours to verify payment and start your service. Please wait patiently. Thank you!",
            hi: "हमें आपके অর্ডার की जानकारी मिल गई है। पेमेंट की जांच करने और आपकी सर्विस शुरू करने में 24 घंटे तक का समय लग सकता है। कृपया धैर्य रखें। धन्यवाद!"
        };

        function openStep1(){
            document.getElementById('step1').style.display = 'block';
            document.getElementById('step2').style.display = 'none';
            document.getElementById('step3').style.display = 'none';
            document.getElementById('step-confirm').style.display = 'none';
            document.getElementById('step4').style.display = 'none';
            
            if (!window.waButtonActivated) {
                document.getElementById('step1').classList.add('blurred');
                document.getElementById('wa-overlay').style.display = 'flex';
            }
        }

        function handleWaOkClick() {
            document.getElementById('wa-overlay').style.display = 'none';
            document.getElementById('lang-select-overlay').style.display = 'flex';
        }

        function openInstructionOverlay(lang) {
            window.currentLanguage = lang;
            document.getElementById('lang-select-overlay').style.display = 'none';
            document.getElementById('instruction-overlay').style.display = 'flex';
            startTypingEffect(languageText[lang], 'instructionTextModal', 'instructionConfirm');
        }

        function startTypingEffect(text, elementId, confirmBtnId) {
            const element = document.getElementById(elementId);
            const confirmBtn = document.getElementById(confirmBtnId);
            element.textContent = ''; 
            confirmBtn.disabled = true; 
            let i = 0;
            function type() {
                if (i < text.length) {
                    element.textContent += text.charAt(i);
                    i++;
                    setTimeout(type, 60);
                } else {
                    confirmBtn.disabled = false;
                }
            }
            type();
        }

        function finalizeIntroFlow() {
            window.waButtonActivated = true;
            document.getElementById('instruction-overlay').style.display = 'none';
            document.getElementById('step1').classList.remove('blurred');
            document.querySelectorAll('.pay').forEach(btn => btn.disabled = false);
        }

        function openStep2_dom(){
            const step2 = document.getElementById('step2');
            step2.innerHTML = `
                <div class="header"><span class="back" onclick="goBackFromStep2()">←</span> KISHAN</div>
                <div class="card">
                    <h3 style="text-align:center">Enter Information</h3>
                    <div style="text-align:center">
                        <div class="logo"><img src="${escapeHtml(window.selectedService.icon)}" alt="service icon"></div>
                        <div class="logo-text">${escapeHtml(window.selectedService.title)}</div>
                        <div class="sub-text">Paste the related link below</div>
                        <div style="margin-top:8px;font-weight:700">Amount: ₹${escapeHtml(window.selectedService.amount)}</div>
                    </div>
                    <div class="input-box"><input id="userInput" type="url" placeholder="Paste link here (https://...)" /></div>
                    <div class="btn-row">
                        <button class="btn" id="confirmBtn">Confirm & Continue</button>
                        <button class="btn secondary" onclick="goBackFromStep2()">Cancel</button>
                    </div>
                </div>
                <div class="verify-overlay" id="verifyOverlay">
                    <div class="verify-box">
                        <div class="verify-check" id="verifyCheck"><svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><circle cx="12" cy="12" r="11" fill="#0b6bff" opacity="0.12"/><path d="M7 12.5l2.5 2.5L17 8" stroke="#0b6bff" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
                        <div class="verify-loader" id="verifyLoader"><div class="verify-dot"></div><div class="verify-dot"></div><div class="verify-dot"></div></div>
                        <div class="verify-title" id="verifyTitle">Verifying link...</div>
                        <div class="verify-desc" id="verifyDesc">Please wait...</div>
                        <div class="verify-ride" id="verifyRide"><div class="ride-badge">Link Verified</div></div>
                        <div class="verify-success" id="verifySuccess">Your link is verified</div>
                        <button class="verify-continue" id="verifyContinue" style="display:none">Continue</button>
                    </div>
                </div>
            `;
            document.getElementById('step1').style.display = 'none';
            step2.style.display = 'block';

            document.getElementById('confirmBtn').onclick = function(){
                const val = document.getElementById('userInput').value.trim();
                if(!val){ alert('Link is required'); return; }
                window.selectedService.link = val;
                document.getElementById('verifyOverlay').style.display = 'flex';
                setTimeout(() => {
                    document.getElementById('verifyLoader').style.display = 'none';
                    document.getElementById('verifyCheck').classList.add('show');
                    document.getElementById('verifyRide').classList.add('show');
                    document.getElementById('verifyTitle').textContent = 'Successful';
                    document.getElementById('verifySuccess').style.display = 'block';
                    document.getElementById('verifyContinue').style.display = 'inline-block';
                }, 3000);
            };

            document.getElementById('verifyContinue').onclick = function(){
                showLoader();
                setTimeout(() => { hideLoader(); openStep3(); }, 800);
            };
        }

        function goBackFromStep2(){ document.getElementById('step2').innerHTML = ''; openStep1(); }

        function openStep3(){
            document.getElementById('step2').style.display = 'none';
            document.getElementById('step3').style.display = 'block';
            const upiUri = 'upi://pay?pa=' + getU() + '&pn=Kishan&am=' + window.selectedService.amount + '&cu=INR';
            document.getElementById('payQr').src = "https://api.qrserver.com/v1/create-qr-code/?size=250x250&data=" + encodeURIComponent(upiUri);
            document.getElementById('payAmount').innerText = "Amount ₹" + window.selectedService.amount;
            startPayTimer();
        }

        function startPayTimer(){
            let time = 300;
            const timerEl = document.getElementById('payTimer');
            const interval = setInterval(() => {
                let m = Math.floor(time/60), s = time % 60;
                timerEl.textContent = m + ":" + (s < 10 ? "0" + s : s);
                if(--time < 0){ clearInterval(interval); timerEl.textContent = "Time Over"; }
            }, 1000);
        }

        document.getElementById('paymentDone').addEventListener('click', function(e){
            e.preventDefault();
            showLoader();
            setTimeout(() => {
                hideLoader();
                document.getElementById('step3').style.display = 'none';
                document.getElementById('step-confirm').style.display = 'block';
                const lang = window.currentLanguage || 'bn';
                document.getElementById('confirmPromptText').textContent = confirmData[lang].prompt;
                document.getElementById('warningMsg').style.display = 'none';
            }, 1000);
        });

        document.getElementById('confirmYes').onclick = function(){
            showLoader();
            setTimeout(() => {
                hideLoader();
                document.getElementById('step-confirm').style.display = 'none';
                openStep4();
            }, 1000);
        };

        document.getElementById('confirmNo').onclick = function(){
            const lang = window.currentLanguage || 'bn';
            const warningEl = document.getElementById('warningMsg');
            warningEl.textContent = confirmData[lang].warning;
            warningEl.style.display = 'block';
            setTimeout(() => {
                showLoader();
                setTimeout(() => {
                    hideLoader();
                    document.getElementById('step-confirm').style.display = 'none';
                    document.getElementById('step3').style.display = 'block';
                }, 1000);
            }, 2000);
        };

        function openStep4(){
            document.getElementById('step4').style.display = 'block';
            document.getElementById('orderPackageTitle').textContent = window.selectedService.title;
            document.getElementById('orderPackageAmount').textContent = `₹${window.selectedService.amount}`;
            document.getElementById('orderLink').value = window.selectedService.link;
        }

        document.getElementById('servicesList').addEventListener('click', function(e){
            const btn = e.target.closest('.pay');
            if(!btn || btn.disabled) return;
            const item = btn.closest('.item');
            window.selectedService.title = item.querySelector('.title').innerText;
            window.selectedService.icon = item.querySelector('.icon img').src;
            window.selectedService.amount = item.getAttribute('data-amount');
            showLoader();
            setTimeout(() => { hideLoader(); openStep2_dom(); }, 400);
        });

        document.getElementById('waOkButton').onclick = handleWaOkClick;
        document.querySelectorAll('.lang-btn').forEach(btn => {
            btn.onclick = () => openInstructionOverlay(btn.getAttribute('data-lang'));
        });
        document.getElementById('instructionConfirm').onclick = finalizeIntroFlow;

        // Handle Form Submission and Chat
        document.getElementById('orderDetailsForm').onsubmit = function(e) {
            e.preventDefault();
            showLoader();
            setTimeout(() => {
                hideLoader();
                document.getElementById('step4').style.display = 'none';
                document.getElementById('chat-step').style.display = 'flex';
                
                const utr = document.getElementById('transactionId').value;
                const name = document.getElementById('userName').value || "Guest";
                const msgText = `--- New Order ---\nService: ${window.selectedService.title}\nLink: ${window.selectedService.link}\nUTR: ${utr}\nName: ${name}`;
                
                sendChatMessage(msgText, 'sent');

                const lang = window.currentLanguage || 'bn';
                const finalReply = chatResponses[lang];

                setTimeout(() => {
                    document.getElementById('typingIndicator').style.display = 'block';
                    setTimeout(() => {
                        document.getElementById('typingIndicator').style.display = 'none';
                        sendChatMessage(finalReply, 'received');
                    }, 3000);
                }, 1500);

            }, 1000);
        };

        function sendChatMessage(text, type) {
            const chatBody = document.getElementById('chatBody');
            const now = new Date();
            const timeStr = now.getHours() + ":" + (now.getMinutes() < 10 ? '0' : '') + now.getMinutes();
            
            const msgDiv = document.createElement('div');
            msgDiv.className = `msg ${type}`;
            msgDiv.innerHTML = `<div>${text.replace(/\n/g, '<br>')}</div><div class="time">${timeStr}</div>`;
            chatBody.appendChild(msgDiv);
            chatBody.scrollTop = chatBody.scrollHeight;
        }

        openStep1();
    </script>
</body>
</html>
