<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>给萁萁的信</title>
  <style>
    body {
      font-family: "Segoe UI", "Microsoft YaHei", sans-serif;
      background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
      margin: 0;
      padding: 50px 0;
      overflow-x: hidden;
    }
    .letter {
      max-width: 700px;
      margin: 0 auto;
      background: rgba(255, 255, 255, 0.9);
      padding: 40px;
      border-radius: 15px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
      line-height: 1.8;
      font-size: 18px;
      position: relative;
      z-index: 2;
    }
    .signature {
      text-align: right;
      margin-top: 40px;
      font-style: italic;
      opacity: 0;
    }
    h1 {
      text-align: center;
      color: #ff6b81;
      margin-bottom: 30px;
    }
    .music {
      text-align: center;
      margin-bottom: 20px;
      position: relative;
      z-index: 2;
    }
    .heart {
      position: fixed;
      top: -10%;
      animation: fall 3s linear forwards;
      font-size: 2em;
      color: #ff6b81;
      z-index: 1;
    }
    @keyframes fall {
      to {
        transform: translateY(110vh) rotate(720deg);
        opacity: 0.8;
      }
    }
    #text-container {
      white-space: pre-wrap;
    }
  </style>
</head>
<body>
  <div class="music">
    <audio controls autoplay loop>
      <source src="https://cdn.freesound.org/previews/457/457569_9170664-lq.mp3" type="audio/mpeg">
     您的浏览器不支持音频播放。
    </audio>
    <p style="color:#ff6b81;">🎵 背景音乐</p>
  </div>

  <div class="letter">
    <h1>To：萁萁</h1>
    <div id="text-container"></div>
    <div class="signature">——爱你的旭</div>
  </div>

  <script>
    const text = `2025年5月14日我遇到了一个女孩 她很开朗大大方方的 走进了我的生活 让我的世界从此变得丰富多彩 她在过去的恋爱并不幸福 想要被爱 现在遇到了一个很爱她很爱她的我 而我这样一个拧巴的人需要一个坚定选择我的人 宝宝其实你不知道我远比你想象中的更需要你 因为我真的很在意你 你所有的一举一动都会左右我的情绪 我喜欢每天睁开眼睛就能看到你的消息 我喜欢你发现有趣的事情和我分享的样子 我喜欢你把大小事都告诉我 这会让我感觉到我也又被需要 路的尽头还有多远我们不知道 但无论怎么样 我都会一直陪你走下去的 希望可以走的很远 我会牢牢握紧你的手 都说爱情是相互的 你在乎我 我会更加珍惜你 你愿意理解我我更愿意花心思懂你 你给了我真心 我拼了命也不会负你 刚开始认识的时候原本以为不会有交集 真没想到已经认识了快200天了 而且还在一起啦 缘分真的很奇妙 所以我万般珍惜`;
    const container = document.getElementById('text-container');
    let index = 0;
    function type() {
      if (index < text.length) {
        container.textContent += text.charAt(index);
        index++;
        setTimeout(type, 80);
      } else {
        document.querySelector('.signature').style.opacity = '1';
      }
    }
    type();

    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.textContent = '❤️';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (Math.random() * 2 + 2) + 's';
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 5000);
    }
    setInterval(createHeart, 300);
  </script>
</body>
</html>
