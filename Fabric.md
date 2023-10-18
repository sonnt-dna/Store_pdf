QUY TRÌNH TRIỂN KHAI SẢN PHẨM SỐ TRÊN MICROSOFT FABRIC

I. Thuật ngữ
1. Workflow: quy trình làm việc.
2. Workspace: không gian làm việc, ở đây là không gian làm việc của mỗi dự án trên nền tảng Microsoft Fabric.
Tham khảo thêm về Microsoft Fabric Workspace tại link: https://learn.microsoft.com/en-us/fabric/get-started/workspaces
3. Domain workspace: không gian làm việc chứa dữ liệu gốc cần sử dụng của dự án, ở đây là không gian làm việc trên nền tảng Microsoft Fabric.
4. Collab workspace: không gian làm việc cộng tác giữa các thành viên thực hiện/hỗ trợ thực hiện sản phẩm số, ở đây là không gian làm việc trên nền tảng Microsoft Fabric.
5. Production workspace: không gian làm việc chứa sản phẩm số cuối cùng có thể chia sẻ đến khách hàng, ở đây là không gian làm việc trên nền tảng Microsoft Fabric.
6. PO - Project owner: chủ nhiệm dự án.
7. PMO – Product management office: nhân sự bộ phận quản lý sản phẩm.
8. DE – Data engineer: kỹ sư dữ liệu.
9. Problem statement: yêu cầu cần đạt của sản phẩm.
10. Solution map: sơ đồ thiết kế sản phẩm.

II. Workflow[MP1] cơ bản trên Fabric
1. Các bước thực hiện
Để các bước triển khai sản phẩm số rõ ràng và dễ dàng cộng tác hơn, workflow cơ bản trên Fabric được xây dựng với 3 lớp: lớp dữ liệu, lớp phân tích, lớp người sử dụng. 
- Lớp dữ liệu: Lớp dữ liệu đóng vai trò nền tảng và kết nối giữa người sử dụng và nhà phân tích. Ở lớp này, các nhiệm vụ liên quan đến luồng dữ liệu, xử lý số liệu đầu vào, xây dựng cơ sở dữ liệu, lưu trữ dữ liệu, xây dựng nền tảng, kết nối người dùng, quản lý quyền truy cập được thực hiện để đảm bảo dữ liệu cho sản phẩm số.
- Lớp phân tích: Là lớp mà người xây dựng lên sản phẩm số thực hiện các công việc, thao tác liên quan đến các phân tích chuyên sâu như xây dựng các mô hình dự báo với machine learning,... 
- Lớp người sử dụng: Tại đây yêu cầu của người dùng được định hình và sản phẩm hay giải pháp cuối cùng cũng được chỉ ra. Đâu là đầu vào cần phải có để triển khai được sản phẩm và đâu là sản phẩm mà người dùng hay khách hàng nhận về sau khi đi qua các bước xử lý trung gian.
      
Hoàn thiện một sản phẩm số yêu cầu người xây dựng thực hiện 5 – 7 bước tuỳ theo nhu cầu của dự án.
Bước 1: Người xây dựng sản phẩm số lấy dữ liệu từ các nguồn dữ liệu (Sharepoint, Dataverse for Teams,…) và đưa vào các công cụ của nền tảng Microsoft Fabric như Dataflow Gen 2 và Notebook. Ở bước này, các công cụ trên sẽ hỗ trợ biến đổi, làm sạch dữ liệu.
Bước 2: Dữ liệu đã xử lý, biến đổi được người xây dựng sản phẩm số đưa vào lưu trữ tại công cụ Lakehouse của nền tảng Microsoft Fabric.
Bước 3: Tuỳ theo nhu cầu của dự án, người xây dựng sản phẩm số thực hiện tính toán nâng cao, phân tích chuyên sâu, học máy,… với Dataflow Gen 2, Notebook hoặc một số công cụ khác trong cấu phần Data Science của nền tảng Microsoft Fabric. 
Bước 4: Khi có nhu cầu lưu trữ dữ liệu và kết quả có được trong bước 3, người xây dựng sản phẩm số thực hiện lưu trữ trong Lakehouse. Nếu không có nhu cầu thực hiện tính toán, phân tích nâng cao, có thể bỏ qua bước 3 và bước 4.
Bước 5: Với những dữ liệu đã lưu trữ trong Lakehouse, người xây dựng sản phẩm số tạo lập báo cáo, biểu diễn dữ liệu với Power BI Visuals.
Bước 6: Để chia sẻ sản phẩm số với khách hàng, người xây dựng sản phẩm số tạo ứng dụng với công cụ Power BI App.
Bước 7: Khi có nhu cầu tạo giao diện nhập liệu để khách hàng có thể tương tác nhiều hơn, người xây dựng sản phẩm số có thể sử dụng công cụ Power Automate, Power Apps.

2. Nhân sự tham gia triển khai sản phẩm số
Quá trình triển khai sản phẩm số nêu trên sẽ yêu cầu sự cộng tác giữa nhân sự ở các bộ phận khác nhau. Một dự án triển khai thông thường sẽ cần sự tham gia của chủ nhiệm dự án, nhân sự bộ phận quản lý sản phẩm, các thành viên, kỹ sư dữ liệu và được tiến hành theo các bước sau.
Bước 1: PMO tạo các Collab workspace và Production workspace phục vụ cho dự án.
Bước 2: PMO thực hiện phân quyền cho PO, các thành viên cùng thực hiện dự án, DE (nếu cần) vào các workspace tương ứng như sau
- Collab workspace: PO, PMO, các thành viên, DE (nếu cần)
- Production workspace: PO, PMO
Bước 3: PO tạo Lakehouse trống trong Collab workspace để các thành viên đưa dữ liệu vào. Các thành viên tạo Lakehouse trong Domain workspace, đưa dữ liệu từ nguồn dữ liệu (Sharepoint, Dataverse for Teams,…) vào các công cụ Dataflơ Gen 2 hoặc Notebook và lưu trữ ở Lakehouse. Sau đó, các thành viên tạo ra bản sao là các bảng dữ liệu trong Lakehouse thuộc Collab workspace.
Bước 4: Các thành viên cộng tác và tạo ra sản phẩm trên Collab workspace. Ở bước này, nếu có nhu cầu thực hiện tính toán nâng cao, phân tích chuyên sâu, các thành viên có thể sử dụng Dataflow Gen 2, Notebook hoặc các công cụ khác của cấu phần Data Science thuộc Microsoft Fabric, sau đó lưu trữ dữ liệu và kết quả đã xử lý tại Lakehouse. Nếu không có nhu cầu, có thể bỏ qua việc tính toán, phân tích này. Với những dữ liệu đã lưu trữ trong Lakehouse, người xây dựng sản phẩm số tạo lập báo cáo, biểu diễn dữ liệu với Power BI Visuals. Khi có yêu cầu tạo giao diện nhập liệu để khách hàng có thể tương tác nhiều hơn, người xây dựng sản phẩm số có thể sử dụng công cụ Power Automate, Power Apps.
Bước 5: PMO tạo ứng dụng với Power BI App để kiểm tra trên Collab workspace.
Bước 6: PMO tạo ra bản sao của sản phẩm cuối trên Production workspace.
Bước 7: PMO phân quyền cho khách hàng tiếp cận sản phẩm.

3. Phân quyền sản phẩm
Để đảm bảo bảo mật cho dữ liệu và chỉ khách hàng có thể tiếp cận và sử dụng sản phẩm, khách hàng cần được phân quyền theo các bước như sau:
Bước 1: Tạo, phân quyền và chia sẻ Power BI App
- Trong Power BI Service, chọn Workspace cần tạo App và chọn “Create App”.
- Nhập các thông tin ban đầu: Tên App trong mục App Name; mô tả về App trong mục Description; cập nhật logo của App (nếu có).
- Tạo nội dung cho App: Chọn mục “App Content” và chọn một hoặc nhiều báo cáo đã tạo với công cụ Power BI Report. Danh sách báo cáo được chọn sẽ hiển thị trong Navigation Pane.
- Trong mục Audience, chọn “New Audience” để tạo nhóm người dùng mới và đặt tên nhóm.
- Thêm tài khoản người dùng cho nhóm người dùng vừa tạo vào mục “Specific users of groups”.
- Chọn “Publish app” để tạo App và gửi link App hiển thị trên màn hình cho người dùng (Người dùng cần có tài khoản Power BI Pro/Premium và được thêm vào nhóm người dùng mới có thể truy cập App).
Bước 2: Kiểm tra và hoàn thiện phân quyền.
- Trong Production workspace, vào báo cáo đã được sử dụng để tạo App, chọn “Manage permission”. Trong mục Direct Access, nếu trong danh sách chưa có tài khoản khách hàng, chọn “Add user”. Bỏ chọn các hộp lựa chọn và chọn “Grant access”.
- Trong Collab workspace, vào Lakehouse chứa dữ liệu tạo báo cáo và điều chỉnh phân quyền bằng cách chọn “Manage permission”. Chọn “Add user” và thêm tài khoản khách hàng. Chỉ lựa chọn hộp lựa chọn đầu tiên và “Grant acces”. 
- Trong Collab workspace, vào Dataset đã được sử dụng để tạo báo cáo, chọn “Manage permission”. Trong mục Direct Access, nếu trong danh sách chưa có tài khoản khách hàng, chọn “Add user”. Bỏ chọn các hộp lựa chọn và chọn “Grant access”.
- Sau khi hoàn thiện phân quyền có thể đăng nhập vào App bằng tài khoản của khách hàng để kiểm tra trước khi chuyển cho khách hàng.

III. Problem statement và Solution map
Xây dựng Problem statement và Solution map rất cần thiết trong quá trình triển khai sản phẩm số trên Microsoft Fabric.
Problem statement đảm bảo người xây dựng phải thấu hiểu vấn đề cần giải quyết, đối tượng sử dụng, yêu cầu của sản phẩm. 
Solution map đưa ra các bước thực hiện cụ thể từ lấy dữ liệu, xử lý dữ liệu cho tới xây dựng tính năng cho người dùng. Nhờ đó mà quá trình xây dựng sản phẩm được thực hiện một cách logic và nhất quán.
1. Problem statement
Để xây dựng Problem statement, chủ nhiệm dự án/nhóm thực hiện dự án cần cung cấp đầy đủ các thông tin sau:
• Người dùng sản phẩm.
• Yêu cầu cần đạt của sản phẩm
- Thực trạng: Người xây dựng sản phẩm số cần xác định những yếu tố sau: Vấn đề thực tế cần giải quyết và định lượng hoá vấn đề nếu có thể (Chi phí giải quyết vấn đề theo hướng truyền thống, thời gian yêu cầu để triển khai); Các sản phẩm tương tự có khả năng giải quyết vấn đề trên thị trường.
- Hình dung sản phẩm mong muốn: Các tính năng cần thiết của sản phẩm; Các tính năng vượt trội so với sản phẩm trên thị trường.
- Triển khai thực hiện
+ Phương pháp triển khai
Phương pháp truyền thống (Waterfall): Xác định các mốc tiến độ của dự án và thời gian thực hiện dự án.
Phương pháp linh hoạt (Agile): Dự kiến thời gian kéo dài của 1 Sprint; Xác định Sprint sẽ ra mắt Sản phẩm khả dụng tối thiểu (MVP).
+ Nhân sự triển khai: Cung cấp thông tin nhóm trực tiếp thực hiện dự án và nhóm hỗ trợ tiến hành.



Cách viết Problem statement hiệu quả:
- Đặt câu hỏi hiệu quả: có thể áp dụng quy tắc 5W1H để tìm hiểu về vấn đề đang gặp phải, cụ thể What? Why? When? Where? Who? How?
- Đặt giới hạn: thời gian thực hiện dự án, các chỉ tiêu cần đạt của sản phẩm.
- Ngắn gọn: cố gắng viết ngắn gọn, rõ ràng, cần chi tiết hơn có thể trao đổi trong các cuộc họp hoặc trong những tài liệu khác đi kèm.
- Không nên cố định Problem statement: Problem statement sẽ thay đổi và hoàn thiện dần theo yêu cầu của khách hàng và khả năng đáp ứng của nhóm phát triển sản phẩm.
- Không nên dùng nhiều ngôn ngữ chuyên môn/kỹ thuật: nên đảm bảo mọi nhân sự liên quan của dự án đều có thể hiểu được mà không nhất thiết phải có hiểu biết sâu về chuyên môn/kỹ thuật.

Cách viết hiệu quả theo SMART Problem statement:
- S – Specific: cụ thể vấn đề cần giải quyết một cách ngắn gọn, dễ hiểu.
- M – Measurable: định lượng và định tính đối với yêu cầu sản phẩm đầu ra.
- A – Action: những công việc cần làm để giải quyết vấn đề.
- R – Relevant: so sánh với các giải pháp đang có sẵn trên thị trường.
- T – Timebound: thời gian dự kiến giải quyết vấn đề.

2. Solution map
Solution map gồm 3 lớp: Lớp dữ liệu; Lớp phân tích; Lớp người sử dụng và được chia theo 5 dạng sản phẩm số như sau
2.1. Dữ liệu số: Các bước được thực hiện trong lớp dữ liệu
- Nguồn dữ liệu: Người xây dựng sản phẩm lấy dữ liệu từ các nguồn dữ liệu (Sharepoint Folder, Sharepoint List,…)
- Chuẩn hoá dữ liệu: Người xây dựng sản phẩm thực hiện chuẩn hoá dữ liệu bằng các công cụ Dataflow Gen 2 hoặc Notebook của Microsoft Fabric.
- Cơ sở dữ liệu: Người xây dựng sản phẩm lưu trữ dữ liệu đã chuẩn hoá trong Lakehouse.

2.2. Báo cáo số
Lớp dữ liệu: bao gồm các bước sau
- Nguồn dữ liệu: Người xây dựng sản phẩm lấy dữ liệu từ các nguồn dữ liệu (Sharepoint Folder, Sharepoint List,…)
- Chuẩn hoá dữ liệu: Người xây dựng sản phẩm thực hiện chuẩn hoá dữ liệu bằng các công cụ Dataflow Gen 2 hoặc Notebook của Microsoft Fabric.
- Cơ sở dữ liệu: Người xây dựng sản phẩm lưu trữ dữ liệu đã chuẩn hoá trong Lakehouse.
Lớp phân tích: Người xây dựng sản phẩm biến đổi, tính toán, phân tích theo nhu cầu với Dataflow Gen 2, Notebook hoặc các công cụ khác trong cấu phần Data Science của nền tảng Microsoft Fabric và lưu trữ dữ liệu, kết quả phân tích trong Lakehouse.
Lớp người sử dụng: Từ dữ liệu lưu trữ trong Lakehouse, người xây dựng sản phẩm tạo báo cáo, biểu diễn dữ liệu với Power BI.

2.3. Phân tích số
Lớp dữ liệu: bao gồm các bước sau
- Nguồn dữ liệu: Người xây dựng sản phẩm lấy dữ liệu từ các nguồn dữ liệu (Sharepoint Folder, Sharepoint List,…)
- Chuẩn hoá dữ liệu: Người xây dựng sản phẩm thực hiện chuẩn hoá dữ liệu bằng các công cụ Dataflow Gen 2 hoặc Notebook của Microsoft Fabric.
- Cơ sở dữ liệu: Người xây dựng sản phẩm lưu trữ dữ liệu đã chuẩn hoá trong Lakehouse.
Lớp phân tích: Người xây dựng sản phẩm biến đổi, tính toán, phân tích và ứng dụng ML/AI với Dataflow Gen 2, Notebook hoặc các công cụ khác trong cấu phần Data Science của nền tảng Microsoft Fabric và lưu trữ dữ liệu, kết quả phân tích trong Lakehouse.
Lớp người sử dụng: Từ dữ liệu lưu trữ trong Lakehouse, người xây dựng sản phẩm tạo báo cáo, biểu diễn dữ liệu với Power BI.

2.4. Mảnh ghép số: Gồm 3 dạng
• Mảnh ghép số - Biến đổi dữ liệu
Lớp dữ liệu: bao gồm các bước sau 
- Nguồn dữ liệu: Người xây dựng sản phẩm lấy dữ liệu từ các nguồn dữ liệu (Sharepoint Folder, Sharepoint List,…)
- Chuẩn hoá dữ liệu: Người xây dựng sản phẩm thực hiện chuẩn hoá dữ liệu bằng các công cụ Dataflow Gen 2 hoặc Notebook của Microsoft Fabric.
- Cơ sở dữ liệu: Người xây dựng sản phẩm lưu trữ dữ liệu đã chuẩn hoá trong Lakehouse.
Lớp phân tích: Người xây dựng sản phẩm sử dụng các thuật toán biến đổi mô hình/dữ liệu với Notebook hoặc một số công cụ khác trong cấu phần Data Science của nền tảng Microsoft Fabric và lưu trữ dữ liệu, kết quả phân tích trong Lakehouse. Đồng thời, Người xây dựng sản phẩm tiến hành đóng gói API thuật toán đã sử dụng.
Lớp người sử dụng: Người sử dụng làm việc với API End-point để biến đổi dữ liệu đầu vào, kết quả là dữ liệu đầu ra đã xử lý.
• Mảnh ghép số - Thuật toán
Lớp dữ liệu: bao gồm các bước sau
- Nguồn dữ liệu: Người xây dựng sản phẩm lấy dữ liệu từ các nguồn dữ liệu (Sharepoint Folder, Sharepoint List,…)
- Chuẩn hoá dữ liệu: Người xây dựng sản phẩm thực hiện chuẩn hoá dữ liệu bằng các công cụ Dataflow Gen 2 hoặc Notebook của Microsoft Fabric.
- Cơ sở dữ liệu: Người xây dựng sản phẩm lưu trữ dữ liệu đã chuẩn hoá trong Lakehouse.
Lớp phân tích: Người xây dựng sản phẩm sử dụng các thuật toán xây dựng mô hình với Notebook hoặc một số công cụ khác trong cấu phần Data Science của nền tảng Microsoft Fabric và lưu trữ dữ liệu, kết quả phân tích trong Lakehouse. Đồng thời, người xây dựng sản phẩm tiến hành đóng gói API thuật toán đã sử dụng.
Lớp người sử dụng: Người sử dụng làm việc với API End-point để biến đổi dữ liệu đầu vào, kết quả đầu ra là mô hình.

• Mảnh ghép số - Mô hình
Lớp dữ liệu: bao gồm các bước sau
- Nguồn dữ liệu: Người xây dựng sản phẩm lấy dữ liệu từ các nguồn dữ liệu (Sharepoint Folder, Sharepoint List,…)
- Chuẩn hoá dữ liệu: Người xây dựng sản phẩm thực hiện chuẩn hoá dữ liệu bằng các công cụ Dataflow Gen 2 hoặc Notebook của Microsoft Fabric.
- Cơ sở dữ liệu: Người xây dựng sản phẩm lưu trữ dữ liệu đã chuẩn hoá trong Lakehouse.
Lớp phân tích: Người xây dựng sản phẩm xây dựng mô hình huấn luyện trước với Notebook hoặc một số công cụ khác trong cấu phần Data Science của nền tảng Microsoft Fabric và lưu trữ dữ liệu, kết quả phân tích trong Lakehouse. Đồng thời, Người xây dựng sản phẩm tiến hành đóng gói API thuật toán đã sử dụng.
Lớp người sử dụng: Người sử dụng làm việc với API End-point để biến đổi dữ liệu đầu vào và đầu ra là kết quả dự báo.

2.5. Ứng dụng số: Gồm 2 dạng
• Ứng dụng số - Đơn giản
Lớp dữ liệu: bao gồm các bước sau
- Nguồn dữ liệu: Người xây dựng sản phẩm lấy dữ liệu từ các nguồn dữ liệu (Sharepoint Folder, Sharepoint List,…)
- Chuẩn hoá dữ liệu: Người xây dựng sản phẩm thực hiện chuẩn hoá dữ liệu bằng các công cụ Dataflow Gen 2 hoặc Notebook của Microsoft Fabric.
- Cơ sở dữ liệu: Người xây dựng sản phẩm lưu trữ dữ liệu đã chuẩn hoá trong Lakehouse.
Lớp phân tích: Người xây dựng sản phẩm biến đổi, tính toán, phân tích theo nhu cầu với Dataflow Gen 2, Notebook hoặc các công cụ khác trong cấu phần Data Science của nền tảng Microsoft Fabric và lưu trữ dữ liệu, kết quả phân tích trong Lakehouse.
Lớp người sử dụng: Từ dữ liệu lưu trữ trong Lakehouse, người xây dựng sản phẩm tạo báo cáo, biểu diễn dữ liệu với Power BI hay tạo giao diện nhập liệu với công cụ Power Apps hoặc Power Automate phục vụ mục đích người sử dụng.

• Ứng dụng số - Nâng cao
Lớp dữ liệu: bao gồm các bước sau
- Nguồn dữ liệu: Người xây dựng sản phẩm lấy dữ liệu từ các nguồn dữ liệu (Sharepoint Folder, Sharepoint List,…)
- Chuẩn hoá dữ liệu: Người xây dựng sản phẩm thực hiện chuẩn hoá dữ liệu bằng các công cụ Dataflow Gen 2 hoặc Notebook của Microsoft Fabric.
- Cơ sở dữ liệu: Người xây dựng sản phẩm lưu trữ dữ liệu đã chuẩn hoá trong Lakehouse.
Lớp phân tích: Người xây dựng sản phẩm biến đổi, tính toán, phân tích và ứng dụng ML/AI với Dataflow Gen 2, Notebook hoặc các công cụ khác trong cấu phần Data Science của nền tảng Microsoft Fabric và lưu trữ dữ liệu, kết quả phân tích trong Lakehouse.
Lớp người sử dụng: Từ dữ liệu lưu trữ trong Lakehouse, người xây dựng sản phẩm tạo báo cáo, biểu diễn dữ liệu với Power BI hay tạo giao diện nhập liệu với công cụ Power Apps hoặc Power Automate phục vụ mục đích người sử dụng.
[MP1]@Dao Huong Giang bổ sung giới thiệu về workflow nhé: workflow tên là gì, mục đích là gì, bổ sung list từ điển cho quy trình: bao gồm tiếng anh, tiếng việt, nghĩa trong bối cảnh doc vd: workspace: không gian làm việc chung, ở đây là Power BI workspace
