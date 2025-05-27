# StudentAnalyzerProject

Đây là dự án Java đơn giản giúp phân tích điểm số học sinh, đếm số học sinh loại Giỏi và tính điểm trung bình hợp lệ.

## Cấu trúc dự án

```
StudentAnalyzerProject/
├── src/
│   ├── main/
│   │   └── java/
│   │       └── com/example/studentanalyzer/
│   │           └── StudentAnalyzer.java
│   └── test/
│       └── java/
│           └── com/example/studentanalyzer/
│               └── StudentAnalyzerTest.java
├── pom.xml
└── README.md
```

## Tính năng

- **countExcellentStudents(List<Double> scores):**  
  Đếm số học sinh có điểm >= 8.0, bỏ qua điểm không hợp lệ (<0 hoặc >10).

- **calculateValidAverage(List<Double> scores):**  
  Tính điểm trung bình của các điểm hợp lệ từ 0 đến 10.

## Yêu cầu

- Java 11 trở lên
- Maven 3.6 trở lên (để build và chạy test)
- Tùy chọn: VS Code với Java Extension Pack để phát triển dễ dàng

## Hướng dẫn build và chạy

### Biên dịch và chạy thủ công

1. Mở terminal, vào thư mục gốc dự án.
2. Biên dịch:

   ```bash
   mvn compile
   ```

3. Chạy chương trình chính:

   ```bash
   mvn exec:java -Dexec.mainClass="com.example.studentanalyzer.StudentAnalyzer"
   ```

Hoặc chạy trực tiếp phương thức `main` trong VS Code.

### Chạy test

Chạy toàn bộ test unit:

```bash
mvn test
```

## Lưu ý

- Các điểm số không hợp lệ (<0 hoặc >10) sẽ bị bỏ qua.
- Nếu danh sách điểm trống hoặc null, kết quả trả về là 0.

## License

Dự án này mã nguồn mở, có thể sử dụng tự do.
