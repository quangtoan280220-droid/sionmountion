<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Leo núi vượt thử thách</title>
  <style>
    :root{
      --steps: 6;           /* số câu hỏi */
      --step-height: 65px;  /* khoảng cách mỗi bước leo */
      --char-size: 48px;
      --mountain-color: #7a5f3b;
      --sky: linear-gradient(#b3e5fc, #e1f5fe);
      --ground: #6db37f;
      --accent: #ffcc00;
    }

    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      background: var(--sky);
      color: #222;
      display: grid;
      grid-template-columns: 1fr 420px;
      min-height: 100vh;
    }

    /* Khu vực game */
    .scene {
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: flex-end;
      justify-content: center;
      padding: 24px;
    }

    .ground {
      position: absolute;
      bottom: 0;
      left: 0; right: 0;
      height: 120px;
      background: var(--ground);
    }

    /* Núi dạng đa giác */
    .mountain {
    position: absolute;
  bottom: 120px;
  left: 50%;
  transform: translateX(-50%);
  width: 60%;
  max-width: 9000px;
  height: 500px;
  background-image: url('fuji.jpg'); /* Đổi thành đường dẫn ảnh bạn có */
  background-size: cover;
  background-position: center;

    }

    /* Vạch bước (bậc leo) */
    .step {
      position: absolute;
      left: 1%;
      transform: translateX(-1%);
      width: 0.5%;
      height: 0.5px;
      background: rgba(255,255,255,.7);
      border-radius: 0.5px;
    }

    /* Nhân vật hoạt hình (hình tròn + mắt) */
    .character {
      position: absolute;
  bottom: 120px;
  left: 50%;
  transform: translateX(-50%);
  width: 64px;
  height: 64px;
  background-image: url('samurai.png'); /* Đổi thành đường dẫn ảnh chiến binh */
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
  transition: bottom .5s ease;

    }

    @keyframes idle {
      0%, 100% { transform: translateX(-50%) translateY(0); }
      50% { transform: translateX(-50%) translateY(-3px); }
    }

   

    /* UI bên phải */
    .panel {
      background: #ffffffcc;
      backdrop-filter: blur(6px);
      border-left: 1px solid #ddd;
      padding: 20px;
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .title {
      font-weight: 700;
      font-size: 20px;
    }

    .progress {
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .dot {
      width: 14px; height: 14px;
      border-radius: 50%;
      background: #ddd;
      border: 1px solid #bbb;
    }
    .dot.active { background: #4caf50; border-color: #2e7d32; }
    .dot.current { background: var(--accent); border-color: #c9a300; }

    .question {
      background: #fff;
      border: 1px solid #ddd;
      border-radius: 10px;
      padding: 14px;
    }

    .answers {
      display: grid;
      gap: 10px;
      margin-top: 10px;
    }

    button.answer {
      padding: 10px 12px;
      border-radius: 8px;
      border: 1px solid #ccc;
      background: #f7f7f7;
      cursor: pointer;
      text-align: left;
      transition: transform .05s ease, background .2s ease, border-color .2s ease;
    }
    button.answer:hover { background: #eee; }
    button.answer:active { transform: scale(.98); }

    .controls {
      display: flex;
      gap: 8px;
      margin-top: 8px;
    }
    .btn {
      padding: 8px 12px;
      border-radius: 8px;
      border: 1px solid #bbb;
      background: #fafafa;
      cursor: pointer;
    }

    .toast {
      font-size: 14px;
      color: #444;
      min-height: 20px;
    }

    .win {
      position: absolute;
      top: 10%;
      left: 50%;
      transform: translateX(-50%);
      background: #ffffffee;
      border: 2px solid #4caf50;
      color: #2e7d32;
      padding: 12px 16px;
      border-radius: 10px;
      display: none;
      font-weight: 700;
      filter: drop-shadow(0 6px 10px rgba(0,0,0,.2));
    }
    .win.show { display: block; }

    /* Responsive */
    @media (max-width: 900px) {
      body { grid-template-columns: 1fr; }
      .panel { border-left: none; border-top: 1px solid #ddd; }
      .mountain { width: 80%; }
    }
  </style>
</head>
<body>
  <div class="scene">
    <div class="ground"></div>
    <div class="mountain" id="mountain"></div>

    <!-- Bậc leo sẽ được JS tạo -->
    <!-- Nhân vật -->
    <div class="character" id="character" aria-label="Nhân vật">
      <div class="face">
        <div class="eye left"></div>
        <div class="eye right"></div>
        <div class="smile"></div>
      </div>
    </div>

    <div class="win" id="winBanner">Bạn đã lên đỉnh núi! 🎉</div>
  </div>

  <aside class="panel">
    <div class="title">Leo núi vượt thử thách</div>

    <div class="progress" id="progressDots"></div>

    <div class="question">
      <div id="questionText">Câu hỏi sẽ hiển thị ở đây.</div>
      <div class="answers" id="answers"></div>
      <div class="controls">
        <button class="btn" id="resetBtn">Làm lại từ đầu</button>
        <button class="btn" id="shuffleBtn">Xáo trộn đáp án</button>
      </div>
      <div class="toast" id="toast"></div>
    </div>

    <div style="font-size:13px;color:#555;">
      Gợi ý: Sửa nội dung mảng <code>questions</code> trong mã để thay câu hỏi/đáp án.
    </div>
  </aside>

  <script>
    // ====== CẤU HÌNH CÂU HỎI (SỬA TẠI ĐÂY) ======
    // Mỗi phần tử: { text: '...', options: ['A','B','C'], correctIndex: 1 }
    const questions = [
      {
        text: '1) Thủ đô của Việt Nam là gì?',
        options: ['TP.HCM', 'Hà Nội', 'Đà Nẵng'],
        correctIndex: 1
      },
      {
        text: '2) 2 + 3 bằng bao nhiêu?',
        options: ['4', '5', '6'],
        correctIndex: 1
      },
      {
        text: '3) Biển lớn nhất thế giới?',
        options: ['Đại Tây Dương', 'Ấn Độ Dương', 'Thái Bình Dương'],
        correctIndex: 2
      },
      {
        text: '4) Ngôn ngữ dùng để tạo cấu trúc trang web?',
        options: ['CSS', 'HTML', 'Python'],
        correctIndex: 1
      },
      {
        text: '5) Tốc độ ánh sáng xấp xỉ?',
        options: ['300.000 km/s', '30.000 km/s', '3.000 km/s'],
        correctIndex: 0
      },
      {
        text: '6) Số nguyên tố nhỏ nhất?',
        options: ['1', '2', '3'],
        correctIndex: 1
      }
    ];

    // ====== BIẾN TRẠNG THÁI ======
    let current = 0; // chỉ số câu hỏi hiện tại
    const total = questions.length;

    // ====== THAM CHIẾU DOM ======
    const mountainEl = document.getElementById('mountain');
    const characterEl = document.getElementById('character');
    const winBanner = document.getElementById('winBanner');
    const questionText = document.getElementById('questionText');
    const answersEl = document.getElementById('answers');
    const toastEl = document.getElementById('toast');
    const progressDots = document.getElementById('progressDots');
    const resetBtn = document.getElementById('resetBtn');
    const shuffleBtn = document.getElementById('shuffleBtn');

    // ====== TẠO BẬC LEO & DOT PROGRESS ======
    function buildSteps() {
      // Xóa cũ
      document.querySelectorAll('.step').forEach(s => s.remove());
      progressDots.innerHTML = '';

      // Tạo bậc leo theo số câu hỏi
      for (let i = 0; i < total; i++) {
        const step = document.createElement('div');
        step.className = 'step';
        const baseBottom = 120; // chân núi
        step.style.bottom = (baseBottom + (i + 1) * parseInt(getComputedStyle(document.documentElement).getPropertyValue('--step-height'))) + 'px';
        mountainEl.appendChild(step);

        const dot = document.createElement('div');
        dot.className = 'dot';
        progressDots.appendChild(dot);
      }
      updateProgressDots();
    }

    function updateProgressDots() {
      const dots = progressDots.querySelectorAll('.dot');
      dots.forEach((d, i) => {
        d.classList.toggle('active', i < current);
        d.classList.toggle('current', i === current);
      });
    }

    // ====== CẬP NHẬT VỊ TRÍ NHÂN VẬT ======
    function updateCharacterPosition() {
      const baseBottom = 120;
      const stepHeight = parseInt(getComputedStyle(document.documentElement).getPropertyValue('--step-height'));
      const newBottom = baseBottom + current * stepHeight;
      characterEl.style.bottom = newBottom + 'px';

      // Nghiêng nhẹ khi leo
      characterEl.style.transform = `translateX(-50%) rotate(${current > 0 ? 2 : 0}deg)`;
    }

    // ====== HIỂN THỊ CÂU HỎI ======
    function renderQuestion() {
      const q = questions[current];
      questionText.textContent = q ? q.text : 'Hoàn thành!';
      answersEl.innerHTML = '';

      if (!q) return;

      q.options.forEach((opt, idx) => {
        const btn = document.createElement('button');
        btn.className = 'answer';
        btn.textContent = opt;
        btn.addEventListener('click', () => handleAnswer(idx));
        answersEl.appendChild(btn);
      });

      updateProgressDots();
      updateCharacterPosition();
      toast('');
    }

    // ====== XỬ LÝ TRẢ LỜI ======
    function handleAnswer(selectedIndex) {
      const q = questions[current];
      const correct = selectedIndex === q.correctIndex;

      if (correct) {
        toast('Đúng rồi! Tiếp tục nào 💪');
        current++;
        if (current >= total) {
          // Thắng
          updateCharacterPosition(); // lên đỉnh
          winBanner.classList.add('show');
          questionText.textContent = 'Bạn đã trả lời đúng tất cả câu hỏi!';
          answersEl.innerHTML = '';
          updateProgressDots();
          return;
        }
        renderQuestion();
      } else {
        toast('Sai mất rồi! Bạn tụt về câu đầu 😅');
        // Tụt về câu đầu
        current = 0;
        winBanner.classList.remove('show');
        renderQuestion();
      }
    }

    // ====== TIỆN ÍCH ======
    function toast(msg) {
      toastEl.textContent = msg;
      if (!msg) return;
      // Tự mờ sau 2.5s
      setTimeout(() => { if (toastEl.textContent === msg) toastEl.textContent = ''; }, 2500);
    }

    function shuffleAnswers() {
      const q = questions[current];
      if (!q) return;
      // Trộn đồng thời options và cập nhật correctIndex
      const pairs = q.options.map((opt, idx) => ({ opt, idx }));
      for (let i = pairs.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [pairs[i], pairs[j]] = [pairs[j], pairs[i]];
      }
      q.options = pairs.map(p => p.opt);
      q.correctIndex = pairs.findIndex(p => p.idx === q.correctIndex);
      renderQuestion();
    }

    // ====== SỰ KIỆN NÚT ======
    resetBtn.addEventListener('click', () => {
      current = 0;
      winBanner.classList.remove('show');
      renderQuestion();
      toast('Đã quay về câu đầu.');
    });

    shuffleBtn.addEventListener('click', shuffleAnswers);

    // ====== KHỞI TẠO ======
    buildSteps();
    renderQuestion();
  </script>
</body>
</html>
