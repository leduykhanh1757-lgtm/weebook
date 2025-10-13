# 📚 BookSelf - Website bán sách trực tuyến

## 🎯 Dành cho ai?

### 👨‍💻 Developer
- File chính: `index.html`, `script.js`, `style.css`, `data.js`
- Xem git history để hiểu cấu trúc

### 🎨 Designer / Content Manager
- **Chỉ cần sửa:** `data.js` (hoặc dùng Python scraper)
- **Xem hướng dẫn:** `scrapper/SCRAPING_GUIDE.md`

---

## 📁 Cấu trúc dự án chi tiết

```
weebook/
├── 📄 HTML Pages
│   ├── index.html                 ← Trang chủ với sản phẩm nổi bật
│   ├── category.html              ← Trang danh mục sản phẩm
│   ├── product.html               ← Chi tiết sản phẩm
│   ├── checkout.html              ← Trang thanh toán
│   ├── order-success.html         ← Xác nhận đặt hàng thành công
│   ├── orders.html                ← Quản lý đơn hàng
│   ├── profile.html               ← Hồ sơ người dùng
│   ├── reviews.html               ← Đánh giá sản phẩm
│   ├── auth.html                  ← Đăng nhập/đăng ký
│   ├── admin.html                 ← Panel quản trị
│   ├── chatbot.html               ← Chatbot AI
│   └── about.html                 ← Giới thiệu công ty
│
├── 🔧 JavaScript Files
│   ├── script.js                  ← JavaScript chính (logic website)
│   ├── load-components.js         ← Load header/footer/chatbot components
│   ├── checkout.js                ← Logic thanh toán
│   ├── order-success.js           ← Logic trang thành công
│   ├── orders.js                  ← Logic quản lý đơn hàng
│   ├── profile.js                 ← Logic hồ sơ người dùng
│   ├── reviews.js                 ← Logic đánh giá
│   ├── auth.js                    ← Logic đăng nhập/đăng ký
│   └── admin.js                   ← Logic admin panel
│
├── 🎨 Styling & Components
│   └── style.css                  ← CSS chính (responsive design)
│
├── 📊 Data & Configuration
│   ├── data.js                    ← Database sản phẩm (169 sản phẩm)
│   └── README.md                  ← Tài liệu dự án
│
├── 🖼️ Assets
│   └── images/                    ← Thư mục ảnh sản phẩm và logo
│       ├── book-*.jpg             ← Ảnh sách
│       ├── hero-banner.*           ← Banner trang chủ
│       ├── logo.png               ← Logo công ty
│       └── icon-*.png             ← Icons
│
└── 📋 Info Pages
    └── info/                      ← Thư mục chính sách và hướng dẫn
        ├── chinh-sach-*.html      ← Các chính sách
        ├── huong-dan-*.html       ← Hướng dẫn sử dụng
        └── template.html          ← Template trang info
```

---

## 📋 Chi tiết từng file quan trọng

### 🗂️ File chính

#### `data.js` - Database sản phẩm
- **Mục đích:** Chứa toàn bộ dữ liệu sản phẩm (169 sản phẩm)
- **Cấu trúc:** Object `BOOK_DATABASE` với các thuộc tính:
  - `id`, `title`, `author`, `publisher`
  - `price`, `originalPrice`, `discount`
  - `category`, `subcategory`
  - `images[]`, `description`, `tags[]`
  - `rating`, `reviewCount`, `stock`
- **Categories:** vietnamese, foreign, office-supplies, toys, comics
- **Cách sửa:** Thêm/sửa/xóa sản phẩm trực tiếp trong object

#### `script.js` - Logic chính
- **Mục đích:** Xử lý tất cả logic của website
- **Chức năng chính:**
  - Load sản phẩm từ `data.js`
  - Xử lý giỏ hàng, wishlist
  - Tìm kiếm và lọc sản phẩm
  - Navigation và routing
  - Dynamic content loading
- **Key functions:** `loadProductDetails()`, `initializeHomePage()`, `searchBooks()`

#### `style.css` - Giao diện
- **Mục đích:** Styling và responsive design
- **Features:**
  - CSS Grid và Flexbox layout
  - Responsive design (mobile-first)
  - Product card styling
  - Navigation styling
  - Form styling
- **Key classes:** `.product-card`, `.product-grid`, `.nav-links`

#### `index.html` - Trang chủ
- **Mục đích:** Trang chủ với sản phẩm nổi bật
- **Sections:**
  - Hero banner
  - Featured products (8 sản phẩm)
  - New releases (8 sản phẩm)
  - Categories overview
- **Dynamic loading:** Sử dụng `script.js` để load content

### 🔧 File hỗ trợ

#### `load-components.js` - Load components
- **Mục đích:** Load header, footer và chatbot vào các trang
- **Function:** `loadComponents()` - Load tất cả components
- **Usage:** Được gọi trong mỗi trang HTML
- **Components:** Header, Footer, Chatbot với HTML được định nghĩa trong file

#### `checkout.js` - Thanh toán
- **Mục đích:** Xử lý logic thanh toán
- **Features:** Form validation, order processing

#### `auth.js` - Xác thực
- **Mục đích:** Đăng nhập/đăng ký
- **Features:** Form validation, user management

### 🖼️ Assets

#### `images/` - Thư mục ảnh
- **Sản phẩm:** `book-*.jpg` (ảnh sách)
- **UI:** `hero-banner.*`, `logo.png`, `icon-*.png`
- **Format:** JPG, PNG
- **Naming:** Theo pattern `book-{category}-{number}.jpg`

#### `info/` - Trang thông tin
- **Chính sách:** `chinh-sach-*.html`
- **Hướng dẫn:** `huong-dan-*.html`
- **Template:** `template.html` cho các trang info

### 📋 Info Pages (`info/`)

#### Chính sách và hướng dẫn
- **Chính sách:** `chinh-sach-*.html` - Các chính sách của website
- **Hướng dẫn:** `huong-dan-*.html` - Hướng dẫn sử dụng
- **Template:** `template.html` - Template cho các trang info

---

## 🚀 Quick Start

### 1. Chạy website

**Không cần server!** Chỉ cần:
- Mở file `index.html` trong browser
- Hoặc kéo thả `index.html` vào browser

*Hoặc dùng local server (tùy chọn):*
```bash
python -m http.server 8000
```

### 2. Thêm sách mới

**Cách 1: Thủ công**
- Mở `data.js`
- Tìm object `BOOK_DATABASE`
- Thêm entry mới theo format có sẵn

**Cách 2: Import từ file JSON** (Nếu có sẵn)
- Import dữ liệu từ file JSON có sẵn
- Convert sang format `data.js`

### 3. Thay đổi giao diện
Sửa file: `style.css`

### 4. Thêm chức năng
Sửa file: `script.js`

---

## 📝 Tính năng

### 🏠 Trang chủ
- ✅ Hero banner với call-to-action
- ✅ Sản phẩm nổi bật (8 sản phẩm)
- ✅ Sản phẩm mới (8 sản phẩm)
- ✅ Danh mục sản phẩm overview
- ✅ Responsive design

### 🛍️ Mua sắm
- ✅ Danh mục sách đa dạng (5 categories)
- ✅ Chi tiết sản phẩm với ảnh, mô tả, đánh giá
- ✅ Giỏ hàng với Local Storage
- ✅ Wishlist (yêu thích)
- ✅ Tìm kiếm sản phẩm theo tên, tác giả, tags
- ✅ Lọc theo giá, rating, category
- ✅ Quick view sản phẩm

### 💳 Thanh toán & Đơn hàng
- ✅ Trang thanh toán với form validation
- ✅ Xác nhận đặt hàng thành công
- ✅ Quản lý đơn hàng
- ✅ Lịch sử mua hàng

### 👤 Người dùng
- ✅ Đăng nhập/Đăng ký
- ✅ Hồ sơ người dùng
- ✅ Đánh giá sản phẩm
- ✅ Quản lý tài khoản

### 🔧 Quản trị
- ✅ Admin panel
- ✅ Quản lý sản phẩm
- ✅ Thống kê đơn hàng
- ✅ Chatbot AI hỗ trợ

### 🔧 Components & Maintainability
- ✅ Dynamic component loading (header, footer, chatbot)
- ✅ Centralized component management
- ✅ Easy maintenance và updates
- ✅ Consistent UI across all pages

---

## 🔐 Tài khoản mặc định

**Admin:**
- Email: `admin@bookself.com`
- Password: `admin@bookself.com`

**User:**
- Email: `user@bookself.com`
- Password: `user@bookself.com`

---

## 🔧 Component Architecture

### 📦 Dynamic Component Loading

**Website sử dụng centralized component management!**

Tất cả components được quản lý trong `load-components.js`:
- ✅ **Header** - Navigation, logo, search bar
- ✅ **Footer** - Links, contact info, social media
- ✅ **Chatbot** - AI assistant với floating UI

### 🎯 Ưu điểm

1. **Maintainability** - Chỉ cần sửa 1 file để update tất cả trang
2. **Consistency** - UI đồng nhất trên mọi trang
3. **Performance** - Load components dynamically
4. **Flexibility** - Dễ dàng thêm/sửa components
5. **Clean Code** - Không có hardcoded HTML trong các trang

---

## 🛠️ Tech Stack

### Frontend
- **HTML5** - Semantic markup
- **CSS3** - Modern styling với Grid/Flexbox
- **Vanilla JavaScript** - No frameworks, pure JS
- **Local Storage** - Lưu giỏ hàng và user data
- **Responsive Design** - Mobile-first approach

### Data Management
- **JSON** - Data format cho sản phẩm
- **Local Storage** - Lưu giỏ hàng và user data
- **Dynamic Loading** - Load components và content

### Tools & Utilities
- **Git** - Version control
- **VS Code** - Code editor
- **Browser DevTools** - Debugging
- **Local Server** - Development server

---

## 📊 Thống kê dự án

### Sản phẩm
- **Tổng:** 169 sản phẩm
- **Sách tiếng Việt:** ~100 sản phẩm
- **Sách ngoại văn:** ~40 sản phẩm
- **Văn phòng phẩm:** 15 sản phẩm
- **Đồ chơi:** ~10 sản phẩm
- **Truyện tranh:** ~4 sản phẩm

### Files
- **HTML:** 12 trang
- **JavaScript:** 9 files
- **CSS:** 1 file chính
- **Images:** 20+ ảnh
- **Total:** 40+ files

### Categories
- `vietnamese` - Sách tiếng Việt
- `foreign` - Sách ngoại văn
- `office-supplies` - Văn phòng phẩm
- `toys` - Đồ chơi
- `comics` - Truyện tranh

---

## 🚀 Deployment

### Local Development
```bash
# Clone repository
git clone <repo-url>
cd weebook

# Mở index.html trong browser
# Hoặc dùng local server
python -m http.server 8000
```

### Production
- Upload toàn bộ files lên web server
- Không cần database server
- Static website, không cần backend
- CDN cho images (tùy chọn)

---

## 📞 Support & Contributing

### Báo lỗi
- Tạo issue trên GitHub
- Mô tả chi tiết lỗi và steps to reproduce

### Đóng góp
- Fork repository
- Tạo feature branch
- Commit changes
- Tạo pull request

### Liên hệ
- Email: support@bookself.com
- GitHub: [BookSelf Team](https://github.com/bookself)

---

## 📄 License

MIT License - Xem file LICENSE để biết thêm chi tiết.

---

**Made with ❤️ by BookSelf Team**

*Website bán sách trực tuyến với 169 sản phẩm và centralized component management*
