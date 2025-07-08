

---



# Proposal: Website Serverless Quản Lý Thông Tin Sinh Viên với AWS

## 1. 📄 Executive Summary (10%)

### Problem Statement
Hệ thống quản lý thông tin sinh viên hiện tại của các tổ chức giáo dục đang gặp phải nhiều khó khăn trong việc xử lý lượng dữ liệu lớn và ngày càng gia tăng, gây ảnh hưởng trực tiếp đến hiệu suất hoạt động và chi phí vận hành. Các hệ thống truyền thống yêu cầu cơ sở hạ tầng phần cứng phức tạp, chi phí bảo trì cao và thiếu khả năng tự động mở rộng, dẫn đến sự kém linh hoạt trong việc đáp ứng nhu cầu mở rộng và bảo mật. Điều này đặc biệt nghiêm trọng trong bối cảnh sự gia tăng nhanh chóng về số lượng sinh viên và khối lượng dữ liệu cần xử lý.

Ngoài ra, sự thiếu sót trong khả năng tự động hóa sao lưu, bảo mật và thông báo khiến cho việc duy trì hệ thống trở nên phức tạp và dễ dẫn đến các sai sót không đáng có. Các yêu cầu về bảo mật dữ liệu sinh viên cũng ngày càng nghiêm ngặt hơn, buộc các tổ chức phải tìm kiếm các giải pháp thay thế để giảm thiểu rủi ro bảo mật và tối ưu hóa chi phí.


### Solution Overview
Giải pháp đề xuất là xây dựng một **website serverless** sử dụng các dịch vụ của AWS, bao gồm **Lambda**, **API Gateway**, **DynamoDB**, **S3**, **SES**, và **CloudFront**, giúp quản lý thông tin sinh viên một cách hiệu quả, linh hoạt và an toàn. Ứng dụng này sẽ triển khai mô hình **serverless** – không cần phải quản lý hạ tầng máy chủ, giảm thiểu chi phí và nâng cao hiệu suất.

Hệ thống sẽ hỗ trợ các tính năng chính như:
- **Quản lý thông tin sinh viên (CRUD)**: Người dùng có thể thêm, sửa, xóa và xem thông tin sinh viên một cách dễ dàng thông qua giao diện web.
- **Lưu trữ tài liệu**: Các tài liệu liên quan đến sinh viên (hồ sơ, bài tập, chứng chỉ) sẽ được lưu trữ an toàn và tiết kiệm chi phí trên **Amazon S3**.
- **Dữ liệu sinh viên và điểm số**: Thông tin sinh viên sẽ được lưu trữ trong **Amazon DynamoDB**, một cơ sở dữ liệu NoSQL có khả năng mở rộng nhanh chóng và linh hoạt.
- **Bảo mật**: Hệ thống sẽ sử dụng **API Gateway** để bảo mật và kiểm tra các yêu cầu API thông qua **API Key**.
- **Sao lưu tự động**: Tự động sao lưu dữ liệu từ DynamoDB vào **S3** thông qua **EventBridge**.
- **Email xác nhận và thông báo**: Các email xác nhận hoặc thông báo sẽ được gửi qua **Amazon SES**.
- **Mở rộng và tối ưu hóa toàn cầu**: Sử dụng **CloudFront** để phân phối nội dung với độ trễ thấp và tối ưu hóa hiệu suất toàn cầu.


### Business Benefits & ROI Summary
Giải pháp **serverless** mang lại nhiều lợi ích cho tổ chức trong việc tiết kiệm chi phí, tăng cường bảo mật và nâng cao hiệu suất hệ thống:

- **Tiết kiệm chi phí**: Không cần phải duy trì hạ tầng máy chủ vật lý hoặc máy chủ ảo, giúp giảm chi phí đầu tư ban đầu và chi phí duy trì hàng tháng.
- **Khả năng mở rộng linh hoạt**: Hệ thống có thể tự động mở rộng để đáp ứng nhu cầu ngày càng tăng mà không cần sự can thiệp của người dùng.
- **Tăng cường bảo mật**: AWS cung cấp các công cụ bảo mật mạnh mẽ như **IAM**, **KMS** và **VPC**, giúp bảo vệ thông tin sinh viên khỏi các mối đe dọa tiềm ẩn.
- **Dễ dàng quản lý và duy trì**: Việc quản lý hệ thống trở nên đơn giản hơn, nhờ vào khả năng tự động sao lưu và bảo mật của AWS, giảm thiểu rủi ro và chi phí bảo trì.
- **Tiết kiệm thời gian**: Hệ thống được triển khai nhanh chóng và có thể mở rộng dễ dàng khi nhu cầu thay đổi, giảm thiểu thời gian phát triển và triển khai so với hệ thống truyền thống.

**ROI**: 
- Dự kiến sẽ tiết kiệm được 30% chi phí vận hành so với hệ thống truyền thống trong năm đầu tiên.
- Việc tự động hóa các tác vụ quản lý và bảo mật sẽ giảm thiểu chi phí nhân sự, giúp giảm tổng chi phí vận hành.


### Investment Required & Timeline
**Investment**: Dự án yêu cầu đầu tư vào việc thiết kế hệ thống, triển khai dịch vụ AWS, phát triển backend và frontend. Tổng chi phí dự tính sẽ rơi vào khoảng **$50,000** cho giai đoạn triển khai ban đầu.

**Timeline**:
- **Tháng 1**: Thiết kế kiến trúc hệ thống, cấu hình API Gateway, Lambda, và DynamoDB.
- **Tháng 2**: Tích hợp với S3, SES, và cấu hình bảo mật IAM.
- **Tháng 3**: Kiểm thử, triển khai và tối ưu hóa hệ thống.

### Success Metrics & Expected Outcomes
**Success Metrics**:
- **API Response Time**: Thời gian phản hồi của API sẽ dưới **200ms** cho mỗi yêu cầu.
- **Scalability**: Hệ thống có thể xử lý được **1000 yêu cầu/giây** mà không gặp phải vấn đề hiệu suất.
- **Cost Reduction**: Dự kiến giảm được **30% chi phí vận hành** so với mô hình truyền thống.
- **User Experience**: Trải nghiệm người dùng mượt mà, giao diện thân thiện và dễ sử dụng.
  
---

**Expected Outcomes**:
- **Hiệu suất cao và linh hoạt**: Hệ thống sẽ đáp ứng nhanh chóng với số lượng sinh viên và dữ liệu ngày càng tăng.
- **Tiết kiệm chi phí**: Chi phí vận hành hệ thống sẽ được giảm bớt nhờ vào mô hình **serverless**, giúp giảm thiểu chi phí duy trì hạ tầng.
- **Bảo mật tối ưu**: Tăng cường bảo mật cho dữ liệu sinh viên và tài liệu qua các dịch vụ bảo mật của AWS.
- **Dễ dàng mở rộng**: Hệ thống sẽ có khả năng mở rộng mà không cần thay đổi cấu trúc phần cứng.

---

## 2. 🎯 Problem Statement (15%)

### Current Situation Analysis
Hệ thống quản lý sinh viên hiện tại sử dụng máy chủ vật lý và cơ sở dữ liệu truyền thống. Việc mở rộng hệ thống trong trường hợp có sự gia tăng lớn về số lượng sinh viên sẽ gặp khó khăn về phần cứng và chi phí duy trì. Hệ thống cũ cũng thiếu khả năng tự động hóa các tác vụ như sao lưu dữ liệu và thông báo qua email.

### Pain Points Identification with Quantified Impact
1. **Chi phí vận hành cao**:
   - Việc duy trì các máy chủ vật lý và phần mềm quản lý hệ thống gây ra chi phí hàng tháng lớn. Các tổ chức phải chi trả cho các dịch vụ lưu trữ, bảo trì phần cứng, và nhân sự kỹ thuật.
   - **Tác động**: Các chi phí bảo trì máy chủ vật lý có thể chiếm tới 40% ngân sách công nghệ thông tin hàng năm của tổ chức.

2. **Khó khăn trong việc mở rộng**:
   - Khi số lượng sinh viên và tài liệu tăng lên, việc mở rộng hệ thống đòi hỏi nâng cấp phần cứng và phần mềm, điều này không linh hoạt và tốn kém.
   - **Tác động**: Việc mở rộng có thể mất đến vài tháng, dẫn đến gián đoạn trong công việc và giảm hiệu suất hoạt động.

3. **Bảo mật thông tin kém**:
   - Dữ liệu sinh viên không được bảo mật tối ưu, dễ bị truy cập trái phép nếu không có các cơ chế bảo vệ phù hợp.
   - **Tác động**: Việc bảo mật kém có thể dẫn đến vi phạm dữ liệu và ảnh hưởng đến danh tiếng của tổ chức.


### Stakeholders Affected & Their Concerns
- **Quản lý hệ thống**: Lo ngại về chi phí bảo trì và khả năng mở rộng.
- **Giảng viên**: Quan tâm đến độ chính xác và bảo mật của thông tin sinh viên.
- **Sinh viên**: Lo ngại về việc bảo mật và an toàn thông tin cá nhân.

### Business Consequences of Inaction
Nếu không thay đổi hệ thống, tổ chức sẽ phải tiếp tục chi trả cho chi phí duy trì phần cứng và phần mềm, đồng thời gặp phải khó khăn khi mở rộng quy mô. Hệ thống sẽ gặp nhiều vấn đề về hiệu suất, bảo mật và khả năng đáp ứng các yêu cầu mới, dẫn đến giảm hiệu quả công việc và uy tín của tổ chức.


### Market Opportunity
Với sự phát triển mạnh mẽ của các dịch vụ điện toán đám mây, chuyển sang mô hình **serverless** sẽ giúp tổ chức tiết kiệm chi phí vận hành, giảm độ phức tạp trong việc quản lý hệ thống, và cung cấp khả năng mở rộng linh hoạt. Đây là cơ hội để tối ưu hóa hiệu quả công việc và đáp ứng nhu cầu của một hệ thống quản lý sinh viên hiện đại.

---

## 3. 🏗️ Solution Architecture (25%)

### High-Level Architecture Diagram

![High-Level Architecture Diagram](images/high-level-architecture-diagram.jpg)
*Hình 1: Sơ đồ tổng quan kiến trúc hệ thống serverless với các dịch vụ AWS.*

### AWS Services Selection with Justification

Để xây dựng ứng dụng **Website Serverless Quản Lý Thông Tin Sinh Viên**, chúng tôi chọn các dịch vụ AWS sau để đảm bảo hiệu suất, bảo mật và khả năng mở rộng của hệ thống:

1. **AWS Lambda**:
   - **Lý do chọn**: Lambda cho phép thực thi mã mà không cần quản lý máy chủ, giúp tiết kiệm chi phí và dễ dàng mở rộng khi có lưu lượng cao. Các hàm Lambda sẽ xử lý logic backend, bao gồm các thao tác CRUD trên dữ liệu sinh viên.
   - **Lợi ích**: Tính linh hoạt cao, dễ dàng tích hợp với các dịch vụ khác của AWS và tự động mở rộng khi có yêu cầu.

2. **API Gateway**:
   - **Lý do chọn**: API Gateway giúp xây dựng và quản lý các API RESTful, cung cấp một giao diện duy nhất để giao tiếp với ứng dụng. Nó cũng hỗ trợ bảo mật qua API Key và rate limiting.
   - **Lợi ích**: Đảm bảo tính bảo mật và dễ dàng quản lý các API.

3. **Amazon DynamoDB**:
   - **Lý do chọn**: DynamoDB là cơ sở dữ liệu NoSQL của AWS, hỗ trợ khả năng mở rộng tự động và hiệu suất cao trong việc lưu trữ và truy xuất dữ liệu sinh viên.
   - **Lợi ích**: Được tối ưu hóa cho các ứng dụng có lượng truy vấn lớn và thay đổi dữ liệu nhanh chóng.

4. **Amazon S3**:
   - **Lý do chọn**: S3 sẽ được sử dụng để lưu trữ các tài liệu học tập của sinh viên (chẳng hạn như bài thi, tài liệu học tập) và sao lưu dữ liệu sinh viên từ DynamoDB.
   - **Lợi ích**: Lưu trữ chi phí thấp, bền vững và dễ dàng tích hợp với các dịch vụ AWS khác.

5. **Amazon SES**:
   - **Lý do chọn**: SES (Simple Email Service) sẽ được sử dụng để gửi email xác nhận cho sinh viên và thông báo hệ thống.
   - **Lợi ích**: Dịch vụ email dễ sử dụng, chi phí thấp và khả năng tích hợp cao với các dịch vụ khác của AWS.

6. **Amazon CloudFront**:
   - **Lý do chọn**: CloudFront sẽ giúp phân phối nội dung tĩnh (như hình ảnh, CSS, JS) toàn cầu với độ trễ thấp.
   - **Lợi ích**: Tăng tốc độ tải trang và giảm độ trễ cho người dùng ở bất kỳ đâu trên thế giới.

7. **AWS IAM (Identity and Access Management)**:
   - **Lý do chọn**: IAM được sử dụng để quản lý quyền truy cập và bảo mật cho các dịch vụ AWS, đảm bảo rằng chỉ những người dùng hoặc dịch vụ có quyền mới có thể truy cập vào các tài nguyên.
   - **Lợi ích**: Đảm bảo tính bảo mật và tuân thủ các yêu cầu bảo mật của tổ chức.

### Component Interactions và Data Flow

1. **API Gateway** nhận các yêu cầu HTTP từ người dùng và chuyển tiếp các yêu cầu đến **AWS Lambda**. Các yêu cầu này bao gồm các thao tác CRUD (Create, Read, Update, Delete) đối với thông tin sinh viên.
2. **Lambda** thực hiện các thao tác CRUD với **DynamoDB**, nơi chứa dữ liệu sinh viên như mã sinh viên, họ tên, lớp học, ngày sinh, và email.
3. Khi sinh viên tải lên tài liệu (chẳng hạn như bài thi hoặc bài tập), **Lambda** sẽ lưu trữ tài liệu đó vào **S3**.
4. **SES** sẽ gửi email xác nhận cho sinh viên sau khi một thao tác CRUD được thực hiện thành công (ví dụ, xác nhận việc thêm mới sinh viên).
5. **CloudFront** sẽ phân phối các tài liệu và nội dung tĩnh từ **S3** đến người dùng với độ trễ thấp.

### Security Architecture và Compliance

1. **IAM Roles**:
   - Sử dụng **IAM roles** để cấp quyền truy cập cho các dịch vụ AWS. Ví dụ, **Lambda** cần quyền truy cập vào **DynamoDB** để đọc và ghi dữ liệu, cũng như quyền truy cập vào **S3** để lưu trữ tài liệu.
   - **IAM Policies** sẽ được áp dụng để đảm bảo mỗi dịch vụ chỉ có quyền truy cập cần thiết, giảm thiểu rủi ro bảo mật.

2. **Data Encryption**:
   - **DynamoDB** và **S3** sẽ sử dụng mã hóa tại **REST** và **in-transit** để đảm bảo rằng dữ liệu luôn được bảo vệ.
   - **KMS (Key Management Service)** sẽ được sử dụng để tạo và quản lý các khóa mã hóa.

3. **Authentication and Authorization**:
   - Bảo mật API được thực hiện qua **API Gateway** với việc sử dụng **API Keys** và **IAM roles** để kiểm soát quyền truy cập vào các dịch vụ.

4. **Compliance**:
   - Hệ thống sẽ tuân thủ các tiêu chuẩn bảo mật và quy định của AWS về bảo mật dữ liệu và quyền riêng tư, đặc biệt là các quy định liên quan đến việc xử lý dữ liệu của sinh viên.

### Scalability và Performance Considerations

1. **Auto-scaling**:
   - **AWS Lambda** tự động mở rộng để đáp ứng yêu cầu về xử lý mà không cần phải điều chỉnh hạ tầng thủ công. Số lượng yêu cầu được xử lý đồng thời sẽ được điều chỉnh tự động.
   - **DynamoDB** hỗ trợ khả năng mở rộng tự động để đáp ứng với lưu lượng truy vấn và ghi lớn.

2. **CloudFront** giúp phân phối nội dung với độ trễ thấp ở các khu vực toàn cầu, tối ưu hóa tốc độ tải trang và giảm độ trễ cho người dùng.

3. **Caching**:
   - **API Gateway** có thể sử dụng **caching** để giảm tải cho backend và cải thiện hiệu suất cho các yêu cầu đọc dữ liệu lặp đi lặp lại.

### Integration Points với Existing Systems

- **Hệ thống quản lý sinh viên hiện tại** có thể được tích hợp với hệ thống serverless thông qua các API được cung cấp bởi **API Gateway**. Điều này sẽ cho phép đồng bộ hóa thông tin giữa hệ thống mới và hệ thống cũ mà không gặp phải sự gián đoạn lớn.
- Việc sử dụng **Lambda** và **API Gateway** làm cầu nối giữa các dịch vụ backend giúp dễ dàng tích hợp và mở rộng mà không làm thay đổi quá nhiều hệ thống hiện tại.

---

## 4. 🔧 Technical Implementation (20%)

### Implementation Phases với Deliverables

Dự án sẽ được triển khai qua ba giai đoạn chính, mỗi giai đoạn có các deliverables cụ thể và mục tiêu rõ ràng.

1. **Phase 1: Thiết kế và Cấu hình Hệ thống (Tháng 1)**:
   - **Mục tiêu**: Thiết lập kiến trúc hệ thống và cấu hình các dịch vụ AWS cơ bản.
   - **Deliverables**:
     - Thiết kế chi tiết kiến trúc hệ thống.
     - Cấu hình **API Gateway**, **Lambda Functions**, và **DynamoDB**.
     - Tạo và cấu hình các **IAM roles** và quyền truy cập.
   
2. **Phase 2: Tích hợp với S3, SES, và IAM (Tháng 2)**:
   - **Mục tiêu**: Tích hợp hệ thống với các dịch vụ lưu trữ và bảo mật AWS.
   - **Deliverables**:
     - Tích hợp **Amazon S3** để lưu trữ tài liệu và dữ liệu sao lưu.
     - Cấu hình **SES** để gửi email xác nhận và thông báo.
     - Cấu hình **IAM** cho việc quản lý bảo mật và phân quyền truy cập.
   
3. **Phase 3: Kiểm thử, Triển khai và Tối ưu hóa (Tháng 3)**:
   - **Mục tiêu**: Kiểm thử hệ thống, triển khai lên môi trường sản xuất và tối ưu hóa hiệu suất.
   - **Deliverables**:
     - Kiểm thử toàn bộ hệ thống: unit tests, integration tests và performance tests.
     - Triển khai ứng dụng lên môi trường AWS sản xuất.
     - Tối ưu hóa các dịch vụ và xử lý sự cố nếu có.

### Technical Requirements

1. **Compute**:
   - **AWS Lambda**: Chạy mã backend mà không cần quản lý máy chủ. Mỗi hàm Lambda sẽ xử lý các yêu cầu từ **API Gateway** và thực hiện các thao tác CRUD trên **DynamoDB**.
   - **API Gateway**: Quản lý các yêu cầu HTTP từ người dùng và chuyển tiếp các yêu cầu đến Lambda, cung cấp các tính năng bảo mật và kiểm tra lưu lượng truy cập.

2. **Storage**:
   - **Amazon DynamoDB**: Cơ sở dữ liệu NoSQL sẽ lưu trữ các thông tin về sinh viên, bao gồm mã sinh viên, họ tên, lớp, ngày sinh, và email.
   - **Amazon S3**: Lưu trữ các tài liệu học tập của sinh viên, bao gồm bài thi, tài liệu học tập, chứng chỉ, v.v. S3 cũng sẽ được sử dụng để sao lưu dữ liệu từ DynamoDB.

3. **Network**:
   - **Amazon CloudFront**: Phân phối nội dung tĩnh và giảm độ trễ cho người dùng trên toàn cầu.
   - **Amazon VPC (Virtual Private Cloud)**: Cấu hình mạng riêng cho các dịch vụ AWS để đảm bảo an toàn và bảo mật cho dữ liệu truyền tải giữa các dịch vụ.

### Development Approach và Methodologies

- **Agile Development**: Dự án sẽ được triển khai theo phương pháp Agile, với các sprint ngắn (2 tuần) và kiểm tra liên tục để đảm bảo chất lượng. Sau mỗi sprint, các phần tính năng của hệ thống sẽ được hoàn thiện và kiểm thử.
  
- **CI/CD (Continuous Integration and Continuous Deployment)**:
  - Sử dụng **AWS CodePipeline** để tự động hóa quy trình kiểm thử và triển khai.
  - **AWS CodeBuild** để biên dịch và kiểm tra mã nguồn mỗi khi có thay đổi.
  - **AWS CodeDeploy** sẽ được sử dụng để triển khai ứng dụng lên môi trường sản xuất.

- **Infrastructure as Code (IaC)**: Toàn bộ hạ tầng sẽ được mô tả dưới dạng mã thông qua **AWS CloudFormation**. Điều này giúp tự động hóa việc triển khai, cập nhật và quản lý cấu trúc hạ tầng AWS.

### Testing Strategy (Unit, Integration, Performance)

1. **Unit Testing**:
   - **AWS Lambda** sẽ được kiểm tra từng chức năng nhỏ, đảm bảo mã nguồn hoạt động đúng như mong đợi.
   - Sử dụng **Jest** cho việc kiểm tra mã JavaScript trong Lambda Functions.

2. **Integration Testing**:
   - Kiểm tra toàn bộ hệ thống, bao gồm việc tích hợp giữa **API Gateway**, **Lambda**, **DynamoDB**, **S3**, và **SES**.
   - Đảm bảo các yêu cầu API được xử lý đúng đắn và các dịch vụ AWS tương tác với nhau một cách chính xác.

3. **Performance Testing**:
   - Kiểm tra khả năng chịu tải của hệ thống, đảm bảo hệ thống có thể xử lý được số lượng lớn yêu cầu (tối thiểu 1000 yêu cầu mỗi giây).
   - Sử dụng **AWS CloudWatch** để giám sát hiệu suất và tài nguyên của Lambda, API Gateway và DynamoDB.

### Deployment Plan và Rollback Procedures

1. **Deployment Plan**:
   - **Bước 1**: Triển khai mã nguồn và cấu hình hệ thống lên môi trường AWS sản xuất.
   - **Bước 2**: Kiểm thử toàn bộ hệ thống sau khi triển khai, đảm bảo các dịch vụ AWS được kết nối và hoạt động chính xác.
   - **Bước 3**: Theo dõi hệ thống qua **AWS CloudWatch** để đảm bảo không có lỗi xảy ra.

2. **Rollback Procedures**:
   - **Bước 1**: Nếu có sự cố xảy ra sau khi triển khai, sử dụng **AWS CloudFormation** để khôi phục lại cấu trúc hạ tầng của hệ thống về trạng thái trước khi triển khai.
   - **Bước 2**: Nếu có lỗi trong mã nguồn, quay lại phiên bản trước đó của Lambda function và triển khai lại thông qua **AWS CodeDeploy**.

### Configuration Management

- **AWS CloudFormation** sẽ được sử dụng để quản lý cấu hình và triển khai tự động. Các file **CloudFormation templates** sẽ mô tả tất cả các dịch vụ AWS (Lambda, DynamoDB, API Gateway, S3, SES, VPC), giúp dễ dàng quản lý và tái triển khai toàn bộ hệ thống.
  
- **Parameter Store** của **AWS Systems Manager** sẽ được sử dụng để lưu trữ các biến môi trường và thông tin cấu hình cần thiết cho hệ thống.

---

## 5. 📅 Timeline & Milestones (10%)

### Project Phases Breakdown

Dự án được chia thành ba giai đoạn chính, mỗi giai đoạn sẽ kéo dài một tháng và bao gồm các công việc cụ thể. Các giai đoạn này được xác định dựa trên mức độ phức tạp và các mục tiêu quan trọng của dự án.

1. **Phase 1: Thiết kế và Cấu hình Hệ thống (Tháng 1)**:
   - **Mục tiêu**: Thiết lập kiến trúc hệ thống và cấu hình các dịch vụ AWS cơ bản.
   - **Công việc chính**:
     - Thiết kế kiến trúc tổng thể.
     - Cấu hình **API Gateway**, **Lambda Functions**, và **DynamoDB**.
     - Xác định **IAM Roles** và cấu hình các quyền truy cập.

2. **Phase 2: Tích hợp với S3, SES, và IAM (Tháng 2)**:
   - **Mục tiêu**: Tích hợp các dịch vụ lưu trữ và bảo mật AWS.
   - **Công việc chính**:
     - Tích hợp **Amazon S3** để lưu trữ tài liệu và sao lưu dữ liệu.
     - Cấu hình **SES** để gửi email xác nhận và thông báo.
     - Cấu hình **IAM** để quản lý quyền truy cập bảo mật cho các dịch vụ AWS.

3. **Phase 3: Kiểm thử, Triển khai và Tối ưu hóa (Tháng 3)**:
   - **Mục tiêu**: Kiểm thử toàn bộ hệ thống, triển khai và tối ưu hóa hiệu suất.
   - **Công việc chính**:
     - Kiểm thử **Unit Testing**, **Integration Testing** và **Performance Testing**.
     - Triển khai hệ thống lên môi trường AWS sản xuất.
     - Tối ưu hóa hiệu suất hệ thống và giám sát qua **AWS CloudWatch**.

---

### Key Milestones với Success Criteria

1. **Milestone 1: Thiết kế và Cấu hình Hệ thống** (Cuối Tháng 1)
   - **Success Criteria**: Hoàn thành cấu hình các dịch vụ **API Gateway**, **Lambda**, **DynamoDB** và thiết lập các **IAM roles**.
   - **Deliverables**: Kiến trúc hệ thống, cấu hình cơ bản của các dịch vụ AWS.

2. **Milestone 2: Tích hợp với S3 và SES** (Cuối Tháng 2)
   - **Success Criteria**: Hoàn thành việc tích hợp **Amazon S3** và **SES**, đảm bảo rằng tài liệu được lưu trữ thành công trên S3 và email được gửi từ SES.
   - **Deliverables**: Hệ thống có khả năng lưu trữ tài liệu và gửi email thông báo cho người dùng.

3. **Milestone 3: Kiểm thử và Triển khai Hệ thống** (Cuối Tháng 3)
   - **Success Criteria**: Hệ thống đã được kiểm thử đầy đủ và triển khai thành công lên môi trường sản xuất, hệ thống hoạt động ổn định dưới tải.
   - **Deliverables**: Hệ thống đã được kiểm thử và triển khai trên AWS, các lỗi được khắc phục, tối ưu hóa hiệu suất.

---

### Dependencies Identification

- **API Gateway** phụ thuộc vào việc cấu hình **Lambda Functions** để xử lý các yêu cầu API.
- **DynamoDB** cần phải được cấu hình trước khi tích hợp với các hàm **Lambda** để lưu trữ dữ liệu.
- **SES** phụ thuộc vào việc cấu hình **IAM Roles** để đảm bảo gửi email đúng cách từ **Lambda**.
- **S3** cần được cấu hình trước khi tài liệu sinh viên có thể được lưu trữ.

---

### Critical Path Analysis

- **Critical Path**: 
  - Giai đoạn **Phase 1** (Thiết kế và Cấu hình Hệ thống) là giai đoạn quan trọng nhất vì nó bao gồm việc cấu hình **API Gateway**, **Lambda**, và **DynamoDB**, tất cả các dịch vụ này phải được thiết lập đúng cách để hệ thống hoạt động ổn định. 
  - Việc **IAM roles** được cấu hình chính xác cũng là yếu tố quyết định việc triển khai thành công ở các giai đoạn sau.

- **Risk**: Nếu có sự chậm trễ trong việc thiết lập **API Gateway** hoặc **Lambda Functions**, sẽ kéo dài toàn bộ tiến độ dự án, ảnh hưởng đến các giai đoạn tiếp theo.

---

### Resource Allocation Plan

1. **Nhân sự cần thiết**:
   - **Developer** (2 người): Chịu trách nhiệm phát triển các hàm **Lambda**, cấu hình **API Gateway** và tích hợp các dịch vụ.
   - **DevOps** (1 người): Chịu trách nhiệm thiết lập và duy trì môi trường AWS, bao gồm việc cấu hình **IAM**, **S3**, **SES**, và **CloudWatch**.
   - **Tester** (1 người): Chịu trách nhiệm kiểm thử hệ thống, bao gồm **Unit Testing**, **Integration Testing**, và **Performance Testing**.
   - **Project Manager** (1 người): Quản lý tiến độ và giám sát toàn bộ quá trình triển khai.

2. **Tài nguyên AWS**:
   - **AWS Lambda**: Tính toán chi phí theo số lượng yêu cầu và thời gian thực thi.
   - **DynamoDB**: Chi phí sẽ tăng theo lượng dữ liệu và số lượng truy vấn.
   - **S3 và SES**: Tính phí lưu trữ và gửi email.

---

### Buffer Time cho Risks

Để đối phó với các vấn đề phát sinh, chúng tôi sẽ dự trữ **1 tuần buffer time** vào cuối mỗi phase, giúp xử lý các rủi ro như:
- **Delay trong việc cấu hình dịch vụ**: Nếu gặp sự cố khi thiết lập **IAM Roles** hoặc các dịch vụ AWS khác, thời gian buffer này sẽ giúp khắc phục vấn đề.
- **Vấn đề trong quá trình kiểm thử**: Nếu hệ thống không đáp ứng được các yêu cầu kiểm thử, thời gian buffer sẽ cho phép nhóm kỹ thuật khắc phục sự cố và đảm bảo chất lượng hệ thống.

---

## 6. 💰 Budget Estimation (10%)

### AWS Infrastructure Costs
- **Lambda**: Tính phí theo số lần gọi và thời gian chạy.
- **API Gateway**: Tính phí theo số lượng API requests.
- **DynamoDB**: Phí lưu trữ và số lượng truy vấn.
- **S3**: Phí lưu trữ và truyền tải dữ liệu.

### Development Costs
- Phát triển backend, frontend và triển khai hạ tầng AWS: **30,000 USD**.

### Operational Costs
- Chi phí duy trì hằng năm cho AWS dịch vụ và nhân lực.

### ROI Calculation & Break-even Analysis
- **ROI**: Dự đoán đạt 40% trong vòng 18 tháng.

### Cost Optimization Strategies
- Sử dụng các gói giá AWS tiết kiệm và tối ưu hóa quy mô dịch vụ.

---

## 7. ⚠️ Risk Assessment (5%)

### Risk Identification
- **Technical Risk**: Các vấn đề về tích hợp AWS và bảo mật.
- **Business Risk**: Hệ thống không hoàn toàn tương thích với các hệ thống quản lý sinh viên hiện tại.
- **Operational Risk**: Thiếu nhân lực có kỹ năng để duy trì hệ thống.

### Impact Assessment & Probability Analysis
- **Technical Risk**: Có khả năng xảy ra nhưng có thể giải quyết qua kiểm thử kỹ lưỡng.
- **Business Risk**: Khả năng thấp nhưng cần chuẩn bị kế hoạch thay thế.

### Risk Matrix with Prioritization
- Ưu tiên các rủi ro kỹ thuật và bảo mật.

### Mitigation Strategies
- **Testing**: Đảm bảo tích hợp đúng qua nhiều giai đoạn kiểm thử.
- **Training**: Đảm bảo nhân lực được đào tạo đầy đủ.

---

## 8. 🎯 Expected Outcomes (5%)

### Success Metrics
- **Technical**: API đáp ứng dưới 200ms.
- **Business**: Giảm 30% chi phí vận hành.

### Short-term Benefits (0-6 months)
- Cải thiện hiệu suất và bảo mật.

### Medium-term Benefits (6-18 months)
- Hệ thống ổn định và có thể mở rộng.

### Long-term Value (18+ months)
- Tăng hiệu quả quản lý thông tin sinh viên và giảm chi phí.

### User Experience Improvements
- Giao diện thân thiện và dễ sử dụng, giúp sinh viên và giảng viên tiết kiệm thời gian.

---

Đây là bản proposal chi tiết cho dự án "Website Serverless Quản Lý Thông Tin Sinh Viên với AWS". Chúc bạn triển khai thành công dự án!
