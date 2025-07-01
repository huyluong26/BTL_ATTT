<div align="center">
  <h1>ỨNG DỤNG BẢO MẬT TIN NHẮN VĂN BẢN BẰNG DES & RSA</h1>
</div>

<div>
  <h2>Giới thiệu</h2>
  <p>
    Đây là một ứng dụng web mô phỏng hệ thống <strong>nhắn tin bảo mật hai chiều</strong>, trong đó:
    <ul>
      <li>Tin nhắn được mã hóa bằng <strong>DES (CFB mode)</strong> để đảm bảo tính bí mật.</li>
      <li>Người gửi và người nhận được xác thực qua <strong>RSA 2048-bit</strong> (kèm chữ ký số RSA + OAEP + SHA-256).</li>
      <li>Ứng dụng sử dụng <strong>SHA-256</strong> để kiểm tra tính toàn vẹn của nội dung, phát hiện chỉnh sửa hoặc giả mạo tin nhắn.</li>
    </ul>
  </p>
</div>

<div>
  <h2>Công nghệ và thuật toán sử dụng</h2>
  <ul>
    <li><strong>Python Flask</strong> – Backend xử lý server</li>
    <li><strong>HTML/CSS/JS</strong> – Giao diện người dùng</li>
    <li><strong>DES (CFB)</strong> – Mã hóa tin nhắn văn bản</li>
    <li><strong>RSA 2048-bit</strong> – Ký số và trao đổi khóa bảo mật</li>
    <li><strong>SHA-256</strong> – Kiểm tra toàn vẹn tin nhắn</li>
  </ul>
</div>

<div>
  <h2>Luồng xử lý hệ thống</h2>
  <ol>
    <li><strong>Handshake</strong>: Hai người dùng trao đổi khóa RSA qua kết nối P2P</li>
    <li><strong>Xác thực & Trao khóa:</strong> Người gửi ký ID bằng RSA, tạo khóa DES và gửi kèm chữ ký</li>
    <li><strong>Mã hóa & gửi tin nhắn:</strong> Mã hóa tin bằng DES → Tạo hash → Ký số → Gửi đi</li>
    <li><strong>Người nhận:</strong> Giải RSA → Kiểm tra hash → Xác thực chữ ký → Giải DES</li>
  </ol>
</div>

<div>
  <h2> Các chức năng nổi bật</h2>
  <ul>
    <li> Đăng ký & đăng nhập người dùng</li>
    <li> Tạo và lưu khóa RSA cá nhân</li>
    <li> Nhắn tin 2 chiều có mã hóa</li>
    <li> Tự động ký số và kiểm tra hash tin nhắn</li>
    <li> Phản hồi lỗi nếu phát hiện chỉnh sửa (hash/ chữ ký sai)</li>
  </ul>
</div>

