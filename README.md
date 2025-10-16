
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>سرور گودرزی - هوش مصنوعی</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* استایل کلی */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            line-height: 1.6;
            padding: 20px;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        /* هدر و تایتل */
        header {
            text-align: center;
            margin-bottom: 40px;
            padding-bottom: 20px;
            border-bottom: 3px solid #4CAF50;
            position: relative;
        }

        .ai-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background: linear-gradient(45deg, #FF6B6B, #FF8E53);
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9em;
            font-weight: bold;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        h1 {
            color: #2c3e50;
            font-size: 2.5em;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }

        h2 {
            color: #34495e;
            font-size: 1.8em;
            margin: 25px 0 15px 0;
            padding-right: 15px;
            border-right: 4px solid #3498db;
        }

        h3 {
            color: #7f8c8d;
            font-size: 1.3em;
            margin: 20px 0 10px 0;
        }

        /* پاراگراف */
        p {
            margin-bottom: 20px;
            font-size: 1.1em;
            text-align: justify;
            padding: 0 10px;
        }

        /* دکمه‌های دانلود */
        .download-section {
            background: #f8f9fa;
            padding: 25px;
            border-radius: 10px;
            margin: 25px 0;
            border-right: 5px solid #e74c3c;
        }

        .download-btn {
            display: inline-block;
            background: linear-gradient(45deg, #4CAF50, #45a049);
            color: white;
            padding: 12px 25px;
            margin: 10px;
            border: none;
            border-radius: 8px;
            text-decoration: none;
            font-size: 1.1em;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .download-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
            background: linear-gradient(45deg, #45a049, #4CAF50);
        }

        /* ساعت و تاریخ */
        .clock-container {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            margin: 25px 0;
            font-size: 1.3em;
            font-weight: bold;
        }

        /* دکمه فول اسکرین */
        .fullscreen-btn {
            background: linear-gradient(45deg, #e74c3c, #c0392b);
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            font-size: 1.1em;
            cursor: pointer;
            margin: 15px 0;
            transition: all 0.3s ease;
        }

        .fullscreen-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        /* بخش برنامه هفتگی */
        .schedule {
            background: #e8f4f8;
            padding: 25px;
            border-radius: 10px;
            margin: 25px 0;
            border: 2px dashed #3498db;
        }

        .schedule h2 {
            color: #2980b9;
            text-align: center;
        }

        .schedule-content {
            background: white;
            padding: 20px;
            border-radius: 8px;
            margin-top: 15px;
            font-family: 'Courier New', monospace;
            font-size: 1.1em;
            line-height: 2;
        }

        /* iframe */
        .video-frame {
            width: 100%;
            height: 400px;
            border: 2px solid #bdc3c7;
            border-radius: 10px;
            margin: 20px 0;
        }

        /* فونت مخصوص متن گودرزی */
        .godarzi-text {
            font-family: 'Courier New', monospace;
            font-size: 1.2em;
            background: #2c3e50;
            color: #ecf0f1;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            margin: 20px 0;
            direction: ltr;
            overflow-x: auto;
        }

        /* کد سورس */
        .code-container {
            background: #1e1e1e;
            color: #d4d4d4;
            padding: 20px;
            border-radius: 10px;
            font-family: 'Courier New', monospace;
            direction: ltr;
            text-align: left;
            position: relative;
            margin: 20px 0;
            overflow-x: auto;
        }
        
        .copy-btn {
            position: absolute;
            top: 10px;
            left: 10px;
            background: #4CAF50;
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
        }
        
        .copy-btn:hover {
            background: #45a049;
        }

        /* بخش چت هوش مصنوعی */
        .ai-chat-container {
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 15px;
            padding: 20px;
            margin: 25px 0;
            color: white;
        }

        .ai-chat-header {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }

        .ai-icon {
            font-size: 2em;
            margin-left: 15px;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }

        .chat-box {
            background: white;
            border-radius: 10px;
            padding: 15px;
            height: 300px;
            overflow-y: auto;
            margin-bottom: 15px;
            direction: rtl;
        }

        .message {
            padding: 10px 15px;
            margin: 10px 0;
            border-radius: 10px;
            max-width: 80%;
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .user-message {
            background: #4CAF50;
            color: white;
            margin-right: auto;
            margin-left: 0;
        }

        .ai-message {
            background: #f1f1f1;
            color: #333;
            margin-left: auto;
            margin-right: 0;
        }

        .chat-input-container {
            display: flex;
            gap: 10px;
        }

        .chat-input {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 8px;
            font-size: 1em;
            direction: rtl;
        }

        .send-btn {
            background: #4CAF50;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .send-btn:hover {
            background: #45a049;
            transform: scale(1.05);
        }

        /* ویژگی‌های هوش مصنوعی */
        .ai-features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 25px 0;
        }

        .ai-feature {
            background: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .ai-feature:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }

        .ai-feature i {
            font-size: 2.5em;
            color: #667eea;
            margin-bottom: 15px;
        }

        /* رسپانسیو */
        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            
            h1 {
                font-size: 2em;
            }
            
            h2 {
                font-size: 1.5em;
            }
            
            .download-btn {
                display: block;
                margin: 10px 0;
            }
            
            .video-frame {
                height: 300px;
            }
            
            .ai-features {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="ai-badge">هوش مصنوعی فعال</div>
            <h1>🚀 به سرور گودرزی خوش آمدید</h1>
            <h2>این سرور تستی با طراحی جدید و زیبا</h2>
            <h3>همراه با دستیار هوش مصنوعی پیشرفته</h3>
        </header>

        <div class="godarzi-text">
            ggggggggggggggggggggooooooooooooooooooodddddddddddddddddddddddddaaaaaaaaaaaaaaaaaaaaaaaaarrrrrrrrrrrrzzzzzzzzzzzzzzzzzzzzzzzziiiiiiiiiiii
        </div>

        <!-- بخش چت هوش مصنوعی -->
        <div class="ai-chat-container">
            <div class="ai-chat-header">
                <i class="ai-icon fas fa-robot"></i>
                <h2>دستیار هوش مصنوعی گودرزی</h2>
            </div>
            <div class="chat-box" id="chat-box">
                <div class="message ai-message">
                    سلام! من دستیار هوش مصنوعی سرور گودرزی هستم. چطور میتونم کمکتون کنم؟
                </div>
            </div>
            <div class="chat-input-container">
                <input type="text" class="chat-input" id="user-input" placeholder="سوال خود را بپرسید...">
                <button class="send-btn" id="send-btn">
                    <i class="fas fa-paper-plane"></i> ارسال
                </button>
            </div>
        </div>

        <!-- ویژگی‌های هوش مصنوعی -->
        <h2>🤖 قابلیت‌های هوش مصنوعی</h2>
        <div class="ai-features">
            <div class="ai-feature">
                <i class="fas fa-comments"></i>
                <h3>پشتیبانی هوشمند</h3>
                <p>پاسخگویی به سوالات و راهنمایی کاربران</p>
            </div>
            <div class="ai-feature">
                <i class="fas fa-graduation-cap"></i>
                <h3>آموزش تعاملی</h3>
                <p>آموزش مفاهیم و پاسخ به سوالات درسی</p>
            </div>
            <div class="ai-feature">
                <i class="fas fa-code"></i>
                <h3>تولید کد</h3>
                <p>کمک در برنامه نویسی و تولید کدهای نمونه</p>
            </div>
            <div class="ai-feature">
                <i class="fas fa-lightbulb"></i>
                <h3>پیشنهاد هوشمند</h3>
                <p>ارائه پیشنهادات بر اساس نیاز کاربر</p>
            </div>
        </div>

        <!-- برنامه هفتگی -->
        <div class="schedule">
            <h2>📅 برنامه هفتگی کلاسی (جدید)</h2>
            <div class="schedule-content">
                شنبه: قرآن / ریاضی / فارسی / ورزش<br>
                یکشنبه: هدیه / ریاضی / فارسی<br>
                دوشنبه: قرآن / ریاضی / فارسی / علوم<br>
                سه‌شنبه: مطالعات / علوم / املا / نگارش<br>
                چهارشنبه: هدیه / ریاضی / مطالعات / هنر
            </div>
        </div>

        <h2>📦 سورس سرور</h2>
        <div class="code-container">
            <button class="copy-btn" onclick="copyCode()">کپی کد</button>
            <pre id="source-code">
// کد سرور گودرزی با هوش مصنوعی
const godarziServer = {
  name: "سرور گودرزی",
  version: "2.0.0",
  status: "فعال",
  features: ["دانلود", "برنامه هفتگی", "ویدیو آموزشی", "هوش مصنوعی"],
  aiEnabled: true,
  
  start: function() {
    console.log("سرور گودرزی با قابلیت هوش مصنوعی راه‌اندازی شد");
    this.initializeAI();
    return "سرور فعال است - هوش مصنوعی آماده";
  },
  
  initializeAI: function() {
    console.log("سیستم هوش مصنوعی بارگذاری شد");
    this.ai = {
      respond: function(message) {
        const responses = {
          "سلام": "سلام! چطور میتونم کمک کنم؟",
          "برنامه": "برنامه هفتگی در بخش مربوطه موجود است",
          "دانلود": "لینک‌های دانلود در پایین صفحه موجودند",
          "کمک": "من اینجام تا کمک کنم! سوال خود را بپرس"
        };
        return responses[message] || "متوجه نشدم. میتونید دقیق‌تر بپرسید؟";
      }
    };
  }
};

// راه‌اندازی سرور
godarziServer.start();
            </pre>
        </div>
        
        <h2>📱 برنامه‌های کاربردی</h2>
        <div class="download-section">
            <a href="https://s6.uplod.ir:182/d/2k2s4kma4hvhuf6to6nyz3jhuufwiaxjvpnnei27kb72zsu3now2rapyggeugyum25zx7llg/Setup.exe" 
               class="download-btn" target="_blank">
               ⬇️ دانلود وین رار - 3.6 مگابایت
            </a>
            
            <a href="https://s6.uplod.ir:182/d/2k2sgkma4hvhuf6to6n5j434wm34hwdaowbvo56qmlhf5eg742mgkr4raw3dlsd4an6zze27/Windows.cmd" 
               class="download-btn" target="_blank">
               ⚡ اکتیو کننده ویندوز - 256 کیلوبایت
            </a>
        </div>

        <!-- ساعت و تاریخ -->
        <div class="clock-container">
            <h2>🕒 ساعت و تاریخ زنده</h2>
            <div id="clock">۱۴۰۴ مهر ۲۰, یکشنبه - ۲۱:۱۵:۱۳</div>
        </div>

        <!-- دکمه فول اسکرین -->
        <button class="fullscreen-btn" onclick="goFullScreen()">
            📺 رفتن به حالت تمام‌صفحه
        </button>

        <h2>📁 مکان فایل</h2>
        <p>file:///C:/Users/mhu6d/Desktop/MY%20COOD/%D8%AA%D8%B3%D8%AA.HTML</p>

        <h2>🎮 تقلب بازی دایناسور</h2>
        <p>برای تقلب کردن ویدیوی زیر رو ببین!</p>
        <iframe class="video-frame" src="هنللت.html" title="ویدیو تقلب بازی دایناسور"></iframe>
        <p>متأسفانه ویدیو کامل نیست</p>

        <h2>🔽 دانلود اپلیکیشن</h2>
        <div class="download-section">
            <a href="https://s6.uplod.ir:182/d/2k2ymima4hvhuf6to6n53il6v3xh25sbiajrgxta3wf5xmybmb3ftwtjhewz6rijbmdaurpl/______.html" 
               class="download-btn" target="_blank">
               📱 دانلود برای اندروید
            </a>
            <a href="https://s6.uplod.ir:182/d/2k2ymima4hvhuf6to6n53il6v3xh25sbiajrgxta3wf5xmybmb3ftwtjhewz6rijbmdaurpl/______.html" 
               class="download-btn" target="_blank">
               🖥️ دانلود برای ویندوز
            </a>
            <a href="https://s6.uplod.ir:182/d/2k2ymima4hvhuf6to6n53il6v3xh25sbiajrgxta3wf5xmybmb3ftwtjhewz6rijbmdaurpl/______.html" 
               class="download-btn" target="_blank">
               🍎 دانلود برای iOS
            </a>
        </div>
    </div>

    <script>
        // ساعت و تاریخ
        function updateClock() {
            const now = new Date();
            const options = { 
                weekday: 'long', 
                year: 'numeric', 
                month: 'long', 
                day: 'numeric' 
            };
            const date = now.toLocaleDateString('fa-IR', options);
            const time = now.toLocaleTimeString('fa-IR');
            document.getElementById('clock').innerHTML = `${date} - ${time}`;
        }

        setInterval(updateClock, 1000);
        updateClock();

        // فول اسکرین
        function goFullScreen() {
            const elem = document.documentElement;
            if (elem.requestFullscreen) {
                elem.requestFullscreen();
            } else if (elem.webkitRequestFullscreen) {
                elem.webkitRequestFullscreen();
            } else if (elem.msRequestFullscreen) {
                elem.msRequestFullscreen();
            }
        }
        
        // کپی کد
        function copyCode() {
            const codeElement = document.getElementById('source-code');
            const textArea = document.createElement('textarea');
            textArea.value = codeElement.textContent;
            document.body.appendChild(textArea);
            textArea.select();
            document.execCommand('copy');
            document.body.removeChild(textArea);
            
            // نمایش پیام موفقیت
            const btn = document.querySelector('.copy-btn');
            const originalText = btn.textContent;
            btn.textContent = 'کپی شد!';
            setTimeout(() => {
                btn.textContent = originalText;
            }, 2000);
        }

        // سیستم چت هوش مصنوعی
        document.getElementById('send-btn').addEventListener('click', sendMessage);
        document.getElementById('user-input').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                sendMessage();
            }
        });

        function sendMessage() {
            const userInput = document.getElementById('user-input');
            const message = userInput.value.trim();
            
            if (message === '') return;
            
            // اضافه کردن پیام کاربر
            addMessage(message, 'user');
            userInput.value = '';
            
            // پاسخ هوش مصنوعی
            setTimeout(() => {
                const aiResponse = generateAIResponse(message);
                addMessage(aiResponse, 'ai');
            }, 1000);
        }

        function addMessage(text, sender) {
            const chatBox = document.getElementById('chat-box');
            const messageDiv = document.createElement('div');
            messageDiv.className = `message ${sender}-message`;
            messageDiv.textContent = text;
            chatBox.appendChild(messageDiv);
            chatBox.scrollTop = chatBox.scrollHeight;
        }

        function generateAIResponse(message) {
            const lowerMessage = message.toLowerCase();
            
            // پاسخ‌های از پیش تعریف شده
            if (lowerMessage.includes('سلام') || lowerMessage.includes('hello')) {
                return 'سلام! چطور میتونم کمک کنم؟';
            } else if (lowerMessage.includes('برنامه') || lowerMessage.includes('کلاس')) {
                return 'برنامه هفتگی در بخش "برنامه هفتگی کلاسی" موجود است.';
            } else if (lowerMessage.includes('دانلود') || lowerMessage.includes('download')) {
                return 'لینک‌های دانلود در بخش "برنامه‌های کاربردی" و "دانلود" موجود هستند.';
            } else if (lowerMessage.includes('کمک') || lowerMessage.includes('help')) {
                return 'حتما! من اینجام تا کمک کنم. در چه زمینه‌ای نیاز به راهنمایی دارید؟';
            } else if (lowerMessage.includes('هوش مصنوعی') || lowerMessage.includes('ai')) {
                return 'من دستیار هوش مصنوعی سرور گودرزی هستم. میتونم در زمینه‌های مختلف کمکتون کنم!';
            } else if (lowerMessage.includes('گودرزی')) {
                return 'سرور گودرزی یک پروژه تستی با قابلیت‌های متنوع از جمله هوش مصنوعی است!';
            } else if (lowerMessage.includes('تشکر') || lowerMessage.includes('ممنون')) {
                return 'خواهش میکنم! خوشحالم که مفید بودم.';
            } else {
                return 'جالب است! میتونید کمی بیشتر توضیح بدید تا بتونم بهتر کمک کنم?';
            }
        }
    </script>
</body>
</html>
