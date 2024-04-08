# I. Lệnh Git cơ bản:

1. **git init**: Tạo một kho lưu trữ Git mới trong thư mục hiện tại.
  $ git init
3. **git clone [url]**: Sao chép một kho lưu trữ Git đã tồn tại từ một URL (địa chỉ web hoặc đường dẫn tới kho lưu trữ).
  $ git clone https://example.com/repository.git
4. **git add [file]**: Thêm tệp đã chỉ định vào chỉ mục (staging area) để chuẩn bị cho việc commit.
  $ git add index.html
5. **git add .**: Thêm tất cả các thay đổi trong thư mục hiện tại vào chỉ mục.
  
6. **git commit -m "[message]"**: Tạo một commit mới với các tệp đã được thêm và thông điệp kèm theo.
  $ git commit -m "Add index.html file"
7. **git status**: Xem trạng thái của các tệp trong thư mục làm việc hiện tại và các tệp đã thêm vào chỉ mục.
  
8. **git log**: Xem lịch sử commit của kho lưu trữ.
  
9. **git branch**: Liệt kê tất cả các nhánh hiện có và chỉ ra nhánh đang được checkout (hiện tại).
  
10. **git checkout [branch]**: Chuyển đổi sang một nhánh khác.
  $ git checkout feature-branch
11. **git merge [branch]**: Merge (hợp nhất) một nhánh khác vào nhánh hiện tại.
  $ git merge feature-branch
12. **git pull**: Lấy và merge các thay đổi từ kho lưu trữ từ xa (remote repository) vào nhánh hiện tại của bạn.
  $ git pull origin main
13. **git push**: Đẩy các commit cục bộ lên kho lưu trữ từ xa (remote repository).
  $ git push origin main
14. **git remote**: Liệt kê tất cả các remote repository mà local repository đang trỏ đến.
15. **git remote -v**: Hiển thị URL của các remote repository mà local repository đang trỏ đến.
16. **git fetch origin**: Lấy các thay đổi từ remote repository (ở đây là origin) nhưng không thực hiện merge với nhánh hiện tại.
17. **git restore [file]**: Khôi phục nội dung của tệp về phiên bản đã commit gần nhất trong kho lưu trữ.
    $ git restore index.html
18. **git reset [commit]**: Đặt lại trạng thái của local repository về commit trước đó.
    $ git reset HEAD~1
19. **git diff**: Hiển thị sự khác biệt giữa thay đổi chưa được stage và commit trong local repository.
20. **git tag [tagname]**:
    $ git tag v1.0.0 : Tạo một tag với tên là v1.0.0 cho commit hiện tại.

# II. Luồng làm việc thông thường khi sử dụng Git thường đi qua các bước sau:

1. **Khởi tạo kho lưu trữ (repository)**:
   - Bắt đầu bằng cách tạo một kho lưu trữ mới (hoặc sao chép một kho lưu trữ đã tồn tại).
   - Sử dụng lệnh `git init` để khởi tạo một kho lưu trữ mới trong thư mục làm việc của bạn hoặc sử dụng `git clone [url]` để sao chép một kho lưu trữ từ xa.

2. **Phát triển công việc**:
   - Tạo, chỉnh sửa và xóa các tệp trong dự án của bạn.
   - Sử dụng các lệnh như `git add` để đưa các thay đổi vào chỉ mục, và `git commit` để tạo các commit với thông điệp mô tả công việc đã thực hiện.

3. **Quản lý nhánh (branching)**:
   - Tạo và chuyển đổi giữa các nhánh để phát triển các tính năng, sửa lỗi hoặc thực hiện các nhiệm vụ khác mà không ảnh hưởng đến nhánh chính (thường là `main` hoặc `master`).
   - Sử dụng lệnh `git branch` để tạo và liệt kê các nhánh, và `git checkout` để chuyển đổi giữa chúng.

4. **Hợp nhất (merging)**:
   - Hợp nhất các thay đổi từ các nhánh phụ (feature branches) vào nhánh chính (ví dụ: `main`) khi công việc trên nhánh đã hoàn thành và kiểm tra.
   - Sử dụng lệnh `git merge` để hợp nhất các nhánh.

5. **Đồng bộ hóa với kho lưu trữ từ xa (remote repository)**:
   - Lấy các thay đổi mới từ remote repository bằng cách sử dụng `git fetch` hoặc `git pull`.
   - Đẩy các commit cục bộ của bạn lên remote repository bằng lệnh `git push`.

6. **Quản lý xung đột (conflict management)**:
   - Xử lý xung đột nếu có sự không phù hợp giữa các phiên bản của tệp giữa local repository và remote repository.
   - Sử dụng `git status`, `git diff`, và các công cụ hỗ trợ khác để giải quyết xung đột.

7. **Quản lý phiên bản (version control)**:
   - Sử dụng các tính năng như tags và release để đánh dấu các phiên bản quan trọng của dự án.
   - Sử dụng `git tag` để tạo các tag cho các commit quan trọng.

8. **Xem và xem lại lịch sử (history)**:
   - Sử dụng `git log` để xem lịch sử commit của kho lưu trữ.
   - Theo dõi và kiểm tra các thay đổi bằng cách sử dụng `git diff` và các công cụ khác.
