Bước 	PMO	PO	DE
Bước 1			Xây dựng các templates
  Push lên Github Repository
  Cập nhật danh sách các templates hiện có trên Miro.
  Note:
  Templates Repository có type là "Public" repo
  Repository có tên bắt đầu bằng "template-....."

Bước 2	Trao đổi với khách hàng để tìm hiểu nhu cầu
  Xây dựng API Documents bằng Tool trên DeepNote hoặc bằng công cụ khác
  Trao đổi với PO để làm rõ API Documents và chỉnh sửa/hoàn thiện thêm nếu cần
	Trao đổi với PMO để làm rõ và góp ý thêm về API Documents
	
Bước 3	Tạo Repository và Branches mới trên Github:
  Truy cập và signin tài khoản Github 
  Chuyển sang Organization "Vietnam-Petroleum-Institute"
  Trong "Vietnam-Petroleum-Institute". Tạo một Repository mới bằng cách import từ Template. Hướng dẫn cách tạo tại đây
  Tạo 2 branch có tên là "colab" và "production". Hướng dẫn cách tạo tại đây
  Phân quyền truy cập Repository cho PO và DE. Hướng dẫn phân quyền tại đây
  Thông báo và gửi link Repository vừa tạo cho PO và DE
		Kết nối branch "Production" và "Colab" của Repo với Azure và cấu hình CI/CD:
  Hướng dẫn Deploy lên Azure Container App tại đây
  Hướng dẫn Deploy lên Azure Webapp tại đây
  Kiểm tra cấu hình CI/CD để đảm bảo Github Action chạy thông suốt:
  Test thử API sau khi deploy xem có kết nối không
  Cập nhật code trên Branch xem Github Action có chạy thành công không
  Gửi Base URL của API cho PMO và PO

Bước 4		Xác định rõ nhu cầu cần giải quyết, các chức năng, tính năng và thông tin API cần cung cấp:
  Nhu cầu cần giải quyết: Trước hết, bạn cần hiểu rõ vấn đề hoặc nhu cầu mà API sẽ đáp ứng. Đây có thể là việc cung cấp dữ liệu từ một cơ sở dữ liệu, thực hiện một hành động cụ thể trong một ứng dụng hoặc bất kỳ nhiệm vụ cụ thể nào khác.
  Chức năng và tính năng: Đây là những gì API có thể thực hiện. Ví dụ: một API cho một mảnh ghép số dự báo dữ liệu dầu khí có thể có chức năng tự lấy dữ liệu đầu vào từ cơ sở dữ liệu, xác minh người dùng hoặc tra cứu thông tin cơ sở dữ liệu.
  Thông tin API cần cung cấp: Điều này liên quan đến dữ liệu mà API sẽ trả về cho người dùng. Trong ví dụ về ứng dụng mảnh ghép số dự báo, thông tin có thể bao gồm chi tiết các trường dữ liệu, thông tin thống kê dữ liệu bên trong, và các thông tin khác.
  Xác định số lượng endpoint, phương thức HTTP (Post, Get...) và trả dữ liệu:
  Số lượng endpoint: Mỗi endpoint trong một API thường tương ứng với một chức năng cụ thể hoặc một tập dữ liệu. Ví dụ: trong một API quản lý người dùng, có thể có endpoints riêng biệt cho việc tạo người dùng mới, cập nhật thông tin người dùng, và lấy danh sách người dùng.
  Phương thức HTTP: Đây là các phương thức được sử dụng để tương tác với API. Các phương thức thông thường bao gồm:
  GET: Để truy xuất dữ liệu
  POST: Để tạo dữ liệu mới
  PUT hoặc PATCH: Để cập nhật dữ liệu hiện có
  DELETE: Để xóa dữ liệu
  Trả dữ liệu: Điều này liên quan đến cách dữ liệu được trả về từ API - ví dụ, dưới dạng JSON hoặc XML. Điều này cũng bao gồm việc xác định cấu trúc của dữ liệu, như các trường thông tin và kiểu dữ liệu của từng trường.
	

Bước 5 và Bước 6: Mở Project và test API trên Codespace hoặc VSCode
  Hướng dẫn mở Project và test API trên Codespace
  Hướng dẫn mở Project và test API trên VSCode
  Góp ý để PO hoàn thiện API nếu có
  	Xây dựng các functions theo Workflow đã thiết kế (trên Fabric Notebook hoặc Codespace hoặc VSCode):
  Hướng dẫn tạo Fabric Notebook tại đây
  
  Hướng dẫn tạo Codespace từ Github Repository tại đây
  
  Hướng dẫn clone Github Repository và mở bằng VSCode
  
  Import các functions đã tạo vào API Project và push source code từ API Project lên Github Repository
  Hướng dẫn Import các functions đã tạo vào API Project và push source code từ API Project lên Github Repository - VSCode, Codespace


  Hướng dẫn với Fabric Notebook
  Hướng dẫn với Codespace
  Hướng dẫn với VSCode
  - Test API: Hướng dẫn test API trên Codespace/VSCode
    Link Video hướng dẫn: https://drive.google.com/file/d/1VxgaUy9vpDQWkPguyAMFum0gvPNjFe-0/view
    link download Docker: https://docs.docker.com/get-docker/
    Link download Postman: https://www.postman.com/downloads/
  Câu lệnh được dùng để đóng Docker Image và chạy Docker Container:
      - Docker Image (lưu ý thay ** bằng tên image cụ thể (tên bằng tiếng Anh, không có khoảng trắng):
      docker build -t <image_name> .
      - Chạy Docker Container từ Image vừa tạo:
      docker run -p 8017:3500 <image_name> uvicorn app.api:app --reload --host 0.0.0.0 --port 3500
  Gỡ lỗi, hoàn thiện API
  Thông báo cho PMO để test API trên Codespace hoặc VSCode Live Share
  Hướng dẫn sử dụng VSCode Live Share
	

Bước 7 và Bước 8: 
  Trên Github Repository, merge branch "colab" với branch "production" (Hướng dẫn merge 2 branch tại đây)
  Kiểm tra quá trình CI/CD tự động update code lên Azure có thành công hay không (Hướng dẫn kiểm tra tại đây)
  Nếu có lỗi trong quá trình CI/CD, thông báo DE được hỗ trợ
  Nếu CI/CD thành công, test API theo Base URL đã được DE cung cấp ở Bước 3
  		Hỗ trợ PMO để kiểm tra lỗi trong quá trình CI/CD hoặc các lỗi khác trong quá trình test API

Bước 9	Xây dựng các Policy sử dụng API và gửi cho DE:
  Những ai được cấp Key truy cập, thời gian sử dụng của mỗi Key,...
  Giới hạn lượng truy cập nếu có
  Test API sau khi đã cấu hình trên APIM theo các API mà DE cung cấp
  Góp ý để DE chỉnh sửa hoàn thiện nếu cần
  		Cấu hình APIM để kết nối với Azure WebApp/ContainerApp (Hướng dẫn tại đây)
  Phân quyền, cấp key truy cập, thêm Policy kiểm soát lượng truy cập cho từng đối tượng/khách hàng theo yêu cầu của PMO:
  Hướng dẫn cấp key truy cập API
  Hướng dẫn thêm Policy kiểm soát lượng truy cập API
  Test API sau khi cấu hình để kiểm tra độ ổn định, tốc độ, khả năng kiểm soát lưu lượng truy cập,... đã đáp ứng với yêu cầu của PMO hay chưa
  Gửi PMO các API sau khi cấu hình

Bước 10	Gửi các API chính thức (đã cấu hình trên APIM) và Key truy cập cho khách hàng
  Nhận phản hồi từ khách hàng, đánh giá và trao đổi với PO/DE để hoàn thiện nếu cần

Link chi tiết các bước: https://miro.com/app/board/uXjVM90twxg=/?share_link_id=568007571414
