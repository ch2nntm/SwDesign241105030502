Kết quả bài thực hành Lab1:
--
3. Phân tích ca sử dụng Select Payment:
- Các lớp phân tích:
  + boundary: PaymentForm
  + control: PaymentController
  + entity: EmployeeEntity
- Biểu đồ tuần tự:
  ![Diagram](https://www.planttext.com/api/plantuml/png/j9J1IiD048Rl-nH3Jote2_GWXLBrwDNZkWtTq6HssMmEEOed4G--GQk8M2ZKeycXXvM-Hvx0Lt3Iq9hIfgBK71B-PUURVtw6V6RpJcIviN4Oi6Ze8nWLUOnnOPM1NgW3bNWUkr8nzhb9u88deOVsL9cG2ONMg61rrYrbu1b6ohV9khotb8ojD1oVL47GXgxCiti4BHUpnHW7O4c_2lfmb62L6sEpnQebH5ZJsd3kvzaDBglkmBht14G9t0GSjl_MsCGvoxEfJrSP3smT56MUJf41FTk8obnbQeKvkg_BChlF8ZGR9RlHObuGUNK61eL94ejPlOdDU2xT90QHfoynV3nGndoPxss5H3CNh3q9nsI04C_w1yJ1C_dkK9UBbcwiLqvebQvfSKoUlOb2fNFzXvY4zCjY2pXmZmZIZQXJqxe9La-EQ5r7FWobojCd_4M8knlySuOxiYaonJvZ7NhJF-GB003__mC0)
- Nhiệm vụ của từng lớp phân tích:
  + Boundary
    + PaymentForm: Đây là lớp giao diện mà nhân viên sử dụng để chọn phương thức thanh toán. PaymentForm sẽ yêu cầu nhân viên nhập phương thức thanh toán mong muốn, bao gồm các tùy chọn như "Pick Up", "Mail", và "Direct Deposit”.
  + Control
    + PaymentController: Điều khiển và xử lý logic của quy trình chọn phương thức thanh toán, nhận yêu cầu từ PaymentSelectionForm, xử lý và tương tác với các lớp Employee, PaymentMethod, và Database để cập nhật phương thức thanh toán của nhân viên.
  + Entity
    + EmployeeEntity: Chứa thông tin nhân viên như ID, tên và thông tin thanh toán hiện tại.
- Thuộc tính và quan hệ giữa các lớp phân tích:
 + PaymentForm (Boundary)
  + Thuộc tính:
    + selectedPaymentMethod: String – Phương thức thanh toán được chọn (có thể là "pick up", "mail", hoặc "direct deposit").
    + address: String – Địa chỉ nhận thư (chỉ dùng khi phương thức thanh toán là "mail").
    + bankName: String – Tên ngân hàng (chỉ dùng khi phương thức thanh toán là "direct deposit").
    + accountNumber: String – Số tài khoản ngân hàng (chỉ dùng khi phương thức thanh toán là "direct deposit").
  Quan hệ:
    + Tương tác với PaymentController để gửi thông tin lựa chọn thanh toán từ nhân viên.

+ PaymentController (Control)
  + Quan hệ:
    + Nhận dữ liệu từ PaymentForm để xử lý thông tin lựa chọn thanh toán.
    + Tương tác với Database để lưu thay đổi thông tin thanh toán của Employee.
    + Cập nhật thông tin về phương thức thanh toán trong lớp PaymentMethod

+ Employee (Entity)
  + Thuộc tính:
    + employeeId: Mã nhân viên (int) - xác định duy nhất mỗi nhân viên trong hệ thống.
    + employeeName: Tên nhân viên (String) - lưu trữ tên đầy đủ của nhân viên.
    + address: Địa chỉ (String) - địa chỉ nơi ở của nhân viên.
    + paymentClassification: Phân loại thanh toán (String) - loại hình thanh toán (ví dụ: theo giờ, cố định, hoa hồng).
    + baseSalary: Lương cơ bản (float) - mức lương cố định cho nhân viên có lương cố định.
    + commissionRate: Tỉ lệ hoa hồng (float) - phần trăm để tính lương dựa trên hoa hồng.
    + hourlyRate: Mức lương theo giờ (float) - mức lương mỗi giờ cho nhân viên làm theo giờ.
  + Quan hệ:
    + Liên kết với PaymentMethod để lưu trữ thông tin về phương thức thanh toán hiện tại của nhân viên.
    + Tương tác với PaymentController để cập nhật lựa chọn thanh toán.
- Biểu đồ lớp:
  ![Diagram](https://www.planttext.com/api/plantuml/png/R98nRWCX44LxJa6P57i1LvOYHt8H9_AUO1PcOsHW4CmMACh9KkH8kKBONOh5DkMVpyoR3ty_l_l447boLgIhyJ9IGYc4if2I_83iqFChHIU_X2mdeKN5g6lb3Vb2UYTxZiP_BWxGEc9AZJQ0lvx0OMjKYYRFfyaD63ULhblAsgHW8TT1xu4D-VJql59CWpFSBon5Bkht3V8BUOvaBSOA7YAfWjLmRnlCdYbeOAoMenzfs_ZWWgMCUF1iEDUkMCLZoS1uRhJxXHya4ohkFCACHi6CSvDTmXuinBoJeoLOXoXopfGhvCy5ULkvq1HjRjKQQRFV6i6weTW-TDSz257SIyNNPYB47hqkF-aV003__mC0)

- Giải thích:
  + PaymentForm: Lớp giao diện người dùng để nhân viên lựa chọn phương thức thanh toán. Nó chứa các thuộc tính để lưu trữ thông tin lựa chọn và các phương thức để hiển thị tùy chọn và gửi lựa chọn.
  + PaymentController: Lớp điều khiển logic xử lý thông tin từ PaymentForm. Nó xử lý việc lựa chọn phương thức thanh toán và cập nhật thông tin thanh toán của nhân viên.
  + Employee: Lớp thực thể đại diện cho nhân viên trong hệ thống. Nó lưu trữ thông tin nhân viên và có phương thức để cập nhật phương thức thanh toán.

4. Phân tích ca sử dụng Maintain Timecard:
- Các lớp phân tích:
  + boundary: TimecardForm,ProjectManagement
  + control: TimeCardController
  + entity: TimeCard, Employee, ProjectManagementDatabase
- Biểu đồ tuần tự:
  ![Diagram](https://www.planttext.com/api/plantuml/png/f5MxIiH05EtdAswfXJ-miAAkgnOg5XPQZhD34arcbib4I6qX8e8Mbi9k8OAme208IM4nud_C5_WBtcJTbsusqIqIvd7FkUVScPjyfcyheQPAHu5FI7ZY2L0ov4HxskUmGpsXyO5zB-0Dgbg4KAQbWcRGzcNCET1mE5xDTiYHZ4IBgdW8sP0g84mAhQG_N6pqvpvNX0lCDGeVpATbQEPRWuWz9OyvqpjKK8S7kBXEDJsYA7weuLS88MH2BYmjJmYjmQvharuRJar7WiPn2WpVzm4myoASXKKo7ZuE7rcgmJOYuYbmS3sRdWlGDkbwOrmZRCOuQVVlR3-LzOrjOV2Po6ZIo_yxQo3yIa1eqvj--WYqwGaNsgxf5JegFAfoma8eylxQAwUhTlevt47u7VYc4y1fniIgbYYd41cJdbteoI8DLgimbDZO_dYAvhYzfUWYuHaImqYz3fisxNdJBcszNgR-q3n6m6po485Jm5BHIP682bRUhstoga4ufXD_oy1l0dBH6DvlR7gBl0eR3nrfrypevX7bWUcolF-UMVaDcrNY-T0LmjOycxo9QQU7NZlOJRYMNkHrkChI4hB2HGj_8Ly0003__mC0)
-Nhiệm vụ của từng lớp phân tích:
  + Boundary:
    + TimeCardForm: Biểu mẫu giao diện mà nhân viên sử dụng để duy trì thông tin timecard.
    + ProjectManagement: Form hoặc giao diện dùng để lấy và hiển thị thông tin dự án từ ProjectManagementDatabase.
  + Control:
    + TimeCardController: Điều khiển logic của quy trình duy trì timecard, nhận yêu cầu từ TimeCardForm, xử lý và tương tác với các lớp entity.
  + Entity:
    + TimeCard: Chứa dữ liệu của timecard bao gồm ngày làm việc, số giờ, và thông tin dự án liên quan.
    + EmployeeEntity: Đại diện cho thông tin của nhân viên như ID, tên, và loại nhân viên (lương theo giờ, lương cố định, có hoa hồng).
    + ProjectManagement: Đại diện cho cơ sở dữ liệu chứa thông tin dự án mà timecard có thể cần tham chiếu.
- Thuộc tính và quan hệ giữa các lớp phân tích:
  + TimecardForm (Boundary)
    + Thuộc tính:
      + timecardId: Mã timecard (int)
      + entryDate: Ngày nhập dữ liệu (Date)
      + hoursWorked: Số giờ làm việc (float)
    + Quan hệ:
      + Gửi yêu cầu đến TimeCardController để lấy thông tin timecard.
      + Tương tác với Employee để nhận yêu cầu và hiển thị kết quả.
  + ProjectManagement (Boundary)
    + Thuộc tính:
      + projectId: Mã dự án (int)
      + projectName: Tên dự án (String)
    + Quan hệ:
      + Nhận yêu cầu từ TimeCardController để lấy thông tin dự án từ ProjectManagementDatabase.
      + Truyền tải thông tin dự án đến TimeCardController.
  + TimeCardController (Control)
    + Quan hệ:
      + Nhận yêu cầu từ TimecardForm để điều khiển quy trình xử lý thông tin timecard.
      + Truy cập TimeCard để truy xuất hoặc cập nhật dữ liệu timecard.
      + Tương tác với ProjectManagement để lấy thông tin dự án từ ProjectManagementDatabase.
  + TimeCard (Entity)
    + Thuộc tính:
      + timecardId: Mã timecard (int)
      + employeeId: Mã nhân viên (int, liên kết với Employee)
      + projectChargeNumber: Số dự án đã làm việc (int, liên kết với ProjectManagementDatabase)
      + hoursWorked: Số giờ đã làm (float)
      + overtimeHours: Số giờ làm thêm (float)
    + Quan hệ:
      + Liên kết với Employee để lưu trữ thông tin về số giờ đã làm của nhân viên.
      + Tương tác với TimeCardController để cung cấp dữ liệu về số giờ làm việc.
  + ProjectManagementDatabase (Entity)
    + Thuộc tính:
      + databaseId: ID của cơ sở dữ liệu (int)
      + chargeNumbers: Danh sách số dự án và thông tin liên quan (danh sách đối tượng)
    + Quan hệ:
      + Cung cấp thông tin về dự án cho ProjectManagement khi nhận yêu cầu từ TimeCardController.
      + Không cho phép cập nhật, chỉ có thể truy xuất thông tin.
  + Employee (Entity)
    + Thuộc tính:
      + employeeId: Mã nhân viên (int) - xác định duy nhất mỗi nhân viên trong hệ thống.
      + employeeName: Tên nhân viên (String) - lưu trữ tên đầy đủ của nhân viên.
      + address: Địa chỉ (String) - địa chỉ nơi ở của nhân viên.
      + paymentClassification: Phân loại thanh toán (String) - loại hình thanh toán (ví dụ: theo giờ, cố định, hoa hồng).
      + baseSalary: Lương cơ bản (float) - mức lương cố định cho nhân viên có lương cố định.
      + commissionRate: Tỉ lệ hoa hồng (float) - phần trăm để tính lương dựa trên hoa hồng.
      + hourlyRate: Mức lương theo giờ (float) - mức lương mỗi giờ cho nhân viên làm theo giờ.
    + Quan hệ:
      + Employee (Entity) lưu trữ thông tin nhân viên và liên kết với TimeCard để duy trì dữ liệu về thời gian làm việc và các dự án đã thực hiện.
      + TimecardForm nhận yêu cầu từ Employee (Actor) để duy trì và cập nhật timecard thông qua TimeCardController.
      + TimeCardController phối hợp các yêu cầu, giao tiếp với TimeCard và ProjectManagement để duy trì thông tin về dự án và số giờ làm việc.
      + Employee (Entity) lưu trữ thông tin nhân viên và liên kết với TimeCard để duy trì dữ liệu về thời gian làm việc và các dự án đã thực hiện.
        
- Biểu đồ lớp:
  ![Diagram]([https://www.planttext.com/api/plantuml/png/V9HBRi8m48RtEOMNxO8Bi482AbYqgaebreCz11S_el44AQfwiYvwf5wXDZYGG6WMaVoFu_-RX_Fx_JC93CIrDKNOQoV81omAQI04CRULyGtYtB7cHdmM8ZwOnQKQ2-sufxs0nR5OCMbN7WEW5648FQs2ngBZQRBGMos1jNUz7Hi8k083r8p5rdWucKXlhOwVUFS6ZDt8pjTachuw6ecMu5rRd0AfXyUZKbSgxko8Nss-hPOpvRYKSJcKQLUho7-WvEaEgCINscwGBi745jQUzgYwoFw0bCvVfF0jDQ7qf1QNRpDxfFHIH_orvjthoNSeWwbtJDuOf6CkyhoyS8z6BRoC7RggKOdSAZDWw5KksoxTrWzPFtco_nKmaZIpOwlI-twDCf_IeJBGNF65UcCr3_Kmqps3WnBJd2N-D52PIULbbqdsEdSUn4n060Kyj7ddUjmtp4PvAWO6vUgMP9jq6qhNNhbB7_BvAmQkmyduwbx6eMahKGmCG2SixiJl5wtejRLpLEU0uhO4FSzYWawb7ymV0000__y30000](https://www.planttext.com/api/plantuml/png/V5JBJiCm4BpdAtA4Gt-Wfqej20uWH94uR-rjQl0ZMcygHOWluy0dyGlOgKESDAM7Ifv9TcPdr_dv-bvv1kB6wCA_ArkIyrWKGeFtvOsfjMiHRomhRikFeWm_JE2zN9RAyWXx18FBSikaRDKH82MXzoEiXjQWvNMKK7ibW9MpeoTsu74B6gXTbdlju2GYd34glEBiCp3cpC4rfDif6hHVbC4raBowxf2cbk6P3FpiE-snr2E7emZ7kHvph2RtXeBN1w0A7nkpGnh8wCg_Edf7cTjoHwHO_oxIEK4e7CcxuQtaElXpGWNZhueFJoV5EUzhPvcSraYfY-1EXF0d8LJ8FR81Xb4qgVgztRivXLj7vh-4WdwxwQOG_o-7i5Xqd5I-rj1E_FbcPnJF3IcvUm0B5SOLYlxZhYHFCXrpJs8qchyTImu80u37lk-KnsN18TWkflDDc5o091CNlRBzRHhcaEfl6RZn9-79bLiiXjKiPWQTyHVeow4Lex5cbR82nNa48ql52gqCtuvV0000__y30000)

5.Hợp nhất kết quả phân tích
- Biểu đồ lớp:
  ![Diagram](https://www.planttext.com/api/plantuml/png/l5KxRkGm3Err2fUROYwGAi0aGL8a6-m4ICsHE1xjw6D8T01ZiITBaIFb2YlPCYnfFC1MSM50ZpJv-4ZANn-VDvx0KQyLyoTf6cSzCiOLUD-ymA3HqBrrkld3cl1uLCW9HR8y8Hsjk6vsvAHfHmyGmg7t1RO7Ste6ZQKZvxOtzDphFRhCijcCPY5zfs18YNvs9AtnFwuc5lrUIzgDN08SqByLvQqrvAnIw1BnpbaUQ1Myym3Hf-y442QNHtEmtnBuJdVA3eXtXYGDAIecy368AmqLsBcIAv9tYMvC8G-IGwHJDSNZ3XIuuRevA0jJ4cwrbk4JQtu5ohdbQ7kdXXeDkL-bnYquKHIx2XOYvHhCtgbw2aSUZclLvrZG_dSGUdi4r-8yIBCnylLlrfrGv8JjExeO_o6QSuD3RfruMBvAr0C_osLW_oRf-39bNED-QJ8g9Lga6Ra5WbAVANez8RD_jeUh2eNym-tOd_Y-B4AvOHM_QRSoSDc0YTqJ66WnzZ7oZrEKE8bqp3dneZNrZZiC0BxFTISzBYTSX1rbEf-4QZLIchW2hPdtREb3YhyZeDvFYQjbt6oMqMGhZVuF-sNLMD7NB5GMW9rha3co_8AEkUexYftVMi6jB98nTeD6n1z0UFu1003__mC0)
