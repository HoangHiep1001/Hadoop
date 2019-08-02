# Hadoop
![alt text](https://dinhnguyenngoc.files.wordpress.com/2014/07/what_is_hadoop.png?w=587&h=139)


1, Hadoop:
 - Cung cấp một nền tảng phân tán để quản lí và lưu trữ bigdata, lấy cảm hứng từ MapReduce và Google File System(GFS)
 - Điểm mạnh của Hadoop là cung cấp độ tin cậy và tính sẵn sàng cao
 - Hadoop bao gồm 2 thành phần chính:
     + MapReduce: chia dữ liệu lớn thành các đoạn nhỏ hơn và phân tán nó trên nhiều máy chủ.
     + HDFS: Hệ thống file phân tán chạy trên các phần cứng thông thường có khả năng chịu ỗi cao và triển khai trên các phần cứng rẻ tiền
 - Bên cạnh đó còn có các modul:
      + Hadoop Common: các tiện ích thông dụng cho modul khác Hadoop
      + Hadoop Yarn: nền tảng cho lập lịch và quản lí tài nguyên cluster.
 - Một cụm Hadoop gồm 1 master node và các node worker. Chia làm 2 lớp chính: lớp MapReduce chứa JobTracker, TaskTracker và lớp HDFS chứa: namenode và datanode.
 - Lợi ích khi dùng Hadoop:
   + Có thể thêm node mới khi cần
   + Không cần các phần cứng đặc biệt
   + Khi 1 node lỗi thì hadoop tự chuyển sang node khác và xử lí dữ liệu tiếp 
