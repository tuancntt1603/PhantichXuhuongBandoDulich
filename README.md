# 📊 Phân Tích Xu Hướng Bản Đồ Du Lịch với Spark  

## 📌 Giới Thiệu  
Dự án này sử dụng **Apache Spark** để phân tích dữ liệu du lịch, trực quan hóa xu hướng và đánh giá sự thay đổi lượng khách du lịch theo thời gian từ nhiều tệp CSV. Kết quả phân tích giúp đưa ra dự báo về xu hướng du lịch trong tương lai.  

- **Ngôn ngữ:** Python  
- **Công nghệ:** Spark, Matplotlib, Seaborn, GeoPandas, Folium  

## 🚀 Tính năng chính  
- 📂 Đọc và xử lý dữ liệu từ nhiều tệp CSV  
- 🧹 Làm sạch và tiền xử lý dữ liệu  
- 📈 Trực quan hóa xu hướng du lịch theo thời gian  
- 🔮 Dự báo xu hướng du lịch đến năm 2026  
- 🌍 Hiển thị bản đồ nhiệt về lượng khách du lịch  
- 📊 So sánh sự phát triển du lịch giữa các khu vực  

## 📂 Cấu Trúc Dự Án  
```bash
D:/BigData/Tourism/
├── Data/             # Chứa các tệp dữ liệu CSV
├── Results/          # Lưu kết quả phân tích và dự báo
├── Scripts/
│   ├── data_cleaning.py  # Tiền xử lý dữ liệu
│   ├── analysis.py       # Phân tích dữ liệu
│   ├── visualization.py  # Trực quan hóa dữ liệu
│   ├── forecasting.py    # Dự báo xu hướng
├── tourism_trend.ipynb  # Notebook chính
├── README.md           # Tài liệu hướng dẫn
```

## ❗ Lưu Ý  
- Đảm bảo **Apache Spark** được cài đặt đúng cách.  
- Nếu **Spark UI** không mở được, kiểm tra cổng mặc định của Spark.  
- Cài đặt các thư viện cần thiết trước khi chạy chương trình.  

## 🎯 Mục Tiêu  
✅ Hiểu cách sử dụng **Spark** với **Python**  
✅ Phân tích và trực quan hóa xu hướng du lịch  
✅ Dự báo xu hướng du lịch năm **2026**  
✅ So sánh lượng khách giữa các địa điểm du lịch  
✅ Hiển thị bản đồ du lịch động với **Folium**  

## ⚙️ Cài Đặt  
```sh
# Cài đặt thư viện nếu chưa có
!pip install pyspark matplotlib seaborn

# Khởi tạo SparkSession
spark = SparkSession.builder.appName("TourismData").getOrCreate()
```

## ▶️ Cách Chạy  
```sh
# Bước 1: Tải file lên Google Colab (Chạy lệnh này nếu bạn chưa tải file)
from google.colab import files
uploaded = files.upload()

# Bước 2: Đọc file CSV (Thay "your_file.csv" bằng tên file thực tế)
file_path = "/content/world_tourism_economy_data (1).csv"
df = spark.read.csv(file_path, header=True, inferSchema=True)

# Bước 3: Kiểm tra dữ liệu bị thiếu
print("📌 Kiểm tra dữ liệu bị thiếu:")
df.select([count(when(col(c).isNull(), c)).alias(c) for c in df.columns]).show()

# Hiển thị thống kê mô tả dữ liệu
print("📌 Thống kê mô tả dữ liệu:")
print(df_pandas.describe())
```
## 📝 License  
© 2025 **Nhóm 8 - Lớp CNTT 1603 🎓**  
🏢 **Trường Đại học Đại Nam**
