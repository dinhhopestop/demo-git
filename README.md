# Swagger Demo API

Đây là một ứng dụng demo đơn giản sử dụng Express.js và Swagger để tạo tài liệu API tự động.

## Giới thiệu (Introduction)

Project này demo cách sử dụng Swagger/OpenAPI để tạo tài liệu API tương tác. Swagger UI cho phép bạn:
- Xem tất cả các API endpoints
- Thử nghiệm API trực tiếp từ trình duyệt
- Xem request/response schemas
- Hiểu cách sử dụng API một cách trực quan

## Cài đặt (Installation)

1. Cài đặt Node.js dependencies:
```bash
npm install
```

## Chạy ứng dụng (Running the application)

Khởi động server:
```bash
npm start
```

Hoặc:
```bash
node server.js
```

Server sẽ chạy tại `http://localhost:3000`

## Truy cập Swagger UI

Sau khi server đã chạy, mở trình duyệt và truy cập:

```
http://localhost:3000/api-docs
```

Bạn sẽ thấy giao diện Swagger UI với tất cả các API endpoints được document.

## API Endpoints

### Welcome
- `GET /` - Welcome message

### Users
- `GET /api/users` - Lấy danh sách tất cả users
- `GET /api/users/:id` - Lấy thông tin user theo ID
- `POST /api/users` - Tạo user mới

### Products
- `GET /api/products` - Lấy danh sách tất cả products

## Cách sử dụng Swagger UI

1. Truy cập http://localhost:3000/api-docs
2. Bạn sẽ thấy danh sách các API endpoints
3. Click vào endpoint bất kỳ để xem chi tiết
4. Click nút "Try it out" để thử nghiệm API
5. Điền thông tin cần thiết (nếu có)
6. Click "Execute" để gửi request
7. Xem kết quả trả về

## Công nghệ sử dụng (Technologies)

- **Express.js** - Web framework cho Node.js
- **Swagger JSDoc** - Tạo Swagger specification từ JSDoc comments
- **Swagger UI Express** - Hiển thị Swagger UI trong Express app

## Cấu trúc project

```
.
├── server.js          # Main application file với API endpoints và Swagger annotations
├── package.json       # Node.js dependencies
├── .gitignore        # Git ignore file
└── README.md         # Documentation (file này)
```

## Swagger Annotations

Các API endpoints được document bằng cách sử dụng JSDoc comments với Swagger/OpenAPI tags. Ví dụ:

```javascript
/**
 * @swagger
 * /api/users:
 *   get:
 *     summary: Get all users
 *     description: Retrieve a list of all users
 *     responses:
 *       200:
 *         description: A list of users
 */
app.get('/api/users', (req, res) => {
  // Implementation
});
```

## Mở rộng (Extending)

Để thêm API endpoint mới với Swagger documentation:

1. Viết JSDoc comment với @swagger tag
2. Định nghĩa endpoint details (path, method, parameters, responses)
3. Implement endpoint handler
4. Restart server
5. Swagger UI sẽ tự động cập nhật

## License

MIT
