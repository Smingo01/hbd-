HBD.พี่อ้วน
<html lang="th">
<head>
<meta charset="UTF-8">
<title>สุขสันต์วันเกิด 🎂</title>
<style>
  body {
    margin: 0;
    padding: 20px;
    height: 100vh;
    background: linear-gradient(to top right, #ffdde1, #ee9ca7);
    font-family: 'Segoe UI', Tahoma, sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    overflow: hidden;
  }
  h1 {
    font-size: 2.5rem;
    color: #fff;
    text-shadow: 2px 2px 5px #333;
    margin: 10px 0;
    text-align: center;
  }
  #friendPhoto {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
    border: 5px solid #fff;
    box-shadow: 0 0 15px rgba(0,0,0,0.3);
    margin-bottom: 15px;
  }
  .cake { position: relative; width: 220px; height: 180px; margin: 20px auto; }
  .layer { position: absolute; left: 50%; transform: translateX(-50%); border-radius: 10px; }
  .layer1 { width: 220px; height: 70px; background: #ffb6c1; bottom: 0; }
  .layer2 { width: 180px; height: 60px; background: #ff99cc; bottom: 60px; }
  .layer3 { width: 140px; height: 50px; background: #ff66b2; bottom: 110px; }
  .icing { width: 100%; height: 20px; background: #fff; border-radius: 0 0 10px 10px; position: absolute; top: 0; }
  .candles { position: absolute; top: -40px; left: 50%; transform: translateX(-50%); display: flex; gap: 15px; }
  .candle { width: 15px; height: 40px; background: #fff; border-radius: 5px; position: relative; }
  .flame { position: absolute; top: -20px; left: 50%; transform: translateX(-50%); width: 14px; height: 20px; background: radial-gradient(ellipse at center, yellow 0%, orange 70%, red 100%); border-radius: 50%; animation: flicker 0.3s infinite alternate; }
  @keyframes flicker { from { transform: translateX(-50%) scale(1); opacity: 1; } to { transform: translateX(-50%) scale(1.2); opacity: 0.6; } }

  .balloon { position: absolute; bottom: -150px; width: 50px; height: 70px; border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%; animation: floatUp 10s linear infinite; }
  .balloon::after { content: ''; position: absolute; top: 70px; left: 24px; width: 2px; height: 60px; background: #444; }
  @keyframes floatUp { from { transform: translateY(0); } to { transform: translateY(-120vh); } }

  #message { font-size: 1.8rem; margin-top: 20px; color: #fff; text-shadow: 1px 1px 3px #000; position: relative; }

  /* animation ข้อความลอยขึ้นค้างอยู่ */
  .floatingMessage {
    position: absolute;
    left: 50%;
    bottom: 50px; /* เริ่มจากด้านล่าง */
    transform: translateX(-50%) scale(0.5);
    font-size: 2rem;
    color: yellow;
    font-weight: bold;
    text-shadow: 2px 2px 5px #333;
    animation: floatUpMsg 3s ease-out forwards;
  }
  @keyframes floatUpMsg {
    0% { bottom: 50px; transform: translateX(-50%) scale(0.5); }
    50% { transform: translateX(-50%) scale(1.2); }
    100% { bottom: 300px; transform: translateX(-50%) scale(1); }
  }
</style>
</head>
<body>
  <!-- 🖼️ แก้ไขรูปและชื่อเพื่อนตรงนี้ -->
  <img id="friendPhoto" src="img/ed498ebfdc0bf3d052ecf9d351dce31a_1730967491968_0.webp.jpg" alt="เพื่อน" />
  <h1>สุขสันต์วันเกิด พี่อ้วน 🎉</h1>

  <div class="cake">
    <div class="layer layer1"><div class="icing"></div></div>
    <div class="layer layer2"><div class="icing"></div></div>
    <div class="layer layer3"><div class="icing"></div></div>
    <div class="candles">
      <div class="candle"><div class="flame" id="flame1"></div></div>
      <div class="candle"><div class="flame" id="flame2"></div></div>
      <div class="candle"><div class="flame" id="flame3"></div></div>
    </div>
  </div>

  <div id="message">🎶</div>

  <!-- 🎵 เพลงวันเกิดแบบ MP3 + controls -->
  <div id="musicControls">
    <audio id="birthdayMusic" src="img/Screen_Recording_20250919_182508_YouTube.mp3" controls></audio>
  </div>

  <audio id="blowSound" src="https://www.soundjay.com/human/sounds/blowing-out-candle-01.mp3"></audio>
  <audio id="clapSound" src="https://www.soundjay.com/human/sounds/applause-01.mp3"></audio>

  <script>
    // 🎈 ลูกโป่งลอย
    const colors = ["red", "blue", "green", "purple", "orange", "pink"];
    setInterval(() => {
      let balloon = document.createElement("div");
      balloon.className = "balloon";
      balloon.style.left = Math.random() * window.innerWidth + "px";
      balloon.style.background = colors[Math.floor(Math.random() * colors.length)];
      balloon.style.animationDuration = (6 + Math.random() * 5) + "s";
      document.body.appendChild(balloon);
      setTimeout(() => balloon.remove(), 10000);
    }, 800);

    // 🔥 เทียน & เสียง
    const flames = [document.getElementById("flame1"), document.getElementById("flame2"), document.getElementById("flame3")];
    const blowSound = document.getElementById("blowSound");
    const clapSound = document.getElementById("clapSound");
    const message = document.getElementById("message");
    const music = document.getElementById("birthdayMusic");

    // 🎶 ดับเทียน + ลอยข้อความคำอวยพรค้างอยู่
    music.addEventListener("ended", () => {
      flames.forEach(f => f.style.display = "none"); // ดับเทียน
      blowSound.play();
      setTimeout(() => clapSound.play(), 1500);

      // สร้างข้อความลอยคำอวยพรค้างอยู่
      const floating = document.createElement("div");
      floating.className = "floatingMessage";
      floating.textContent = "🎂 สุขสันต์วันเกิด พี่อ้วน! สุขสันต์วันเกิดพี่ชายที่รัก ขอให้ปีนี้เป็นปีที่ดีเลิศสำหรับพี่ เต็มไปด้วยความสุข ความสำเร็จ และสุขภาพที่แข็งแรง ขอให้ทุกความฝันของพี่เป็นจริง และมีความสุขในทุกๆวัน ขอให้พี่พบเจอแต่สิ่งดีๆ และมีความสุขในทุกย่างก้าวของชีวิต สุขสันต์วันเกิดครับ 🎉";
      document.body.appendChild(floating);

      // ข้อความจะค้างอยู่บนหน้าจอ ไม่ลบออก
    });
  </script>
</body>
</html>
