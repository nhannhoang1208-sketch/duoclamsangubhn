# duoclamsangubhn
website tra cứu về phác đồ điều trị ung thư
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tra cứu phác đồ điều trị ung thư</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      background: #f5f5f5;
    }
    h1 {
      color: #2c3e50;
    }
    table {
      border-collapse: collapse;
      width: 100%;
      margin-top: 20px;
    }
    th, td {
      border: 1px solid #ccc;
      padding: 8px;
      text-align: left;
      cursor: pointer;
    }
    th {
      background: #3498db;
      color: white;
    }
    td:hover {
      background: #ecf0f1;
    }

    /* Popup modal */
    .modal {
      display: none;
      position: fixed;
      z-index: 1000;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: rgba(0,0,0,0.4);
    }
    .modal-content {
      background-color: #fff;
      margin: 15% auto;
      padding: 20px;
      border-radius: 8px;
      width: 60%;
      max-width: 500px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      animation: fadeIn 0.3s;
    }
    .close {
      color: #aaa;
      float: right;
      font-size: 20px;
      font-weight: bold;
      cursor: pointer;
    }
    .close:hover {
      color: #000;
    }
    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }
  </style>
</head>
<body>
  <h1>📖 Tra cứu phác đồ điều trị ung thư</h1>
  <p>Website giúp dược sĩ và bác sĩ dễ dàng tra cứu các phác đồ hóa trị.</p>

  <table>
    <tr>
      <th>Tên phác đồ</th>
      <th>Thành phần</th>
      <th>Nguy cơ giảm bạch cầu</th>
    </tr>
    <tr>
      <td>AC</td>
      <td>Doxorubicin + Cyclophosphamide</td>
      <td onclick="showProphylaxis('Trung bình')">Trung bình</td>
    </tr>
  </table>

  <!-- Popup -->
  <div id="popup" class="modal">
    <div class="modal-content">
      <span class="close" onclick="closePopup()">&times;</span>
      <h2>Thuốc dự phòng</h2>
      <p id="popup-text"></p>
    </div>
  </div>

  <script>
    function showProphylaxis(risk) {
      let message = "";
      if (risk === "Trung bình") {
        message = "Khuyến cáo: Cân nhắc dùng G-CSF (Filgrastim, Pegfilgrastim) nếu bệnh nhân có thêm yếu tố nguy cơ.";
      } else if (risk === "Cao") {
        message = "Khuyến cáo: Sử dụng G-CSF dự phòng (Filgrastim, Pegfilgrastim).";
      } else {
        message = "Nguy cơ thấp: thường không cần dự phòng bằng thuốc.";
      }
      document.getElementById("popup-text").innerText = message;
      document.getElementById("popup").style.display = "block";
    }

    function closePopup() {
      document.getElementById("popup").style.display = "none";
    }

    // đóng popup khi click ra ngoài
    window.onclick = function(event) {
      let popup = document.getElementById("popup");
      if (event.target === popup) {
        popup.style.display = "none";
      }
    }
  </script>
</body>
</html>
