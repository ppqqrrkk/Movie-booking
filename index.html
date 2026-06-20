<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>영화관 예매 시스템</title>
    <style>
        :root {
            --primary-color: #e50914;
            --bg-color: #141414;
            --card-bg: #2f2f2f;
            --text-color: #ffffff;
        }

        body {
            font-family: 'Noto Sans KR', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            padding: 20px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: #1f1f1f;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }

        h1 {
            text-align: center;
            color: var(--primary-color);
            margin-bottom: 30px;
        }

        .section {
            margin-bottom: 25px;
            padding: 20px;
            background: var(--card-bg);
            border-radius: 8px;
        }

        h2 {
            font-size: 1.2rem;
            margin-top: 0;
            border-left: 4px solid var(--primary-color);
            padding-left: 10px;
        }

        /* 영화 선택 */
        .movie-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
        }

        .movie-item {
            padding: 15px;
            background: #3e3e3e;
            border-radius: 6px;
            text-align: center;
            cursor: pointer;
            transition: all 0.2s;
            border: 2px solid transparent;
        }

        .movie-item.selected {
            border-color: var(--primary-color);
            background: #4e1a1a;
        }

        /* 날짜 및 시간 */
        select, input[type="date"] {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            border-radius: 4px;
            border: 1px solid #555;
            background: #333;
            color: #fff;
            font-size: 1rem;
        }

        /* 좌석 배치도 */
        .screen {
            width: 80%;
            margin: 0 auto 20px auto;
            background: #555;
            text-align: center;
            padding: 5px;
            font-size: 0.8rem;
            letter-spacing: 5px;
            border-radius: 0 0 15px 15px;
        }

        .seat-container {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 8px;
            max-width: 300px;
            margin: 0 auto;
        }

        .seat {
            background: #444;
            padding: 8px;
            text-align: center;
            font-size: 0.8rem;
            border-radius: 4px;
            cursor: pointer;
            user-select: none;
        }

        .seat.available:hover {
            background: #666;
        }

        .seat.selected {
            background: var(--primary-color);
        }

        .seat.occupied {
            background: #222;
            color: #555;
            cursor: not-allowed;
        }

        /* 요약 및 결제 */
        .summary-box {
            background: #111;
            padding: 15px;
            border-radius: 6px;
            margin-top: 15px;
            line-height: 1.6;
        }

        .btn-pay {
            width: 100%;
            padding: 15px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 6px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            margin-top: 15px;
        }

        .btn-pay:hover {
            background: #b80710;
        }

        .hidden {
            display: none;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>🎬 영화 예매 시스템</h1>

    <!-- 1. 영화 선택 -->
    <div class="section">
        <h2>1. 영화 선택</h2>
        <div class="movie-list" id="movieList">
            <div class="movie-item" onclick="selectMovie(this, '어벤져스: 엔드게임', 14000)">어벤져스: 엔드게임<br><small>14,000원</small></div>
            <div class="movie-item" onclick="selectMovie(this, '인셉션', 12000)">인셉션<br><small>12,000원</small></div>
            <div class="movie-item" onclick="selectMovie(this, '라라랜드', 11000)">라라랜드<br><small>11,000원</small></div>
        </div>
    </div>

    <!-- 2. 날짜 및 시간대 조회 -->
    <div class="section">
        <h2>2. 관람 날짜 및 시간 선택</h2>
        <input type="date" id="watchDate" onchange="updateSchedule()">
        <select id="watchTime" onchange="updateSchedule()">
            <option value="">시간대를 선택하세요</option>
            <option value="10:00 (1관)">10:00 (1관)</option>
            <option value="14:30 (2관)">14:30 (2관)</option>
            <option value="19:00 (1관)">19:00 (1관)</option>
        </select>
    </div>

    <!-- 3. 상영관 빈 시간 및 좌석 선택 -->
    <div class="section id="seatSection">
        <h2>3. 좌석 선택 (<span id="remains">--</span>석 남음)</h2>
        <p style="font-size:0.85rem; color:#aaa; text-align:center;">※ 회색은 이미 예매된 좌석입니다.</p>
        <div class="screen">SCREEN</div>
        <div class="seat-container" id="seatBoard">
            <!-- 자바스크립트로 좌석 생성 -->
        </div>
    </div>

    <!-- 4. 예매 정보 확인 및 결제 -->
    <div class="section">
        <h2>4. 예매 정보 확인 및 결제</h2>
        <div class="summary-box">
            <div><strong>선택 영화:</strong> <span id="sumMovie">-</span></div>
            <div><strong>상영 일시:</strong> <span id="sumDateTime">-</span></div>
            <div><strong>선택 좌석:</strong> <span id="sumSeats">-</span></div>
            <div><strong>최종 결제 금액:</strong> <span id="sumPrice" style="color:var(--primary-color); font-weight:bold;">0원</span></div>
        </div>

        <select id="paymentMethod">
            <option value="신용카드">신용카드 결제</option>
            <option value="카카오페이">카카오페이</option>
            <option value="네이버페이">네이버페이</option>
            <option value="토스페이">토스페이</option>
        </select>

        <button class="btn-pay" onclick="submitPayment()">결제 승인 요청</button>
    </div>
</div>

<script>
    // 상태 관리 변수
    let reservation = {
        movie: '',
        pricePerSeat: 0,
        date: '',
        time: '',
        seats: []
    };

    // 임의의 예약 꽉 찬 좌석 데이터 (행-열 규칙)
    const occupiedSeats = ['A-2', 'B-4', 'C-1', 'C-2'];

    // 오늘 날짜 기본값 세팅
    const today = new Date().toISOString().split('T')[0];
    document.getElementById('watchDate').min = today;
    document.getElementById('watchDate').value = today;
    reservation.date = today;

    // 1. 영화 선택 함수
    function selectMovie(element, name, price) {
        document.querySelectorAll('.movie-item').forEach(item => item.classList.remove('selected'));
        element.classList.add('selected');
        
        reservation.movie = name;
        reservation.pricePerSeat = price;
        updateSummary();
    }

    // 2 & 3. 일정 및 좌석 판 배치 업데이트
    function updateSchedule() {
        reservation.date = document.getElementById('watchDate').value;
        reservation.time = document.getElementById('watchTime').value;
        reservation.seats = []; // 조건 바뀔 때 선택 좌석 초기화
        
        const seatBoard = document.getElementById('seatBoard');
        seatBoard.innerHTML = '';

        if (!reservation.movie || !reservation.date || !reservation.time) {
            document.getElementById('remains').innerText = '--';
            updateSummary();
            return;
        }

        const rows = ['A', 'B', 'C', 'D'];
        const cols = 6;
        let totalSeats = rows.length * cols;
        let occupiedCount = occupiedSeats.length;
        
        document.getElementById('remains').innerText = totalSeats - occupiedCount;

        // 좌석 렌더링
        rows.forEach(row => {
            for(let col = 1; col <= cols; col++) {
                const seatId = `${row}-${col}`;
                const seatDiv = document.createElement('div');
                seatDiv.innerText = seatId;
                
                if (occupiedSeats.includes(seatId)) {
                    seatDiv.className = 'seat occupied';
                } else {
                    seatDiv.className = 'seat available';
                    seatDiv.onclick = () => toggleSeat(seatDiv, seatId);
                }
                seatBoard.appendChild(seatDiv);
            }
        });
        updateSummary();
    }

    // 좌석 선택/해제 토글
    function toggleSeat(element, seatId) {
        if (element.classList.contains('selected')) {
            element.classList.remove('selected');
            reservation.seats = reservation.seats.filter(s => s !== seatId);
        } else {
            element.classList.add('selected');
            reservation.seats.push(seatId);
        }
        updateSummary();
    }

    // 4. 화면 요약 정보 업데이트
    function updateSummary() {
        document.getElementById('sumMovie').innerText = reservation.movie || '선택 안 됨';
        document.getElementById('sumDateTime').innerText = (reservation.date && reservation.time) ? `${reservation.date} / ${reservation.time}` : '선택 안 됨';
        document.getElementById('sumSeats').innerText = reservation.seats.length > 0 ? reservation.seats.join(', ') : '선택 안 됨';
        
        const totalPay = reservation.seats.length * reservation.pricePerSeat;
        document.getElementById('sumPrice').innerText = totalPay.toLocaleString() + '원';
    }

    // 결제 프로세스 승인
    function submitPayment() {
        if (!reservation.movie) return alert('영화를 선택해주세요.');
        if (!reservation.date || !reservation.time) return alert('날짜와 시간대를 선택해주세요.');
        if (reservation.seats.length === 0) return alert('좌석을 최소 1개 이상 선택해주세요.');

        const method = document.getElementById('paymentMethod').value;
        const totalPay = reservation.seats.length * reservation.pricePerSeat;

        const confirmMsg = `[결제 승인 확인]\n\n` +
                           `🎬 영화: ${reservation.movie}\n` +
                           `📅 일시: ${reservation.date} ${reservation.time}\n` +
                           `💺 좌석: ${reservation.seats.join(', ')}\n` +
                           `💳 결제수단: ${method}\n` +
                           `💰 결제금액: ${totalPay.toLocaleString()}원\n\n` +
                           `위 내용으로 결제를 승인하시겠습니까?`;

        if (confirm(confirmMsg)) {
            alert('🎉 결제가 성공적으로 완료되었습니다! 예매가 확정되었습니다.');
            // 성공 후 초기화 혹은 리로드 가능
            location.reload();
        }
    }

    // 초기 실행
    updateSchedule();
</script>
</body>
</html>
