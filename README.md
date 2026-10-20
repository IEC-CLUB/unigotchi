# IEC Unigotchi

Mobile Tamagotchi game for RMIT IEC Club Day. One HTML file, no build step.

## 1. Put it on GitHub Pages (5 phút)
1. Tạo repo mới, ví dụ `unigotchi`, upload `index.html` (+ `firestore.rules`, `README.md`).
2. Repo → **Settings → Pages** → Source: `Deploy from a branch` → `main` / `root` → Save.
3. Link sẽ là `https://<username>.github.io/unigotchi/`.

Link cho post từng ban (vào thẳng trứng ban đó):

| Ban | Link |
|---|---|
| R&D | `.../unigotchi/#rnd` |
| Media | `.../unigotchi/#media` |
| F&L | `.../unigotchi/#fl` |
| EA | `.../unigotchi/#ea` |
| HR | `.../unigotchi/#hr` |

Không có Firebase game vẫn chạy đầy đủ, chỉ là gallery frame và Doodle Relay lưu trên từng máy.

## 2. Bật gallery chung + Doodle Relay online (Firebase, free)
1. https://console.firebase.google.com → **Add project** (tắt Google Analytics cho nhanh).
2. **Build → Firestore Database → Create database** → chọn region `asia-southeast1` → Production mode.
3. Tab **Rules** → dán toàn bộ nội dung `firestore.rules` → **Publish**.
4. Project settings (bánh răng) → **Your apps → Web (</>)** → đặt tên → copy object `firebaseConfig`.
5. Mở `index.html`, tìm `firebase:null,` trong block `CONFIG`, thay bằng:
   ```js
   firebase:{apiKey:"...",authDomain:"...",projectId:"...",storageBucket:"...",messagingSenderId:"...",appId:"..."},
   ```
6. Commit. Gallery sẽ hiện chữ **live** thay vì "this phone only".

## 3. Thông tin Executive (màn cuối)
Trong `CONFIG.execs`, điền `name`, `photo` (ví dụ upload `img/rnd.jpg` vào repo rồi ghi `"img/rnd.jpg"`), và `line`.
Đổi nút CTA ở `CONFIG.cta` (link form apply / page).

## 4. Nhạc nền
Upload file nhạc (club có quyền dùng) vào repo, đặt tên `music.mp3` cùng thư mục với `index.html`. Đổi tên khác thì sửa `CONFIG.music`. Nhạc bật sau lần chạm đầu tiên (luật trình duyệt), có nút 🔊/🔇 góc trên.

## 5. Restyle (cho Hùng)
Toàn bộ màu và font nằm trong `:root { ... }` đầu thẻ `<style>`. Font đang dùng: Pixelify Sans + M PLUS Rounded 1c (Google Fonts).

## Ghi chú
- Nghiêng máy (R&D) cần HTTPS — GitHub Pages có sẵn. iPhone sẽ hỏi quyền khi bấm START; từ chối thì vẫn kéo tay được.
- Tiến độ từng con lưu trên trình duyệt người chơi; đổi qua lại 5 trứng không mất.
- Ảnh người chơi upload ở F&L chỉ lên gallery khi họ bấm Publish.
