# Link Page 🔗

A personal link-in-bio page with animated snow effect, scrollable links, and interactive hover effects.

หน้า Link-in-Bio ส่วนตัว พร้อมเอฟเฟคหิมะ ลิ้ง(เลื่อนได้ถ้ามีลิ้งค์เยอะ) และ hover effect 

---

## 📁 File Structure / โครงสร้างไฟล์

```
/
├── index.html        # Main file / ไฟล์หลัก
└── shocked-cat.gif   # Cover image / รูป cover (เปลี่ยนได้)
```

---

## 🖼️ เปลี่ยนรูป Cover / Change Cover Image

ค้นหาบรรทัดนี้ใน `index.html`:

```html
<img src="shocked-cat.gif" alt="cover" />
```

เปลี่ยน `shocked-cat.gif` เป็นชื่อไฟล์รูปของคุณ หรือ URL รูปจากอินเทอร์เน็ต:

```html
<!-- ใช้ไฟล์ในโฟลเดอร์เดียวกัน -->
<img src="my-photo.jpg" alt="cover" />

<!-- ใช้ URL จากอินเทอร์เน็ต -->
<img src="https://example.com/my-image.png" alt="cover" />
```

> รองรับ `.jpg`, `.png`, `.gif`, `.webp`

---

## ➕ เพิ่มลิ้ง / Add a New Link

ค้นหา comment นี้ใน `index.html`:

```html
<!-- ══════════════════════════════════
     LINK CARDS — ก๊อปปี้เพิ่มได้เรื่อยๆ
══════════════════════════════════ -->
<div class="links-scroll">
```

คัดลอก block ด้านล่างนี้แล้ววางไว้ **ก่อน** `</div><!-- /.links-scroll -->`:

```html
<a class="link-card" href="https://YOUR_LINK_HERE" target="_blank" rel="noopener" style="--i:4">
    <div class="card-icon" style="font-size:20px;">🎁</div>
    <div class="card-text">
        <div class="card-title">ชื่อลิ้ง</div>
        <div class="card-sub">คำอธิบายสั้นๆ</div>
    </div>
    <div class="card-more">⋮</div>
</a>
```

> `--i:4` คือลำดับ animation delay — เพิ่มทีละ 1 ในแต่ละลิ้งที่เพิ่ม (5, 6, 7 ...)

### ใช้ไอคอน SVG (Discord, YouTube ฯลฯ) / Using SVG Icons

แทน emoji ด้วย SVG เหมือนลิ้งที่มีอยู่แล้ว:

```html
<div class="card-icon">
    <svg viewBox="0 0 24 24">
        <path d="... SVG path ..." />
    </svg>
</div>
```

> หา SVG path ได้จาก [Simple Icons](https://simpleicons.org/)

---

## 🎨 เปลี่ยนสีพื้นหลัง / Change Background Color

ค้นหา `:root` ที่บนสุดของ `<style>`:

```css
:root {
    --page-bg-from: #c06060;   /* สีพื้นหลังด้านบน */
    --page-bg-to:   #a04040;   /* สีพื้นหลังด้านล่าง */
    --card-color:   #e8847a;   /* สีพื้นหลังของ card */
}
```

ตัวอย่างธีมอื่น:

|    ธีม     | `--page-bg-from` | `--page-bg-to` | `--card-color` |

| 🌊 Ocean  | `#1a6080` | `#0d3d52` | `#2a8099` |
| 🌿 Forest | `#2d6a4f` | `#1b4332` | `#40916c` |
| 🌙 Night  | `#2d2d44` | `#1a1a2e` | `#3d3d5c` |
| 🌸 Pink   | `#c06080` | `#a04060` | `#d4788a` |

---

## ✏️ เปลี่ยนชื่อและ Bio / Change Name & Bio

```html
<!-- ชื่อ -->
<div class="profile-name">DEWDABID</div>

<!-- Bio -->
<div class="bio">Content Creator · Gamer · Developer</div>
```

เปลี่ยนข้อความในทั้งสองบรรทัดได้เลยครับ

---

## ❄️ ปรับเอฟเฟคหิมะ / Adjust Snow Effect

ในส่วน `<script>` ท้ายไฟล์:

```javascript
// ขนาดเกล็ดหิมะ (1 = เล็กสุด, 4.5 = ใหญ่สุด)
const r = Math.random() * 3.5 + 1;

// ความเร็วตก
speed: Math.random() * 0.8 + 0.3 + r * 0.18,

// ความโปร่งแสง (0 = ล่องหน, 1 = ทึบ)
alpha: Math.random() * 0.45 + 0.25,
```

ปิดเอฟเฟคหิมะ — ลบ `<canvas id="snow-canvas"></canvas>` และ `<script>...</script>` ออกทั้งหมด

---

## 🚀 Deploy

### GitHub Pages
```bash
git add .
git commit -m "update"
git push
```
จากนั้นเปิด **Settings → Pages → Branch: main → / (root)** แล้ว Save

> ⚠️ ตรวจสอบว่า commit ไฟล์เวอร์ชันล่าสุดแล้ว และกด `Ctrl+Shift+R` เพื่อ hard refresh browser

### Netlify / Vercel
ลาก folder ทิ้งใน dashboard ได้เลย หรือเชื่อม GitHub repo

---

## 🔧 CSS Variables Reference

| Variable | ความหมาย | Default |

| `--page-bg-from` | สีพื้นหลังด้านบน      | `#c06060` 
| `--page-bg-to`   | สีพื้นหลังด้านล่าง     | `#a04040` 
| `--card-color`   | สีพื้น card          | `#e8847a` 
| `--card-radius`  | ความโค้งมุม card    | `28px` 
| `--accent`       | สีหลัก (ลิ้ง, ไอคอน) | `#f07820` 
| `--link-bg`      | สีพื้นปุ่มลิ้ง          | `rgba(255,255,255,0.92)` 
| `--text-on-card` | สีตัวอักษรบน card   | `#fff` 

---

Made by DEWDABID