# StudentAnalyzerProject

Đây là dự án Java đơn giản giúp phân tích điểm số học sinh, đếm số học sinh loại Giỏi và tính điểm trung bình hợp lệ.

## 📁 Cấu trúc dự án

StudentAnalyzerProject/
├── src/
│ ├── main/
│ │ └── java/
│ │ └── com/example/studentanalyzer/
│ │ └── StudentAnalyzer.java
│ └── test/
│ └── java/
│ └── com/example/studentanalyzer/
│ └── StudentAnalyzerTest.java
├── pom.xml
└── README.md

r
Sao chép
Chỉnh sửa

## 🚀 Tính năng

- **countExcellentStudents(List<Double> scores)**  
  Đếm số học sinh có điểm >= 8.0, bỏ qua điểm không hợp lệ (<0 hoặc >10).

- **calculateValidAverage(List<Double> scores)**  
  Tính điểm trung bình của các điểm hợp lệ từ 0 đến 10.

## 🛠️ Yêu cầu

- Java 11 trở lên
- Maven 3.6 trở lên (để build và chạy test)
- Tùy chọn: VS Code với Java Extension Pack để phát triển dễ dàng

---

## ⚙️ Hướng dẫn build và chạy

### Biên dịch và chạy thủ công

1. Mở terminal, vào thư mục gốc dự án.
2. Biên dịch:

   ```bash
   mvn compile
Chạy chương trình chính:

bash
Sao chép
Chỉnh sửa
mvn exec:java -Dexec.mainClass="com.example.studentanalyzer.StudentAnalyzer"
Hoặc chạy trực tiếp phương thức main trong VS Code.

✅ Chạy test
Chạy toàn bộ test unit:

bash
Sao chép
Chỉnh sửa
mvn test
📊 Đo kiểm thử (Coverage)
Sử dụng plugin JaCoCo để đo độ bao phủ kiểm thử.

Chạy lệnh:

bash
Sao chép
Chỉnh sửa
mvn clean test
Kết quả báo cáo: mở file:

bash
Sao chép
Chỉnh sửa
target/site/jacoco/index.html
Coverage đạt: 100%

🐞 Các lỗi phát hiện và khắc phục
✅ Lỗi phát hiện:

Thiếu kiểm thử với tham số đầu vào null trong các phương thức.

Khi chạy mvn test ban đầu, coverage chỉ đạt 92% do bỏ sót branch scores == null.

✅ Cách khắc phục:

Thêm kiểm thử null trong file StudentAnalyzerTest.java:

java
Sao chép
Chỉnh sửa
@Test
public void testNullInput() {
    StudentAnalyzer analyzer = new StudentAnalyzer();
    assertEquals(0, analyzer.countExcellentStudents(null));
    assertEquals(0.0, analyzer.calculateValidAverage(null));
}
Commit kèm Issue để tự động đóng:

bash
Sao chép
Chỉnh sửa
git commit -m "test: add test for null input to fix #5"
✅ Kết quả: Coverage đã tăng lên 100%.

ℹ️ Lưu ý
Các điểm số không hợp lệ (<0 hoặc >10) sẽ bị bỏ qua.

Nếu danh sách điểm trống hoặc null, kết quả trả về là 0.

📄 License
Dự án này mã nguồn mở, có thể sử dụng tự do.
