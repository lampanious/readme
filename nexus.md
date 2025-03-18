Sonatype Nexus Repository

Mục lục:
1. Tổng quan hệ thống
2. Hướng dẫn cài đặt và cấu hình hệ thống
3. Thông tin quản trị hệ thống
4. Phân quyền sử dụng hệ thống
5. Q&A
6. Thông tin tham khảo



##############

Tổng quan hệ thống
https://help.sonatype.com/en/sonatype-nexus-repository.html

- Sonatype Concept: https://help.sonatype.com/en/repository-manager-concepts.html 
- UI Overview
- Tính năng tìm kiếm trong hệ thống: https://help.sonatype.com/en/searching-for-components.html
- Tính năng đẩy file trong hệ thống: https://help.sonatype.com/en/uploading-components.html 

##############

Hướng dẫn cài đặt và cấu hình hệ thống

Cấu hình cơ bản: 
- Triển khai hệ thống bằng docker: https://hub.docker.com/r/sonatype/nexus3/ 
- Cài đặt hệ thống = systemd: https://help.sonatype.com/en/run-as-a-service.html
- Giải thích cài đặt: https://help.sonatype.com/en/directories.html
- Cấu hình môi trường chạy ứng dụng: https://help.sonatype.com/en/configuring-the-runtime-environment.html 
- Giải thích cấu trúc triển khai ứng dụng:
    - Tổng quan:  https://help.sonatype.com/en/sonatype-nexus-repository-reference-architectures.html 
    - Chi tiết phương án triển khai: https://help.sonatype.com/en/nexus-repository-reference-architecture-3.html
        - Triển khai DC1 proxy public repository <BM01>
        - Triển khai DC1 private repository <BM01>
- Hướng dẫn cấu hình cùng database (postgresql):
    - Guide install postgre: https://help.sonatype.com/en/install-nexus-repository-with-postgresql.html
    - Limitation connection: https://help.sonatype.com/en/postgresql-max-connections.html 
- Triển khai HA cho hệ thống: 
    - Tổng quan: https://help.sonatype.com/en/high-availability-deployment.html
    - Chi tiết phương án triển khai: 
        - Requirement: https://help.sonatype.com/en/system-requirements-for-high-availability-deployments.html 
        - Triển khai DC1 proxy public repository: https://help.sonatype.com/en/option-1---manual-high-availability-deployment.html
        - Triển khai DC1 private repository: https://help.sonatype.com/en/option-2---on-premises-high-availability-deployment-using-kubernetes.html 
- Cấu hình reverse proxy: https://help.sonatype.com/en/run-behind-a-reverse-proxy.html 
- File limitation: https://help.sonatype.com/en/adjusting-file-handle-limits.html

Tối ưu hệ thống:
- Tối ưu dung lượng sử dụng: https://help.sonatype.com/en/keeping-disk-usage-low.html 
- Memory Overview: https://help.sonatype.com/en/nexus-repository-memory-overview.html 
- Storage: 
    - Tổng quan: https://help.sonatype.com/en/storage-guide.html
    - Planning: https://help.sonatype.com/en/storage-planning.html

Nâng cấp hệ thống: 
- Thêm cấu hình plugin: https://help.sonatype.com/en/bundle-development.html 
- Giải pháp nâng cấp hệ thống:
    - Path: https://help.sonatype.com/en/nexus-repository-upgrade-paths.html (3.48.0+)
    - Database: https://help.sonatype.com/en/migrating-to-a-new-database.html 
- Hệ thống với các tính năng Professional (Recommend to explore): https://help.sonatype.com/en/nexus-repository-pro-features.html 
- Giải pháp Disaster Recovery(DR): 
    - https://help.sonatype.com/en/disaster-recovery-site.html
    - https://help.sonatype.com/en/combination-active-active-high-availability---disaster-recovery-site.html 

##############

Thông tin quản trị hệ thống

Repository
- Tổng quan: https://help.sonatype.com/en/repository-management.html
- Type: https://help.sonatype.com/en/repository-types.html
- Cấu hình repo: 
    - Tạo+ Xoá: https://help.sonatype.com/en/creating-or-deleting-repositories-in-nexus-repository.html
    - Các trường cấu hình: https://help.sonatype.com/en/configurable-repository-fields.html
    - Quản lý repo đang chạy: https://help.sonatype.com/en/buttons-for-managing-an-existing-repository-in-nexus-repository.html
- Tính năng Cleanup policies: https://help.sonatype.com/en/cleanup-policies.html
- Tính năng Routing: https://help.sonatype.com/en/routing-rules.html

Blobstore
- Tổng quan: https://help.sonatype.com/en/configuring-blob-stores.html
- Chi tiết trên từng Repo:
    - Triển khai DC1 proxy public repository <Mindset phân blobstore + đề xuất>
    - Triển khai DC1 private repository <đề xuất>
  
License
-  https://help.sonatype.com/en/installing-and-updating-licenses.html

Formats
-  https://help.sonatype.com/en/formats.html 

Tasks
- https://help.sonatype.com/en/tasks.html

Capabilities
- https://help.sonatype.com/en/capabilities.html

Nodes
- https://help.sonatype.com/en/nodes.html 

Các phần quản trị nâng cao
- SSL: https://help.sonatype.com/en/configuring-ssl.html
- HTTP, HTTPS requests: https://help.sonatype.com/en/http-and-https-request-and-proxy-settings.html
- Email: https://help.sonatype.com/en/email-server-configuration.html
- Retry limit config: https://help.sonatype.com/en/retry-limit-configuration.html
- Auditing: https://help.sonatype.com/en/auditing.html

Các tính năng hỗ trợ
-  https://help.sonatype.com/en/support-features.html 

##############

Phân quyền sử dụng hệ thống

- Access control:  https://help.sonatype.com/en/access-control.html
  <Đề xuất>

- User Authentication: https://help.sonatype.com/en/user-authentication.html
  <Đề xuất>

##############

Q&A
Best practice: https://help.sonatype.com/en/administration-best-practices.html
Question: 
1. Cài đặt = docker vs systemd, nên dùng cái nào? Tuỳ thuộc vào nhu cầu sử dụng, tuy nhiên để đảm bảo về mặt secure, nên lựa chọn cài đặt bằng docker. Tuy nhiên việc cài đặt bằng docker có issue liên quan đến việc không cài đặt được plugin custom cho hệ thống?
2. Làm thế nào để biết version của hệ thống nexus đang dùng?
3. Thông tin các bên liên quan khi cài đặt hệ thống?
4. Làm thế nào để biết các loại thư viện nào được hỗ trợ với version bao nhiêu?
5. License của version trước có thể apply cho version sau không? Đoán xem -.-
6. Làm thế nào để biết hệ thông đang không hoạt đông?

##############

Thông tin tham khảo

Vất hết đống link bên trên vào =))))
- Open Service Gateway Initivative: https://www.baeldung.com/osgi
- Karaf: https://karaf.apache.org/manual/latest/#_post_installation_steps

##############

