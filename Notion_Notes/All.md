# I. Vim/Vi
- Dưới đây là một số lệnh thường dùng trong chế độ lệnh:

- **Di chuyển con trỏ:**
    - **h:** Di chuyển con trỏ sang trái một ký tự.
    - **j:** Di chuyển con trỏ xuống một dòng.
    - **k:** Di chuyển con trỏ lên một dòng.
    - **l:** Di chuyển con trỏ sang phải một ký tự.
- **Chỉnh sửa văn bản:**
    - **i:** Chuyển sang chế độ chèn.
    - **d:** Xóa ký tự hiện tại.
    - **dd:** Xóa dòng hiện tại.
    - **yy:** Sao chép dòng hiện tại.
    - **p:** Dán văn bản đã sao chép hoặc cắt.
- **Tìm kiếm và thay thế:**
    - **/từ:** Tìm kiếm từ "từ" trong tài liệu.
    - **n:** Di chuyển đến lần xuất hiện tiếp theo của từ "từ".
    - **Ctrl + n:** Di chuyển đến lần xuất hiện trước đó của từ "từ".
    - **:s/từ/thay-the/g:** Thay thế tất cả các lần xuất hiện của từ "từ" bằng "thay-the".
- **Lệnh khác:**
    - **:q:** Thoát khỏi Vim mà không lưu.
    - **:wq:** Thoát khỏi Vim và lưu các thay đổi.
    - **:set nu:** Hiển thị số dòng trong tài liệu.
    - **:set nonu:** Ẩn số dòng trong tài liệu.
- u: Undo
- ggdG: Xóa toàn bộ văn bản

# II. Yum
- Là một công cụ quản lý gói phổ biến trong các hệ điều hành Linux sử dụng hệ thống quản lý gói RPM (Red Hat Package Manager) như CentOS, Fedora, và RHEL (Red Hat Enterprise Linux). **`yum`** được sử dụng để cài đặt, cập nhật, xóa bỏ và quản lý các gói phần mềm trên hệ thống.
    
    Dưới đây là một số ví dụ về cách sử dụng **`yum`**:
    
     **Cài đặt một gói:**
        
        yum install <tên-gói>
        
     **Cập nhật tất cả các gói:**
        
        yum update
        
     **Cập nhật một gói cụ thể:**
        
        yum update <tên-gói>
        
     **Xóa một gói:**
        
        yum remove <tên-gói>
        
     **Tìm kiếm gói:**
        
        yum search <tên-gói>
        
     **Hiển thị thông tin về gói:**
        
        yum info <tên-gói>
    
    Lưu ý rằng các phiên bản mới của hệ điều hành Linux có thể sử dụng **`dnf`** thay vì **`yum`** làm công cụ quản lý gói mặc định. Tuy nhiên, **`yum`** thường vẫn được hỗ trợ và sử dụng trong nhiều trường hợp.
# III. Nginx
- NGINX, engine-ex, là một phần mềm web server mã nguồn mở.
    - Ban đầu, nó được sử dụng để phục vụ web HTTP. Tuy nhiên, ngày nay nó cũng được dùng làm reverse proxy, HTTP load balancer và email proxy như IMAP, POP3, và SMTP.
    - Mục đích giải quyết vấn đề C10k - giới hạn của việc xử lý 10 ngàn kết nối cùng lúc. NGINX sử dụng kiến trúc hướng sự kiện (event-driven) không đồng bộ (asynchronous), giúp nó có khả năng xử lý hàng ngàn kết nối mà không gặp rắc rối.
    - Vì khả năng mạnh mẽ này, nhiều website có lượng traffic lớn đã sử dụng dịch vụ NGINX, bao gồm các ông lớn công nghệ như Google, Netflix, Adobe, Cloudflare, và WordPress.
    - So với Apache, một web server phổ biến khác, NGINX có hiệu suất cao hơn nhờ kiến trúc đơn luồng, hướng sự kiện. Ngoài ra, NGINX còn có thể thực hiện các chức năng quan trọng khác như load balancing, HTTP caching.

# IV. Systemd & Systemctl
- systemctl là một công cụ quản lý dịch vụ trong hệ điều hành Linux, đặc biệt là trong các phiên bản sử dụng systemd như CentOS, Fedora, Ubuntu 15.04 trở đi và một số bản phân phối Linux khác. Systemd là một hệ thống khởi động và quản lý dịch vụ
- Nó được sử dụng để khởi động, dừng, kiểm tra trạng thái, xem thông tin chi tiết, và quản lý các file cấu hình của các dịch vụ.
- Dưới đây là một số ví dụ về cách sử dụng lệnh `systemctl`:
 **Kiểm tra trạng thái của một dịch vụ:**
    
    ```
    systemctl status <tên-dịch-vụ>
    
    ```
    
 **Khởi động một dịch vụ:**
    
    ```
    systemctl start <tên-dịch-vụ>
    
    ```
    
 **Dừng một dịch vụ:**
    
    ```
    systemctl stop <tên-dịch-vụ>
    
    ```
    
 **Khởi động lại một dịch vụ:**
    
    ```
    systemctl restart <tên-dịch-vụ>
    
    ```
    
 **Bật dịch vụ tự động chạy khi khởi động hệ thống:**
    
    ```
    systemctl enable <tên-dịch-vụ>
    
    ```
    
 **Tắt dịch vụ tự động chạy khi khởi động hệ thống:**
    
    ```
    systemctl disable <tên-dịch-vụ>
    
    ```
    
 **Hiển thị danh sách tất cả các dịch vụ và trạng thái:**
    
    ```
    systemctl list-units --type=service
    
    systemctl list-units --type=service --state=running
    ```
    
 **Hiển thị danh sách các dịch vụ đã bật tự động:**
    
    ```
    systemctl list-unit-files --type=service
    
    ```
    

- Lệnh `systemctl` cung cấp một cách linh hoạt để quản lý các dịch vụ và các phần của hệ thống, giúp người quản trị hệ thống Linux dễ dàng thực hiện các tác vụ quản lý hệ thống hàng ngày.
