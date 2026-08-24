<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IT Open House Presentation</title>
    
    <!-- Reveal.js CSS -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.3.1/reveal.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.3.1/theme/white.min.css">
    
    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    
    <!-- Google Fonts & FontAwesome -->
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* Global Styles */
        body { margin: 0; padding: 0; font-family: 'Kanit', sans-serif; background-color: #f8f9fa; }
        .reveal { font-family: 'Kanit', sans-serif; }
        .reveal h1, .reveal h2, .reveal h3 { font-family: 'Kanit', sans-serif; text-transform: none; font-weight: 700; color: #2C3E50; }
        
        /* Custom Layouts */
        .slide-content {
            width: 100%;
            max-width: 1000px;
            margin: 0 auto;
        }

        /* Form Styles */
        .custom-form {
            text-align: left;
            font-size: 20px;
            background: #ffffff;
            padding: 25px 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            border-top: 5px solid #3498db;
        }
        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px 25px;
            margin-bottom: 20px;
        }
        .form-group { display: flex; flex-direction: column; }
        .form-group label { font-size: 18px; font-weight: 600; margin-bottom: 5px; color: #34495e; }
        .form-group input, .form-group select {
            padding: 10px 15px; font-size: 18px; font-family: 'Kanit', sans-serif;
            border: 2px solid #e9ecef; border-radius: 10px;
            transition: border-color 0.3s;
            outline: none;
            background-color: #f8f9fa;
        }
        .form-group input:focus, .form-group select:focus {
            border-color: #3498db;
            background-color: #fff;
        }
        .form-group.full { grid-column: 1 / -1; }
        
        button.submit-btn {
            width: 100%; padding: 15px; font-size: 22px; font-family: 'Kanit', sans-serif; font-weight: bold;
            color: white; background: linear-gradient(135deg, #3498db, #2980b9); border: none; border-radius: 10px; cursor: pointer;
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.4); transition: all 0.3s;
        }
        button.submit-btn:hover { transform: translateY(-3px); box-shadow: 0 8px 20px rgba(52, 152, 219, 0.6); }
        button.submit-btn:disabled { background: #95a5a6; cursor: not-allowed; transform: none; box-shadow: none; }

        /* Dashboard Styles */
        .dashboard-grid {
            display: grid; grid-template-columns: 1fr 1.5fr; gap: 30px; align-items: center;
            background: #ffffff; padding: 30px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.08);
        }
        .stat-box {
            background: #f8f9fa; padding: 25px; border-radius: 15px; margin-bottom: 20px; text-align: center;
            border: 1px solid #e9ecef; transition: transform 0.3s;
        }
        .stat-box:hover { transform: translateY(-5px); }
        .stat-box h4 { margin: 0 0 10px 0; font-size: 20px; color: #7f8c8d; }
        .stat-box .number { font-size: 55px; font-weight: bold; color: #2980b9; line-height: 1.2; }
        .chart-container { width: 100%; max-width: 450px; margin: 0 auto; position: relative; height: 350px; }

        /* Custom Notification Toast */
        #toast {
            position: fixed; top: 20px; right: -300px; background-color: #2ecc71; color: white;
            padding: 15px 25px; border-radius: 8px; font-size: 18px; font-weight: 500;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15); transition: right 0.4s ease; z-index: 9999;
            display: flex; align-items: center; gap: 10px;
        }
        #toast.show { right: 20px; }
        #toast.error { background-color: #e74c3c; }
    </style>
</head>
<body>

    <!-- Notification Container -->
    <div id="toast"><i class="fa-solid fa-circle-check"></i> <span id="toast-msg">บันทึกข้อมูลสำเร็จ</span></div>

    <div class="reveal">
        <div class="slides">
            
            <!-- Slide 1: Cover -->
            <section data-transition="zoom">
                <div class="slide-content">
                    <i class="fa-solid fa-laptop-code" style="font-size: 120px; color: #3498db; margin-bottom: 30px;"></i>
                    <h1 style="font-size: 3.5em; margin-bottom: 10px;">IT Open House</h1>
                    <h3 style="color: #7f8c8d; font-weight: 400;">ระบบลงทะเบียนและแสดงผลข้อมูล</h3>
                    <div style="margin-top: 60px; padding: 15px 30px; background: #eef2f5; border-radius: 50px; display: inline-block;">
                        <p style="margin: 0; color: #2c3e50; font-size: 24px; font-weight: 500;">
                            กดปุ่ม <i class="fa-solid fa-arrow-right-long fa-bounce" style="color: #e74c3c; margin: 0 10px;"></i> เพื่อเริ่มลงทะเบียน
                        </p>
                    </div>
                </div>
            </section>

            <!-- Slide 2: Form -->
            <section data-transition="slide">
                <div class="slide-content">
                    <h2 style="margin-bottom: 25px;"><i class="fa-solid fa-address-card" style="color: #3498db;"></i> ลงทะเบียนเข้าร่วมงาน</h2>
                    <form id="openHouseForm" class="custom-form">
                        <div class="form-grid">
                            <div class="form-group">
                                <label>คำนำหน้า</label>
                                <select id="prefix" required>
                                    <option value="">-- เลือก --</option>
                                    <option value="นาย">นาย</option>
                                    <option value="นางสาว">นางสาว</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label>ชื่อ-นามสกุล</label>
                                <input type="text" id="fullName" placeholder="เช่น สมชาย ใจดี" required>
                            </div>
                            <div class="form-group">
                                <label>เพศ</label>
                                <select id="gender" required>
                                    <option value="">-- เลือก --</option>
                                    <option value="ชาย">ชาย</option>
                                    <option value="หญิง">หญิง</option>
                                    <option value="อื่นๆ">อื่นๆ</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label>อายุ</label>
                                <input type="number" id="age" min="10" max="99" placeholder="เช่น 17" required>
                            </div>
                            <div class="form-group">
                                <label>ระดับชั้น</label>
                                <select id="grade" required>
                                    <option value="">-- เลือก --</option>
                                    <option value="ม.4">ม.4</option>
                                    <option value="ม.5">ม.5</option>
                                    <option value="ม.6">ม.6</option>
                                    <option value="ปวช.">ปวช.</option>
                                    <option value="อื่นๆ">อื่นๆ</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label>ชื่อโรงเรียน</label>
                                <input type="text" id="school" placeholder="ระบุชื่อโรงเรียน" required>
                            </div>
                            <div class="form-group">
                                <label>เบอร์โทรศัพท์</label>
                                <input type="tel" id="phone" placeholder="เช่น 0812345678" required>
                            </div>
                            <div class="form-group">
                                <label>Line ID (ไม่บังคับ)</label>
                                <input type="text" id="lineId" placeholder="ระบุ Line ID">
                            </div>
                            <div class="form-group full">
                                <label>สาขาวิชาที่สนใจของคณะไอที</label>
                                <select id="major" required>
                                    <option value="">-- เลือกระบุสาขาวิชาที่ท่านสนใจ --</option>
                                    <option value="เทคโนโลยีธุรกิจดิจิทัล">เทคโนโลยีธุรกิจดิจิทัล</option>
                                    <option value="เทคโนโลยีสารสนเทศและนวัตกรรมดิจิทัล">เทคโนโลยีสารสนเทศและนวัตกรรมดิจิทัล</option>
                                    <option value="ดิจิทัลมีเดียอาร์ต">ดิจิทัลมีเดียอาร์ต</option>
                                    <option value="วิศวกรรมความปลอดภัย">วิศวกรรมความปลอดภัย</option>
                                    <option value="ไม่สนใจ">ไม่สนใจ</option>
                                </select>
                            </div>
                        </div>
                        <button type="submit" class="submit-btn" id="submitBtn">
                            <i class="fa-solid fa-paper-plane"></i> บันทึกข้อมูล
                        </button>
                    </form>
                </div>
            </section>

            <!-- Slide 3: Dashboard -->
            <section data-transition="slide">
                <div class="slide-content">
                    <h2 style="margin-bottom: 30px;"><i class="fa-solid fa-chart-pie" style="color: #e74c3c;"></i> Dashboard สรุปความสนใจ</h2>
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
                </div>
            </section>

        </div>
    </div>

    <!-- Scripts -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.3.1/reveal.min.js"></script>
    <script>
        // Initialize Reveal.js Presentation
        Reveal.initialize({
            controls: true,
            progress: true,
            center: true,
            hash: false, // ปิดการเปลี่ยน URL Hash เพื่อแก้ปัญหา SecurityError ในหน้า Preview
            transition: 'slide',
            width: 1200, // กำหนดความกว้างมาตรฐาน
            height: 800, // กำหนดความสูงมาตรฐาน
            margin: 0.1
        });

        // Setup Dashboard State
        const majorCounts = {
            'เทคโนโลยีธุรกิจดิจิทัล': 0, 
            'เทคโนโลยีสารสนเทศและนวัตกรรมดิจิทัล': 0, 
            'ดิจิทัลมีเดียอาร์ต': 0, 
            'วิศวกรรมความปลอดภัย': 0, 
            'ไม่สนใจ': 0
        };
        let totalRegistered = 0;

        // Initialize Chart.js Doughnut Chart
        const ctx = document.getElementById('majorChart').getContext('2d');
        let myChart = new Chart(ctx, {
            type: 'doughnut',
            data: {
                labels: ['ธุรกิจดิจิทัล', 'นวัตกรรมดิจิทัล', 'มีเดียอาร์ต', 'ความปลอดภัย', 'ไม่สนใจ'],
                datasets: [{
                    data: [0, 0, 0, 0, 0],
                    backgroundColor: ['#3498db', '#9b59b6', '#e74c3c', '#f1c40f', '#95a5a6'],
                    borderWidth: 2,
                    borderColor: '#ffffff',
                    hoverOffset: 10
                }]
            },
            options: { 
                responsive: true,
                maintainAspectRatio: false,
                plugins: { 
                    legend: { position: 'bottom', labels: { font: { family: 'Kanit', size: 14 } } },
                    tooltip: {
                        titleFont: { family: 'Kanit' },
                        bodyFont: { family: 'Kanit' }
                    }
                },
                cutout: '60%'
            }
        });

        // Function to update stats text
        function updateDashboard() {
            document.getElementById('totalCount').innerText = totalRegistered;
            let maxCount = 0; 
            let topMajors = [];
            
            for (const [major, count] of Object.entries(majorCounts)) {
                if (major !== 'ไม่สนใจ' && count > 0) {
                    if (count > maxCount) { 
                        maxCount = count; 
                        topMajors = [major]; 
                    } 
                    else if (count === maxCount) { 
                        topMajors.push(major); 
                    }
                }
            }
            
            const topMajorEl = document.getElementById('topMajor');
            if (maxCount === 0) {
                topMajorEl.innerText = "รอข้อมูล...";
            } else if (topMajors.length === 1) {
                // Shorten name for display
                topMajorEl.innerText = topMajors[0].replace('เทคโนโลยี', '').replace('และนวัตกรรมดิจิทัล', '');
            } else {
                topMajorEl.innerText = "สูสีหลายสาขา";
            }
        }

        // Custom Notification UI (แทนที่การใช้ alert)
        function showNotification(message, type = 'success') {
            const toast = document.getElementById('toast');
            const msg = document.getElementById('toast-msg');
            
            msg.innerText = message;
            if(type === 'error') {
                toast.classList.add('error');
                toast.innerHTML = '<i class="fa-solid fa-circle-exclamation"></i> <span id="toast-msg">' + message + '</span>';
            } else {
                toast.classList.remove('error');
                toast.innerHTML = '<i class="fa-solid fa-circle-check"></i> <span id="toast-msg">' + message + '</span>';
            }
            
            toast.classList.add('show');
            
            // ซ่อนอัตโนมัติหลัง 3 วินาที
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }

        // Handle Form Submission
        document.getElementById('openHouseForm').addEventListener('submit', function(e) {
            e.preventDefault(); 
            const submitBtn = document.getElementById('submitBtn');
            submitBtn.innerHTML = '<i class="fa-solid fa-spinner fa-spin"></i> กำลังบันทึก...';
            submitBtn.disabled = true;

            const formData = {
                prefix: document.getElementById('prefix').value,
                fullName: document.getElementById('fullName').value,
                gender: document.getElementById('gender').value,
                age: document.getElementById('age').value,
                grade: document.getElementById('grade').value,
                school: document.getElementById('school').value,
                phone: document.getElementById('phone').value,
                lineId: document.getElementById('lineId').value,
                major: document.getElementById('major').value
            };

            // ========================================================
            // 🎯 นำ URL ของ Web App ที่ได้จากขั้นตอนที่ 2 มาวางในเครื่องหมายคำพูดด้านล่างนี้
            // ========================================================
            const SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbxVG32wNH7rMr0dR3aLAW1X9SwMkqpg9AbCJRKVIne6Z6ZpdyQ0w3LLXCEHNMH5Ln51pA/exec'; 

            if (SCRIPT_URL === 'YOUR_WEB_APP_URL_HERE') {
                showNotification('อย่าลืมนำ URL จาก Google Apps Script มาใส่ในโค้ดก่อนนะครับ!', 'error');
                submitBtn.innerHTML = '<i class="fa-solid fa-paper-plane"></i> บันทึกข้อมูล';
                submitBtn.disabled = false;
                return;
            }

            // ส่งข้อมูลไปยัง Google Sheets
            fetch(SCRIPT_URL, {
                method: 'POST',
                body: JSON.stringify(formData),
                headers: { 'Content-Type': 'text/plain;charset=utf-8' } // ต้องใช้ text/plain เพื่อป้องกันปัญหา CORS
            })
            .then(response => response.json())
            .then(data => {
                if (data.result === 'success') {
                    // อัปเดตข้อมูลกราฟในหน้า Dashboard
                    if(formData.major && majorCounts[formData.major] !== undefined) {
                        majorCounts[formData.major]++;
                        totalRegistered++;
                        
                        myChart.data.datasets[0].data = Object.values(majorCounts);
                        myChart.update();
                        updateDashboard();
                    }
                    
                    showNotification('บันทึกข้อมูลลง Google Sheet สำเร็จ!');
                    document.getElementById('openHouseForm').reset();
                    
                    // เลื่อนสไลด์ไปหน้า Dashboard
                    setTimeout(() => {
                        Reveal.slide(2);
                    }, 800);
                } else {
                    showNotification('เกิดข้อผิดพลาดจากฝั่งเซิร์ฟเวอร์', 'error');
                }
            })
            .catch(error => {
                showNotification('ไม่สามารถเชื่อมต่อได้ กรุณาลองใหม่', 'error');
            })
            .finally(() => {
                submitBtn.innerHTML = '<i class="fa-solid fa-paper-plane"></i> บันทึกข้อมูล';
                submitBtn.disabled = false;
            });
        });
    </script>
</body>
</html>
