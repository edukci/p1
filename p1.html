<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>월별 행사 달력</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/PapaParse/5.3.2/papaparse.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.29.4/moment.min.js"></script>
    <style>
        body {
            font-family: 'Malgun Gothic', 'Apple SD Gothic Neo', sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f5f5f5;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background-color: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            padding: 20px;
            border-radius: 5px;
        }
        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 20px;
        }
        .controls {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            align-items: center;
        }
        .month-selector {
            display: flex;
            align-items: center;
        }
        select {
            padding: 8px;
            margin: 0 5px;
            border-radius: 4px;
            border: 1px solid #ddd;
        }
        button {
            padding: 8px 15px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #45a049;
        }
        .calendar {
            width: 100%;
            border-collapse: collapse;
        }
        .calendar th {
            background-color: #f0f0f0;
            padding: 10px;
            text-align: center;
            border: 1px solid #ddd;
        }
        .calendar td {
            border: 1px solid #ddd;
            height: 120px;
            vertical-align: top;
            padding: 5px;
            position: relative;
        }
        .date {
            font-weight: bold;
            margin-bottom: 5px;
            text-align: right;
        }
        .event {
            background-color: #e6f7ff;
            border-radius: 3px;
            padding: 3px 5px;
            margin-bottom: 3px;
            font-size: 0.9em;
            cursor: pointer;
            border-left: 3px solid #1890ff;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
        }
        .event-container {
            max-height: 90px;
            overflow-y: auto;
        }
        .weekend {
            background-color: #f9f9f9;
        }
        .today {
            background-color: #ffffcc;
        }
        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.4);
        }
        .modal-content {
            background-color: #fefefe;
            margin: 10% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            max-width: 600px;
            border-radius: 5px;
        }
        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
        }
        .close:hover {
            color: black;
        }
        .event-title {
            font-size: 1.2em;
            font-weight: bold;
            margin-bottom: 10px;
            color: #333;
        }
        .event-detail {
            margin-bottom: 5px;
        }
        .event-label {
            font-weight: bold;
            display: inline-block;
            min-width: 80px;
        }
        .file-input {
            display: none;
        }
        .file-label {
            padding: 8px 15px;
            background-color: #2196F3;
            color: white;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .file-label:hover {
            background-color: #0b7dda;
        }
        .empty-message {
            text-align: center;
            padding: 20px;
            color: #999;
            font-style: italic;
        }
        .more-indicator {
            font-size: 0.8em;
            color: #666;
            text-align: center;
        }
        .stats {
            margin-top: 20px;
            padding: 10px;
            background-color: #f8f8f8;
            border-radius: 4px;
            font-size: 0.9em;
            color: #666;
        }
        .loading {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(255, 255, 255, 0.8);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        .spinner {
            border: 5px solid #f3f3f3;
            border-top: 5px solid #3498db;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .event-type-공연 { border-left-color: #ff9800; background-color: #fff3e0; }
        .event-type-전시 { border-left-color: #2196F3; background-color: #e3f2fd; }
        .event-type-체험 { border-left-color: #4CAF50; background-color: #e8f5e9; }
        .event-type-교육 { border-left-color: #9C27B0; background-color: #f3e5f5; }
        .event-type-행사 { border-left-color: #F44336; background-color: #ffebee; }
    </style>
</head>
<body>
    <div class="container">
        <h1>월별 행사 달력</h1>
        
        <div class="controls">
            <div>
                <label for="fileInput" class="file-label">CSV 파일 선택</label>
                <input type="file" id="fileInput" class="file-input" accept=".csv">
                <span id="fileName"></span>
            </div>
            
            <div class="month-selector">
                <select id="yearSelect"></select>
                <select id="monthSelect">
                    <option value="1">1월</option>
                    <option value="2">2월</option>
                    <option value="3">3월</option>
                    <option value="4">4월</option>
                    <option value="5">5월</option>
                    <option value="6">6월</option>
                    <option value="7">7월</option>
                    <option value="8">8월</option>
                    <option value="9">9월</option>
                    <option value="10">10월</option>
                    <option value="11">11월</option>
                    <option value="12">12월</option>
                </select>
                <button id="goToToday">오늘</button>
            </div>
        </div>
        
        <div id="calendarContainer"></div>
        
        <div id="stats" class="stats">
            CSV 파일을 선택해주세요.
        </div>
    </div>
    
    <div id="eventModal" class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <div id="eventDetails"></div>
        </div>
    </div>
    
    <div id="loadingIndicator" class="loading" style="display: none;">
        <div class="spinner"></div>
    </div>
    
    <script>
        // 전역 변수
        let eventsData = [];
        let totalRows = 0;
        let successfulRows = 0;
        let failedRows = 0;
        let limitations = [];
        
        // DOM 요소 참조
        const fileInput = document.getElementById('fileInput');
        const fileName = document.getElementById('fileName');
        const yearSelect = document.getElementById('yearSelect');
        const monthSelect = document.getElementById('monthSelect');
        const goToTodayBtn = document.getElementById('goToToday');
        const calendarContainer = document.getElementById('calendarContainer');
        const statsElement = document.getElementById('stats');
        const eventModal = document.getElementById('eventModal');
        const eventDetails = document.getElementById('eventDetails');
        const closeModalBtn = document.querySelector('.close');
        const loadingIndicator = document.getElementById('loadingIndicator');
        
        // 년도 선택 옵션 채우기 (현재 년도 ±5년)
        function populateYearOptions() {
            const currentYear = new Date().getFullYear();
            for (let year = currentYear - 5; year <= currentYear + 5; year++) {
                const option = document.createElement('option');
                option.value = year;
                option.textContent = year + '년';
                yearSelect.appendChild(option);
            }
            yearSelect.value = currentYear;
        }
        
        // 현재 월로 설정
        function setCurrentMonth() {
            const now = new Date();
            monthSelect.value = now.getMonth() + 1;
        }
        
        // 날짜 문자열 파싱 함수
        function parseDate(dateStr) {
            if (!dateStr) return null;
            
            // 문자열 타입인지 확인
            if (typeof dateStr !== 'string') {
                dateStr = String(dateStr);
            }
            
            dateStr = dateStr.trim();
            
            // 일반적인 날짜 형식 시도
            const formats = [
                'YYYY-MM-DD', 'YYYY/MM/DD', 'YYYY.MM.DD',
                'DD-MM-YYYY', 'DD/MM/YYYY', 'DD.MM.YYYY',
                'MM-DD-YYYY', 'MM/DD/YYYY', 'MM.DD.YYYY',
                'YY-MM-DD', 'YY/MM/DD', 'YY.MM.DD'
            ];
            
            for (const format of formats) {
                const date = moment(dateStr, format);
                if (date.isValid()) {
                    return date.toDate();
                }
            }
            
            // 한국어 날짜 형식 시도 (YYYY년MM월DD일)
            const koreanDatePattern = /(\d{4})년\s*(\d{1,2})월\s*(\d{1,2})일/;
            const koreanMatch = dateStr.match(koreanDatePattern);
            if (koreanMatch) {
                const date = new Date(
                    parseInt(koreanMatch[1]),
                    parseInt(koreanMatch[2]) - 1,
                    parseInt(koreanMatch[3])
                );
                if (!isNaN(date.getTime())) {
                    return date;
                }
            }
            
            // 숫자만 있는 경우 (YYYYMMDD 형식)
            const numericPattern = /^(\d{4})(\d{2})(\d{2})$/;
            const numericMatch = dateStr.match(numericPattern);
            if (numericMatch) {
                const date = new Date(
                    parseInt(numericMatch[1]),
                    parseInt(numericMatch[2]) - 1,
                    parseInt(numericMatch[3])
                );
                if (!isNaN(date.getTime())) {
                    return date;
                }
            }
            
            // Excel 일련번호 시도 (1900-01-01 = 1)
            if (/^\d+(\.\d+)?$/.test(dateStr)) {
                const excelDate = parseFloat(dateStr);
                if (excelDate > 0) {
                    // Excel의 날짜 시스템 (1900-01-01 = 1)
                    // 주의: Excel의 버그로 1900년 2월 29일이 실제로 존재하지 않지만 포함됨
                    const date = new Date(Date.UTC(1899, 11, 30));
                    date.setDate(date.getDate() + excelDate);
                    if (!isNaN(date.getTime())) {
                        return date;
                    }
                }
            }
            
            return null;
        }
        
        // CSV 파일 처리 함수
        function processCSVFile(file) {
            showLoading(true);
            eventsData = [];
            totalRows = 0;
            successfulRows = 0;
            failedRows = 0;
            limitations = [];
            
            Papa.parse(file, {
                header: true,
                skipEmptyLines: true,
                encoding: "UTF-8",
                complete: function(results) {
                    const data = results.data;
                    totalRows = data.length;
                    
                    for (let i = 0; i < data.length; i++) {
                        const row = data[i];
                        
                        try {
                            // 필수 필드 확인
                            if (!row['시작날짜'] || !row['행사제목']) {
                                failedRows++;
                                continue;
                            }
                            
                            // 날짜 파싱
                            const startDate = parseDate(row['시작날짜']);
                            if (!startDate) {
                                failedRows++;
                                limitations.push(`행 ${i+2}: 시작날짜 '${row['시작날짜']}' 형식을 인식할 수 없습니다.`);
                                continue;
                            }
                            
                            let endDate = parseDate(row['종료날짜']);
                            if (!endDate) {
                                endDate = new Date(startDate);
                            }
                            
                            // 이벤트 데이터 생성
                            const event = {
                                title: row['행사제목'] || '제목 없음',
                                startDate: startDate,
                                endDate: endDate,
                                startTime: row['시작시간'] || '',
                                endTime: row['종료시간'] || '',
                                content: row['행사내용'] || row['행사제목'] || '',
                                location: row['장소'] || '',
                                type: row['유형'] || '',
                                target: row['대상'] || '',
                                organization: row['기관'] || '',
                                contact: row['연락처'] || ''
                            };
                            
                            eventsData.push(event);
                            successfulRows++;
                        } catch (error) {
                            failedRows++;
                            limitations.push(`행 ${i+2}: 처리 중 오류 발생 - ${error.message}`);
                        }
                    }
                    
                    updateStats();
                    renderCalendar();
                    showLoading(false);
                },
                error: function(error) {
                    console.error('CSV 파싱 오류:', error);
                    statsElement.innerHTML = '파일을 읽는 중 오류가 발생했습니다: ' + error.message;
                    showLoading(false);
                }
            });
        }
        
        // 통계 업데이트
        function updateStats() {
            let statsHTML = `
                <strong>파일 처리 결과:</strong> 총 ${totalRows}행 중 ${successfulRows}행 성공, ${failedRows}행 실패<br>
                <strong>현재 표시 중:</strong> ${eventsData.length}개의 행사
            `;
            
            if (limitations.length > 0) {
                statsHTML += '<br><strong>처리 제한사항:</strong><br>';
                // 최대 5개까지만 표시
                const displayLimit = Math.min(limitations.length, 5);
                for (let i = 0; i < displayLimit; i++) {
                    statsHTML += `- ${limitations[i]}<br>`;
                }
                
                if (limitations.length > displayLimit) {
                    statsHTML += `... 외 ${limitations.length - displayLimit}개 더 있음`;
                }
                
                statsHTML += '<br><strong>제한 사항 해결 방법:</strong> CSV 파일의 날짜 형식을 YYYY-MM-DD 형식으로 통일하거나, 누락된 필수 필드(시작날짜, 행사제목)를 채워주세요.';
            }
            
            statsElement.innerHTML = statsHTML;
        }
        
        // 달력 렌더링 함수
        function renderCalendar() {
            const year = parseInt(yearSelect.value);
            const month = parseInt(monthSelect.value);
            
            // 월의 첫날과 마지막날
            const firstDay = new Date(year, month - 1, 1);
            const lastDay = new Date(year, month, 0);
            
            // 첫 주의 시작 요일 (0: 일요일, 1: 월요일, ...)
            let startingDay = firstDay.getDay();
            // 월요일이 첫 날이 되도록 조정 (0:일->6, 1:월->0, ..., 6:토->5)
            startingDay = startingDay === 0 ? 6 : startingDay - 1;
            
            // 달력 테이블 생성
            let calendarHTML = `
                <table class="calendar">
                    <thead>
                        <tr>
                            <th>월</th>
                            <th>화</th>
                            <th>수</th>
                            <th>목</th>
                            <th>금</th>
                            <th class="weekend">토</th>
                            <th class="weekend">일</th>
                        </tr>
                    </thead>
                    <tbody>
            `;
            
            let day = 1;
            const totalDays = lastDay.getDate();
            const today = new Date();
            const isCurrentMonth = today.getFullYear() === year && today.getMonth() + 1 === month;
            
            // 달력 행 생성
            for (let i = 0; i < 6; i++) {
                calendarHTML += '<tr>';
                
                // 달력 열 생성
                for (let j = 0; j < 7; j++) {
                    let cellClass = '';
                    
                    // 주말 클래스 추가
                    if (j >= 5) {
                        cellClass += 'weekend ';
                    }
                    
                    // 첫 주이고 시작 요일보다 앞이거나, 이미 모든 날짜를 표시한 경우
                    if ((i === 0 && j < startingDay) || day > totalDays) {
                        calendarHTML += `<td class="${cellClass}"></td>`;
                    } else {
                        // 오늘 날짜인지 확인
                        if (isCurrentMonth && day === today.getDate()) {
                            cellClass += 'today ';
                        }
                        
                        // 현재 날짜의 이벤트 찾기
                        const currentDate = new Date(year, month - 1, day);
                        const dateEvents = eventsData.filter(event => {
                            return currentDate >= new Date(event.startDate.setHours(0,0,0,0)) && 
                                  currentDate <= new Date(event.endDate.setHours(23,59,59,999));
                        });
                        
                        calendarHTML += `<td class="${cellClass}">`;
                        calendarHTML += `<div class="date">${day}</div>`;
                        
                        if (dateEvents.length > 0) {
                            calendarHTML += '<div class="event-container">';
                            
                            // 최대 3개만 표시하고 나머지는 +N개 형식으로 표시
                            const displayLimit = 3;
                            for (let k = 0; k < Math.min(dateEvents.length, displayLimit); k++) {
                                const event = dateEvents[k];
                                const eventTypeClass = event.type ? `event-type-${event.type}` : '';
                                calendarHTML += `
                                    <div class="event ${eventTypeClass}" data-event-index="${eventsData.indexOf(event)}">
                                        ${event.title}
                                    </div>
                                `;
                            }
                            
                            // 더 많은 이벤트가 있으면 표시
                            if (dateEvents.length > displayLimit) {
                                calendarHTML += `
                                    <div class="more-indicator">
                                        외 ${dateEvents.length - displayLimit}개 더...
                                    </div>
                                `;
                            }
                            
                            calendarHTML += '</div>';
                        }
                        
                        calendarHTML += '</td>';
                        day++;
                    }
                }
                
                calendarHTML += '</tr>';
                
                // 월의 모든 날짜를 표시했으면 반복 종료
                if (day > totalDays) {
                    break;
                }
            }
            
            calendarHTML += `
                    </tbody>
                </table>
            `;
            
            calendarContainer.innerHTML = calendarHTML;
            
            // 이벤트 클릭 이벤트 리스너 추가
            document.querySelectorAll('.event').forEach(eventElement => {
                eventElement.addEventListener('click', function() {
                    const eventIndex = parseInt(this.getAttribute('data-event-index'));
                    showEventDetails(eventsData[eventIndex]);
                });
            });
        }
        
        // 이벤트 상세 정보 표시
        function showEventDetails(event) {
            // 날짜 형식화
            const formatDate = date => {
                if (!date) return '';
                return `${date.getFullYear()}-${String(date.getMonth() + 1).padStart(2, '0')}-${String(date.getDate()).padStart(2, '0')}`;
            };
            
            // 이벤트 상세 정보 HTML 생성
            let detailsHTML = `
                <div class="event-title">${event.title}</div>
                
                <div class="event-detail">
                    <span class="event-label">시작날짜:</span> ${formatDate(event.startDate)}
                </div>
                
                <div class="event-detail">
                    <span class="event-label">종료날짜:</span> ${formatDate(event.endDate)}
                </div>
            `;
            
            // 시간 정보가 있으면 추가
            if (event.startTime) {
                detailsHTML += `
                    <div class="event-detail">
                        <span class="event-label">시작시간:</span> ${event.startTime}
                    </div>
                `;
            }
            
            if (event.endTime) {
                detailsHTML += `
                    <div class="event-detail">
                        <span class="event-label">종료시간:</span> ${event.endTime}
                    </div>
                `;
            }
            
            // 선택적 필드 추가
            const optionalFields = [
                { label: '장소', value: event.location },
                { label: '유형', value: event.type },
                { label: '대상', value: event.target },
                { label: '기관', value: event.organization },
                { label: '연락처', value: event.contact }
            ];
            
            for (const field of optionalFields) {
                if (field.value) {
                    detailsHTML += `
                        <div class="event-detail">
                            <span class="event-label">${field.label}:</span> ${field.value}
                        </div>
                    `;
                }
            }
            
            // 행사 내용이 있으면 추가
            if (event.content && event.content !== event.title) {
                detailsHTML += `
                    <div class="event-detail" style="margin-top: 10px;">
                        <span class="event-label" style="display: block; margin-bottom: 5px;">행사내용:</span>
                        <div style="white-space: pre-line;">${event.content}</div>
                    </div>
                `;
            }
            
            eventDetails.innerHTML = detailsHTML;
            eventModal.style.display = 'block';
        }
        
        // 로딩 인디케이터 표시/숨김
        function showLoading(show) {
            loadingIndicator.style.display = show ? 'flex' : 'none';
        }
        
        // 이벤트 핸들러 등록
        document.addEventListener('DOMContentLoaded', function() {
            populateYearOptions();
            setCurrentMonth();
            
            fileInput.addEventListener('change', function() {
                if (this.files.length > 0) {
                    const file = this.files[0];
                    fileName.textContent = file.name;
                    processCSVFile(file);
                }
            });
            
            yearSelect.addEventListener('change', renderCalendar);
            monthSelect.addEventListener('change', renderCalendar);
            
            goToTodayBtn.addEventListener('click', function() {
                const now = new Date();
                yearSelect.value = now.getFullYear();
                monthSelect.value = now.getMonth() + 1;
                renderCalendar();
            });
            
            closeModalBtn.addEventListener('click', function() {
                eventModal.style.display = 'none';
            });
            
            window.addEventListener('click', function(event) {
                if (event.target === eventModal) {
                    eventModal.style.display = 'none';
                }
            });
            
            // 초기 달력 렌더링
            renderCalendar();
        });
    </script>
</body>
</html>