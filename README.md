# Project Overview

## Executive Summary (10%)
- Tóm tắt mục tiêu dự án

---

## Cấu Trúc Dự Án

Để biết thêm chi tiết về đề xuất dự án, vui lòng tham khảo [Proposal: Website Serverless Quản Lý Thông Tin Sinh Viên với AWS](./proposal.md).


# Proposal: Website Serverless Quản Lý Thông Tin Sinh Viên với AWS

## 1. 📄 Executive Summary (10%)

### Problem Statement
Hệ thống quản lý thông tin sinh viên hiện tại đang sử dụng cơ sở dữ liệu truyền thống và các máy chủ vật lý, gây khó khăn trong việc mở rộng, bảo mật và chi phí duy trì cao. Việc quản lý thông tin như mã sinh viên, tên, lớp học, điểm số và tài liệu học tập đang gặp phải các vấn đề như hiệu suất kém và khó khăn trong việc mở rộng khi số lượng sinh viên gia tăng.

### Solution Overview
Giải pháp đề xuất là xây dựng một **website serverless** sử dụng các dịch vụ AWS như **Lambda**, **API Gateway**, **DynamoDB**, **S3**, **SES** để quản lý thông tin sinh viên một cách **hiệu quả**, **tiết kiệm chi phí**, và **tự động mở rộng**. Hệ thống sẽ hỗ trợ các tính năng chính như:
- Quản lý thông tin sinh viên (CRUD).
- Lưu trữ tài liệu học tập với Amazon S3.
- Lưu trữ và truy vấn dữ liệu sinh viên qua DynamoDB.
- API RESTful cho các thao tác CRUD.
- Bảo mật qua API Key với API Gateway.
- Gửi email xác nhận qua AWS SES và sao lưu tự động.

### Business Benefits & ROI Summary
Giải pháp này sẽ giúp:
- Tiết kiệm chi phí vận hành nhờ vào mô hình serverless.
- Dễ dàng mở rộng và bảo mật cao.
- Tăng hiệu suất hệ thống và khả năng chịu tải lớn.
- Tối ưu hóa trải nghiệm người dùng và giảm chi phí bảo trì.

**ROI**: 
- Dự kiến giảm 30% chi phí vận hành so với hệ thống truyền thống.
- Tăng tốc độ triển khai và mở rộng hệ thống với chi phí đầu tư ban đầu thấp.

### Investment Required & Timeline
**Investment**: Chi phí đầu tư ban đầu sẽ bao gồm thiết kế hệ thống, triển khai các dịch vụ AWS, và chi phí phát triển.
**Timeline**: Dự án sẽ hoàn thành trong vòng 3 tháng:
1. **Tháng 1**: Thiết kế hệ thống và cấu hình API Gateway, Lambda, DynamoDB.
2. **Tháng 2**: Tích hợp với Amazon S3 và SES, bảo mật IAM.
3. **Tháng 3**: Kiểm thử, triển khai và tối ưu hóa hệ thống.

### Success Metrics & Expected Outcomes
- **Success Metrics**: API có thể xử lý 1000 yêu cầu mỗi giây với thời gian phản hồi dưới 200ms.
- **Expected Outcomes**: Hệ thống hoạt động ổn định, có thể mở rộng linh hoạt và giảm chi phí vận hành hàng tháng.

---

## 2. 🎯 Problem Statement (15%)

### Current Situation Analysis
Hệ thống quản lý sinh viên hiện tại sử dụng máy chủ vật lý và cơ sở dữ liệu truyền thống. Việc mở rộng hệ thống trong trường hợp có sự gia tăng lớn về số lượng sinh viên sẽ gặp khó khăn về phần cứng và chi phí duy trì. Hệ thống cũ cũng thiếu khả năng tự động hóa các tác vụ như sao lưu dữ liệu và thông báo qua email.

### Pain Points Identification with Quantified Impact
- **Chi phí cao**: Hệ thống yêu cầu duy trì các máy chủ vật lý với chi phí bảo trì lên đến 50% tổng chi phí vận hành.
- **Khả năng mở rộng kém**: Hệ thống không thể dễ dàng mở rộng khi số lượng sinh viên gia tăng đột ngột.
- **Bảo mật kém**: Các tài liệu và thông tin sinh viên không được bảo mật chặt chẽ, dễ bị xâm phạm.

### Stakeholders Affected & Their Concerns
- **Quản lý hệ thống**: Lo ngại về chi phí bảo trì và khả năng mở rộng.
- **Giảng viên**: Quan tâm đến độ chính xác và bảo mật của thông tin sinh viên.
- **Sinh viên**: Lo ngại về việc bảo mật và an toàn thông tin cá nhân.

### Business Consequences of Inaction
Không thay đổi sẽ dẫn đến chi phí vận hành tăng cao, khó khăn trong việc quản lý và bảo mật dữ liệu, đồng thời gây ảnh hưởng xấu đến hiệu suất và khả năng mở rộng của hệ thống.

### Market Opportunity
Với sự phát triển của công nghệ điện toán đám mây, việc chuyển sang mô hình **serverless** sẽ giúp tiết kiệm chi phí, giảm độ phức tạp trong việc quản lý hệ thống và cung cấp khả năng mở rộng linh hoạt hơn.

---

## 3. 🏗️ Solution Architecture (25%)

### High-Level Architecture Diagram
![Kiến trúc hệ thống serverless](images/system-architecture-overview.jpg)
*Sơ đồ tổng quan kiến trúc hệ thống serverless với các dịch vụ AWS.*

### AWS Services Selection with Justification
- **Lambda**: Chạy mã mà không cần quản lý máy chủ, giúp giảm chi phí và dễ dàng mở rộng.
- **API Gateway**: Quản lý các API RESTful, cung cấp bảo mật thông qua API Key.
- **DynamoDB**: Cơ sở dữ liệu NoSQL, dễ dàng mở rộng và hỗ trợ truy vấn nhanh chóng.
- **S3**: Lưu trữ tài liệu và dữ liệu sao lưu với chi phí thấp.
- **SES**: Gửi email xác nhận và thông báo qua AWS SES.
- **CloudFront**: Tối ưu hóa tốc độ phân phối nội dung toàn cầu với độ trễ thấp.

### Component Interactions & Data Flow
- **API Gateway** nhận yêu cầu từ người dùng và chuyển tiếp đến Lambda.
- **Lambda Functions** thực hiện các thao tác CRUD và tương tác với DynamoDB.
- **S3** lưu trữ các tài liệu và dữ liệu sao lưu, được tự động tải lên qua Lambda.
- **SES** gửi email xác nhận và thông báo cho người dùng.
  
### Security Architecture & Compliance
- **IAM Roles**: Đảm bảo chỉ những dịch vụ và người dùng có quyền mới có thể truy cập vào các tài nguyên.
- **Dữ liệu được mã hóa** tại **REST** và **transit** để bảo vệ thông tin.
- **Compliance**: Tuân thủ các tiêu chuẩn bảo mật và quy định của AWS.

### Scalability & Performance Considerations
- **Lambda** tự động mở rộng theo yêu cầu.
- **DynamoDB** hỗ trợ mở rộng theo nhu cầu và bảo đảm hiệu suất cao trong việc truy vấn và lưu trữ dữ liệu.

### Integration Points with Existing Systems
Ứng dụng dễ dàng tích hợp với các hệ thống quản lý sinh viên hiện có thông qua API Gateway.

---

## 4. 🔧 Technical Implementation (20%)

### Implementation Phases with Deliverables
1. **Phase 1**: Thiết kế hệ thống và cấu hình API Gateway, Lambda, DynamoDB (Tháng 1).
2. **Phase 2**: Tích hợp Amazon S3, SES và bảo mật IAM (Tháng 2).
3. **Phase 3**: Kiểm thử, triển khai và tối ưu hóa (Tháng 3).

### Technical Requirements
- **Compute**: AWS Lambda.
- **Storage**: Amazon DynamoDB, S3.
- **Network**: API Gateway, CloudFront.

### Development Approach & Methodologies
- **Agile Development**: Phát triển qua các sprint 2 tuần, kiểm tra và đánh giá kết quả liên tục.
- **CI/CD**: Tự động hóa quá trình kiểm thử và triển khai với AWS CodePipeline.

### Testing Strategy
- **Unit Testing**: Kiểm tra chức năng từng Lambda.
- **Integration Testing**: Kiểm tra các kết nối giữa Lambda, DynamoDB, và S3.
- **Performance Testing**: Đảm bảo hệ thống đáp ứng tốt dưới tải cao.

### Deployment Plan & Rollback Procedures
- **Deployment**: Triển khai từng module lên AWS.
- **Rollback**: Sử dụng CloudFormation để quản lý cấu hình và quay lại trạng thái ổn định khi cần.

### Configuration Management
- **AWS CloudFormation** để quản lý và triển khai hạ tầng tự động.

---

## 5. 📅 Timeline & Milestones (10%)

### Project Phases Breakdown
1. **Tháng 1**: Xây dựng API Gateway, Lambda Functions, và DynamoDB.
2. **Tháng 2**: Tích hợp S3, SES và IAM bảo mật.
3. **Tháng 3**: Kiểm thử và triển khai.

### Key Milestones with Success Criteria
- **Milestone 1**: Hoàn thành API Gateway và Lambda Functions.
- **Milestone 2**: Hoàn thành tích hợp với S3, SES và IAM.
- **Milestone 3**: Kiểm thử và triển khai thành công hệ thống.

### Dependencies Identification
- Phụ thuộc vào việc thiết lập chính xác IAM Roles và cấu hình DynamoDB.

### Critical Path Analysis
- Các mốc quan trọng là tích hợp S3 và cấu hình bảo mật IAM.

### Resource Allocation Plan
- Phân bổ nhân lực cho mỗi giai đoạn: phát triển API, Lambda, bảo mật.

### Buffer Time for Risks
- Dự phòng thời gian cho các vấn đề phát sinh trong giai đoạn kiểm thử.

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
