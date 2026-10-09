
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Open House - Dashboard</title>
    
    <!-- Reveal.js CSS -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.3.1/reveal.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.3.1/theme/white.min.css">
    
    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    
    <!-- Google Fonts & FontAwesome -->
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        body { margin: 0; padding: 0; font-family: 'Kanit', sans-serif; background-color: #f8f9fa; }
        .reveal { font-family: 'Kanit', sans-serif; }
        .reveal h2 { font-family: 'Kanit', sans-serif; text-transform: none; font-weight: 700; color: #2C3E50; margin-bottom: 30px; }
        
        .slide-content { width: 100%; max-width: 1000px; margin: 0 auto; }

        .dashboard-grid {
            display: grid; grid-template-columns: 1fr 1.5fr; gap: 30px; align-items: center;
            background: #ffffff; padding: 30px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            border-top: 5px solid #e74c3c;
        }
        .stat-box {
            background: #f8f9fa; padding: 25px; border-radius: 15px; margin-bottom: 20px; text-align: center;
            border: 1px solid #e9ecef; transition: transform 0.3s;
        }
        .stat-box:hover { transform: translateY(-5px); }
        .stat-box h4 { margin: 0 0 10px 0; font-size: 20px; color: #7f8c8d; }
        .stat-box .number { font-size: 55px; font-weight: bold; color: #2980b9; line-height: 1.2; }
        .chart-container { width: 100%; max-width: 450px; margin: 0 auto; position: relative; height: 350px; }
        
        .nav-btn {
            display: inline-block; margin-top: 30px; padding: 12px 25px; font-size: 18px; font-weight: bold;
            color: white; background: #7f8c8d; border-radius: 8px; text-decoration: none; transition: 0.3s;
        }
        .nav-btn:hover { background: #34495e; transform: translateY(-2px); }
    </style>
</head>
<body>

    <div class="reveal">
        <div class="slides">
            <section data-transition="zoom">
                <div class="slide-content">
                    <h2><i class="fa-solid fa-chart-pie" style="color: #e74c3c;"></i> Dashboard สรุปความสนใจ</h2>
                    <div class="dashboard-grid">
                        <div class="stats-container">
                            <div class="stat-box" style="border-left: 5px solid #3498db;">
                                <h4>ยอดผู้ลงทะเบียนรวม</h4>
                                <div class="number" id="totalCount">0</div>
                                <span style="font-size: 18px; color: #7f8c8d; font-weight: 500;">คน</span>
                            </div>
                            <div class="stat-box" style="border-left: 5px solid #e67e22;">
                                <h4>สาขาที่ได้รับความนิยมสูงสุด</h4>
                                <div class="number" id="topMajor" style="font-size: 28px; color: #e67e22; padding: 15px 0;">รอข้อมูล...</div>
                            </div>
                        </div>
                        <div class="chart-container">
                            <canvas id="majorChart"></canvas>
                        </div>
                    </div>
                    
                    <a href="index.html" class="nav-btn"><i class="fa-solid fa-arrow-left"></i> กลับไปหน้าลงทะเบียน</a>
                </div>
            </section>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.3.1/reveal.min.js"></script>
    <script>
        // เริ่มต้น Reveal.js (ใช้แบบ 1 หน้า)
        Reveal.initialize({
            controls: false, progress: false, center: true, hash: false, width: 1200, height: 800
        });

        // กำหนดข้อมูลเริ่มต้น
        const defaultCounts = {
            'เทคโนโลยีธุรกิจดิจิทัล': 0, 'เทคโนโลยีสารสนเทศและนวัตกรรมดิจิทัล': 0, 
            'ดิจิทัลมีเดียอาร์ต': 0, 'วิศวกรรมความปลอดภัย': 0, 'ไม่สนใจ': 0
        };

        // ตั้งค่ากราฟ Chart.js
        const ctx = document.getElementById('majorChart').getContext('2d');
        let myChart = new Chart(ctx, {
            type: 'doughnut',
            data: {
                labels: ['ธุรกิจดิจิทัล', 'นวัตกรรมดิจิทัล', 'มีเดียอาร์ต', 'ความปลอดภัย', 'ไม่สนใจ'],
                datasets: [{
                    data: [0, 0, 0, 0, 0],
                    backgroundColor: ['#3498db', '#9b59b6', '#e74c3c', '#f1c40f', '#95a5a6'],
                    borderWidth: 2, borderColor: '#ffffff', hoverOffset: 10
                }]
            },
            options: { 
                responsive: true, maintainAspectRatio: false,
                plugins: { 
                    legend: { position: 'bottom', labels: { font: { family: 'Kanit', size: 14 } } },
                    tooltip: { titleFont: { family: 'Kanit' }, bodyFont: { family: 'Kanit' } }
                },
                cutout: '60%'
            }
        });

        // ฟังก์ชันดึงข้อมูลจาก LocalStorage และอัปเดตหน้าจอ
        function loadAndUpdateDashboard() {
            // ดึงข้อมูลที่ index.html บันทึกไว้
            const savedData = JSON.parse(localStorage.getItem('openHouseStats')) || defaultCounts;
            
            // คำนวณยอดรวม
            let totalRegistered = 0;
            let maxCount = 0; 
            let topMajors = [];
            
            for (const [major, count] of Object.entries(savedData)) {
                totalRegistered += count;
                
                if (major !== 'ไม่สนใจ' && count > 0) {
                    if (count > maxCount) { 
                        maxCount = count; 
                        topMajors = [major]; 
                    } else if (count === maxCount) { 
                        topMajors.push(major); 
                    }
                }
            }
            
            // อัปเดตตัวเลขบนจอ
            document.getElementById('totalCount').innerText = totalRegistered;
            const topMajorEl = document.getElementById('topMajor');
            
            if (maxCount === 0) {
                topMajorEl.innerText = "รอข้อมูล...";
            } else if (topMajors.length === 1) {
                topMajorEl.innerText = topMajors[0].replace('เทคโนโลยี', '').replace('และนวัตกรรมดิจิทัล', '');
            } else {
                topMajorEl.innerText = "สูสีหลายสาขา";
            }

            // อัปเดตกราฟ
            myChart.data.datasets[0].data = Object.values(savedData);
            myChart.update();
        }

        // โหลดข้อมูลครั้งแรกเมื่อเปิดหน้า
        loadAndUpdateDashboard();

        // **ความสามารถพิเศษ:** หากมีการกรอกข้อมูลในแท็บอื่น (index.html) หน้าต่างนี้จะอัปเดตตัวเองอัตโนมัติ!
        window.addEventListener('storage', function(e) {
            if (e.key === 'openHouseStats') {
                loadAndUpdateDashboard();
            }
        });
    </script>
</body>
</html>
