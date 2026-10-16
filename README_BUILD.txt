README — Build APK bằng GitHub Actions

Project này chứa:
- config.xml
- www/index.html (mở link của bạn trong iframe)
- www/icon.png (icon 512x512)
- .github/workflows/android-build.yml (workflow tự động build APK debug trên GitHub Actions)

Hướng dẫn nhanh:
1) Tạo repository mới trên GitHub.
2) Giải nén ZIP và push toàn bộ nội dung lên repo (branch main).
3) Mở tab Actions trên GitHub — job "Build Android APK" sẽ chạy.
4) Khi job hoàn tất, vào job -> Artifacts -> tải "app-debug-apk" (chứa file app-debug.apk).

Nếu muốn APK signed (release):
- Tạo keystore trên máy của bạn.
- Mã hóa keystore bằng base64 và đưa vào GitHub secret (ví dụ KEYSTORE_BASE64) cùng KEYSTORE_PASSWORD, KEY_ALIAS, KEY_PASSWORD.
- Cập nhật workflow để giải mã và ký APK (mình có thể giúp cấu hình).

Link trang web được đóng gói: https://geometrydash-bice.vercel.app/
App name: Geometry Dash

Lưu ý: bạn cần build/sign trên máy hoặc dùng GitHub Actions với secret để có APK signed.
