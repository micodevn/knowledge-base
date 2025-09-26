# Nguyên tắc ACID trong Cơ sở dữ liệu

## 1. Atomicity (Tính nguyên tử)
**Mô tả:**  
Đảm bảo rằng tất cả các lệnh thực thi trong một giao dịch (transaction) phải được thực hiện thành công toàn bộ (commit), nếu có lỗi nào xảy ra, thì toàn bộ dữ liệu của giao dịch đó sẽ bị rollback

**Ví dụ:**  
Giao dịch chuyển tiền từ tài khoản A sang tài khoản B bao gồm hai thao tác:
- Trừ tiền từ tài khoản A.
- Cộng tiền vào tài khoản B.

Tính nguyên tử đảm bảo rằng nếu thao tác trừ tiền thành công nhưng thao tác cộng tiền thất bại (ví dụ, do lỗi hệ thống), thì thao tác trừ tiền cũng sẽ được hoàn tác

---

## 2. Consistency (Tính nhất quán)
**Mô tả:**  
Thuộc tính này đảm bảo rằng mọi dữ liệu được ghi vào CSDL phải tuân theo tất cả các quy tắc đã được định nghĩa, 
bao gồm các ràng buộc (constraints), khóa (keys), trigger và logic nghiệp vụ

**Ví dụ:**
- Logic nghiệp vụ là số dư tài khoản không được âm. 
- Nếu một giao dịch rút một số tiền lớn hơn số dư hiện có, giao dịch đó sẽ không được thực hiện
---

## 3. Isolation (Tính cô lập)
**Mô tả:**  
Thuộc tính này đảm bảo rằng các giao dịch đồng thời được thực thi một cách độc lập với nhau.
Kết quả trung gian của một giao dịch chưa hoàn thành (uncommitted) không được hiển thị cho các giao dịch khác.
Một giao dịch chỉ được lấy dữ liệu đã được commit

**Ví dụ:**  
Nếu tài khoản A có 100 đồng và có hai giao dịch đồng thời:
- **Giao dịch 1:** Rút 30 đồng.
- **Giao dịch 2:** Kiểm tra số dư để xem có đủ để mua một món hàng giá 80 đồng không.

Tính cô lập đảm bảo rằng Giao dịch 2 sẽ không thấy trạng thái tài khoản A là 70 đồng (sau khi Giao dịch 1 trừ tiền nhưng chưa commit) và đưa ra quyết định sai lầm. Giao dịch 2 sẽ thấy số dư là 100 đồng (trước Giao dịch 1) hoặc 70 đồng (sau khi Giao dịch 1 đã commit hoàn toàn), tùy thuộc vào mức độ cô lập và thời điểm thực thi.

---

## 4. Durability (Tính bền vững)
**Mô tả:**  
Thuộc tính này đảm bảo rằng một khi một giao dịch đã được xác nhận (committed), dữ liệu sẽ được bảo toàn kể cả khi hệ thống gặp sự cố (ví dụ: mất điện, lỗi phần cứng, hoặc hệ thống khởi động lại) thì dữ liệu vẫn được bảo toàn

**Ví dụ:**  
Sau khi giao dịch chuyển tiền từ tài khoản A sang tài khoản B hành công (committed), số dư mới của cả hai tài khoản phải được lưu trữ vĩnh viễn. 
Ngay cả khi máy chủ cơ sở dữ liệu bị sập ngay sau đó, khi khởi động lại, dữ liệu vẫn phải dữ nguyên như cũ
