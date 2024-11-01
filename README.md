<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chúc Mừng Giáng Sinh!</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-image: url('https://example.com/background-image.jpg'); /* Thay đường dẫn đến hình ảnh của bạn */
            background-size: cover;
            background-position: center;
            color: #333;
            text-align: center;
            overflow: hidden; /* Ẩn thanh cuộn */
        }
        h1 {
            color: #e63946;
        }
        .content {
            margin: 20px;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.8);
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            display: none; /* Ẩn nội dung ban đầu */
            position: relative; /* Đặt vị trí tương đối để sử dụng z-index */
            z-index: 1; /* Đặt z-index cao hơn bông tuyết */
            max-width: 600px; /* Giới hạn chiều rộng tối đa */
            width: 90%; /* Chiếm 90% chiều rộng màn hình */
            margin: 0 auto; /* Canh giữa */
        }
        a {
            color: #1d3557;
            text-decoration: none;
            font-weight: bold;
            cursor: pointer;
        }
        a:hover {
            text-decoration: underline;
        }
        /* Hiệu ứng tuyết */
        .snowflake {
            position: absolute;
            top: -10px;
            color: white;
            font-size: 1em;
            user-select: none;
            pointer-events: none;
            animation: fall linear infinite;
            z-index: 0; /* Đặt z-index thấp hơn nội dung */
        }

        @keyframes fall {
            0% {
                transform: translateY(0);
            }
            100% {
                transform: translateY(100vh); /* Rơi xuống hết màn hình */
            }
        }
    </style>
</head>
<body>
    <div class="content" id="main-content">
        <img src="123.jpg" alt="Hình ảnh Giáng Sinh" style="max-width: 100%; height: auto;">
        <h1>Chúc Mừng Giáng Sinh!</h1>
        <p>Hy vọng mùa Giáng sinh này mang đến cho bạn nhiều niềm vui và hạnh phúc!</p>
        <a id="more-info-link">Nhấn vào đây để xem thêm về Giáng sinh!</a>
    </div>

    <div class="content" id="holiday-content">
        <h1>Chào Mừng đến với Thế Giới Giáng Sinh!</h1>
        <p>Giáng sinh là một thời điểm để sum vầy bên gia đình và bạn bè.</p>
        <p>Chúc bạn có một mùa Giáng sinh an lành và hạnh phúc!</p>
        <a id="back-link">Quay lại trang chính</a>
    </div>

    <script>
        // Hiện nội dung chính
        document.getElementById('main-content').style.display = 'block';

        // Sự kiện khi nhấp vào dòng chữ để xem thêm
        document.getElementById('more-info-link').onclick = function() {
            document.getElementById('main-content').style.display = 'none'; // Ẩn nội dung chính
            document.getElementById('holiday-content').style.display = 'block'; // Hiện nội dung Giáng sinh
        };

        // Sự kiện khi nhấp để quay lại
        document.getElementById('back-link').onclick = function() {
            document.getElementById('holiday-content').style.display = 'none'; // Ẩn nội dung Giáng sinh
            document.getElementById('main-content').style.display = 'block'; // Hiện lại nội dung chính
        };

        // Tạo hiệu ứng tuyết
        function createSnowflake() {
            const snowflake = document.createElement('div');
            snowflake.className = 'snowflake';
            snowflake.innerHTML = '❄'; // Biểu tượng bông tuyết
            snowflake.style.left = Math.random() * 100 + 'vw'; // Đặt vị trí bên trái ngẫu nhiên
            snowflake.style.fontSize = Math.random() * 1.5 + 0.5 + 'em'; // Kích thước ngẫu nhiên
            document.body.appendChild(snowflake);

            // Thời gian tồn tại của bông tuyết
            const fallDuration = Math.random() * 3 + 2; // Từ 2 đến 5 giây
            snowflake.style.animationDuration = fallDuration + 's';

            // Xóa bông tuyết sau khi nó rơi xuống
            snowflake.addEventListener('animationend', () => {
                snowflake.remove();
            });
        }

        // Tạo tuyết rơi liên tục
        setInterval(createSnowflake, 300); // Tạo bông tuyết mỗi 300ms
    </script>
</body>
</html>
