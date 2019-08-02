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



2, MapReduce:
 - Là mô hình xử lí dữ liệu, chia ra làm 2 giai đoạn:
    + Map: nhận input là các cặp giá trị (key, value) và đầu ra là các cặp giá trị (key',value') trung gian và thông báo cho reduce nhận dữ liệu
    + Reduce: nhận đầu vào là các cặp (key', value') trung gian và ghép nối lại thành tập key nhỏ hơn
 - MapReduce job là một đơn vị công việc mà client muốn thực hiện. Bao gồm: input data, chương trình mapreduce người dùng cài đặt và các thông số cấu hình. Hadoop thực hiện job bằng cách chia thành các task: maptask và reducetask
 - Có 2 loại node trong quá trình thực thi job là: jobTracker và taskTracker. JobTracker sẽ kết hợp các job chạy trên hệ thống và lập lịch cho tasktracker. Nếu 1 task lỗi, jobtracker sẽ lập lịch lại cho tasktracker khác.
 - Hadoop chia dữ liệu đầu vào cho mapreduce job thành các data block với kích thước xác định. Mỗi data block sẽ có một map task chạy các hàm map do client cài đặt.( với HDFS thì kích thước block data mặc định là 64 MB do mục đích của HDFS là quản lí các dữ liệu lớn)
 - Sơ đồ luồng dữ liệu của MapReduce cho một reduce task:
![alt text](https://bienuit.files.wordpress.com/2014/07/selection_003.png)

3, HDFS:
 - Là hệ thống lưu trữ chính dùng trong Hadoop, cung cấp khả năng truy cập với hiệu suất cao đến dữ liệu trên các cụm Hadoop.
 - HDFS tạo ra các phần nhỏ hơn của dữ liệu lớn và phân tán nó lên các node, mỗi phần dữ liệu nhỏ cũng đc sao chép nhiều lần trên nhiều node khác nhau. Chính vì vậy mà khi có lỗi ở một node thì hệ thống tự động dùng dữ liệu của node khác và tiếp tục xử lí dữ liệu.
 - Một HDFS cluster bao gồm 1 namenode là một node master quản lí hệ thống tệp tin, điều chỉnh truy cập đến các tập tin khác và các datanode bổ sung cho namenode, tác vụ chính của datanode là đọc và ghi tệp tin.
 - Kiến trúc của một HDFS:
![alt text](https://dinhnguyenngoc.files.wordpress.com/2014/07/hdfs_architecture.png?w=768&h=485) 

Spark Hadoop
![alt text](https://viblo.asia/uploads/e458bfb3-2876-490e-8456-d1b03f87600c.jpg)
