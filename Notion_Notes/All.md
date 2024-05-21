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
        
        ```bash
        yum install <tên-gói>
        ```
        
     **Cập nhật tất cả các gói:**
        
        ```bash
        yum update
        ```
        
     **Cập nhật một gói cụ thể:**
        
        ```bash
        yum update <tên-gói>
        ```
        
     **Xóa một gói:**
        
        ```bash
        yum remove <tên-gói>
        ```
        
     **Tìm kiếm gói:**
        
        ```bash
        yum search <tên-gói>
        ```
        
     **Hiển thị thông tin về gói:**
        
        ```bash
        yum info <tên-gói>
        ```
    
    Lưu ý rằng các phiên bản mới của hệ điều hành Linux có thể sử dụng **`dnf`** thay vì **`yum`** làm công cụ quản lý gói mặc định. Tuy nhiên, **`yum`** thường vẫn được hỗ trợ và sử dụng trong nhiều trường hợp.
