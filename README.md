**Đề bài:** 

I. Phần 1:
Tìm hiểu quá trình vận chuyển hàng hóa (parcel) của Ryo kể từ lúc nhận đơn hàng (First mile) cho tới lúc giao hàng/trả hàng thành công (Last mile), tính toán các KPI của trạm (hub), tài xế (driver), và hiệu quả giao hàng đối với shop bán hàng (shipper). 
Thực hiện phân tích về xu hướng mua sắm, theo dõi tiến độ và tình trạng đơn hàng, và các vấn đề liên quan đến hiệu suất giao hàng của Ryo nhằm giúp công ty tìm ra những vấn đề tồn đọng và rủi ro liên quan đến quá trình giao hàng, đồng thời đưa ra các đề xuất để cải thiện chiến lược vận chuyển, phân phối nguồn lực và nâng cao hiệu suất doanh nghiệp.

**Quy định hoạt động của Ryo:**
- Những đơn hàng được tạo trước 16 giờ mỗi ngày, phải được pickup trong ngày. Đối với những đơn được tạo sau 16 giờ thì phải pickup được trong ngày làm việc hôm sau, không áp dụng với chủ nhật và những ngày nghỉ lễ. Đây gọi là *sla_pickup*.
- Những đơn hàng đến trạm (dest_hub_datetime) trước 11 giờ thì phải giao hàng thành công trong ngày hôm đó. Nếu đơn hàng đến trạm sau 11 giờ thì cần giao thành công trong ngày tiếp theo(delivery_success_datetime and granular_status = ‘Completed’), không áp dụng với chủ nhật và những ngày nghỉ lễ. Đây gọi là *sla_delivery*.

Đưa ra các đề xuất để cải thiện chiến lược vận chuyển, phân phối nguồn lực và nâng cao hiệu suất cho Ryo.

**1. Phòng Vận Hành**

**Mục tiêu:** Theo dõi tiến độ đơn hàng và phân tích hiệu suất giao hàng, theo dõi và đánh giá hiệu suất của các nhân viên giao hàng. Tìm hiểu các lý do dẫn đến hiệu suất kém, các rủi ro liên quan đến quá trình giao hàng, nhân viên giao hàng, người bán, khu vực giao nhận đơn hàng... để đánh giá tỷ lệ pick up đúng hạn vàtỷ lệ giao hàng thành công của trạm/khu vực/tỉnh, từ đó nhận xét tình hình vận chuyển và đề xuất chiến lược phù hợp cho Ryo.

**Yêu cầu:**

- Phân tích số lượng đơn hàng theo trạng thái vận chuyển và các khoảng thời gian (theo năm, quý, tháng).
- Theo dõi hiệu suất giao hàng nói chung và hiệu suất của từng tài xế thông qua các KPI như: tỷ lệ giao hàng thành công, tỷ lệ đơn hàng bị hủy, tỷ lệ giao hàng đúng hạn và thời gian giao hàng trung bình.
- Hãy tạo cột sla_pickup và tính toán tỷ lệ pick up đúng hạn (trước sla_pickup) của mỗi trạm và tìm ra những trạm, khu vực và tỉnh đang thực hiện không tốt. Tìm hiểu (hoặc đặt giải thuyết lý do hợp lý) và đề xuất giải pháp cho Ryo dựa trên một số yếu tố bắt buộc như: Parcel Size, Shop (Shipper), Region, Driver Weight.
- Hãy tạo cột sla_delivery và tính toán tỷ lệ giao hàng thành công (không tính trả hàng thành công) đúng hạn (trước sla_delivery) của mỗi trạm, mỗi tài xế và mỗi shop. Từ những lý do được thể hiện trong bộ dữ liệu về trường hợp giao hàng không đúng hạn cùng những đặc tính khác hãy phân tích cho Ryo biết lý do (hoặc giả thuyết các trạm đang hoạt động không ổn định) để đề xuất giải pháp cho Ryo thực hiện các hành động phù hợp.

**2. Phòng Kinh Doanh**
**Mục tiêu:** Xây dựng báo cáo để nắm bắt xu hướng mua sắm và phân tích hành vi của khách hàng là người mua (buyer) đối với shipper, theo dõi tình trạng, lý do và xu hướng hủy đơn hàng theo khu vực, hình thức thanh toán, độ trễ...Đồng thời đưa ra sự đánh giá về xu hướng mua sắm theo vị trí địa lý và trong các dịp đặc biệt. Từ đó, đưa ra các chiến lược thúc đẩy bán hàng và mở rộng thị trường hiệu quả.

**Yêu cầu:**

- Theo dõi lý do hủy đơn nói chung và lọc theo hình thức thanh toán, giá trị COD, khu vực, v.v
- Đánh giá và so sánh xu hướng mua sắm theo vị trí địa lý, theo các dịp giảm giá (ngày Lễ lớn, Double day).
- Hãy phân tích xu hướng hàng hóa (parcels) mà Ryo nhận được trong thời gian qua để Phòng Kinh doanh nắm được xu hướng từ đó tìm kiếm thêm khách hàng sử dụng dịch vụ của Ryo.
- Phân tích rõ sản phẩm (items) tập trung nhiều tại từng khu vực cụ thể từ đó đưa ra đề xuất tập trung phát triển mở rộng khu vực kinh doanh.
- Phân loại nhóm khách hàng, mô tả đặc điểm của họ và đề xuất thêm chiến lược mở rộng thị trường khác.

II. Phần 2:
Yêu cầu: Trong thời gian sắp tới, Ryo chuẩn bị cho chiến lược mở rộng thị trường cả chiều sâu lẫn chiều rộng (có thể mở thêm trạm, gia tăng liên kết với các sàn TMĐT để mở rộng khách hàng). Dựa vào dữ liệu đã cung cấp cùng với bảng giá mới được thiết kế cho năm 2023, hãy giúp Ryo có cái nhìn rõ hơn về bối cảnh tương lai để chuẩn bị tốt nhất.
Ryo vừa ký hợp đồng với một vài đối tác tiềm năng, có thể thúc đẩy tăng trưởng 71% lượng đơn hàng ngày vào đầu năm 2023.

Với năng lực hiện tại của các trạm:
- Mỗi tài xế có thể xử lý giao trả hàng trung bình khoảng 40 đơn hàng/ngày.
- Mỗi trạm chỉ nên có khoảng 7 nhân sự, nếu trạm quá tải và thừa nhân sự, cần phải mở thêm trạm tại khu vực khác.
- Trạm có thể hoạt động từ 8h sáng đến 8h tối.

Với bảng giá mới được cung cấp đính kèm trong dữ liệu.
1. Hãy dự báo sản lượng và doanh thu năm 2023 theo mức độ chính xác gần nhất mà phương pháp bạn chọn có thể cung cấp được (không giới hạn thời gian là số tuần, tháng hay thời gian cao điểm). Giải thích sự lựa chọn của mình để Ryo tin tưởng thực hiện việc mở rộng thị trường phù hợp.
2. Theo dự báo của bạn, với số lượng trạm hiện tại của Ryo thì mỗi trạm nên có tối thiểu bao nhiêu tài xế để xử lý được đơn hàng gia tăng trong thời gian tới? Nếu trạm đã quá tải và cần đóng hoặc mở thêm trạm thì khu vực nào là cần ưu tiên thực hiện và tại sao? Tối ưu hóa mạng lưới trạm giao hàng để tối ưu hiệu suất hoạt động của công ty.
3. Hãy trình bày những rủi ro tiềm ẩn có thể xuất hiện trong chiến lược mở rộng thị trường và trạm giao nhận của Ryo, đồng thời đề xuất chiến lược giảm thiểu rủi ro.
