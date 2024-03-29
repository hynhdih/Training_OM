# 1. Cài đặt Control Machine trên Centos 7
  - Thực hiện lệnh update và cài gói epel-release:
  ```
  yum update -y
  yum install epel-release -y
  ```
  - Thực hiện lệnh để cài Ansible:
  ```
  yum install ansible -y 
  ```
  - Sau khi cài đặt xong thực hiện lệnh sau để kiểm tra phiên bản của Ansible:
  ```
  [root@huynd ~]# ansible --version
  ansible 2.9.27
    config file = /etc/ansible/ansible.cfg
    configured module search path = [u'/root/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']
    ansible python module location = /usr/lib/python2.7/site-packages/ansible
    executable location = /usr/bin/ansible
    python version = 2.7.5 (default, Nov 14 2023, 16:14:06) [GCC 4.8.5 20150623 (Red Hat 4.8.5-44)]
  ```
# 2. Cài đặt trên Managed Node centOS 8
  - Phía Client không cài đặt ansible, chỉ cần cài đặt openssh-server và python
  ```
  yum install openssh-server -y
  ```
  - Kiểm tra phiên bản python có sẵn:
  ```
  [root@huynd ~]# python --version
  Python 2.7.5
  ```
# 3. Cấu hình Ansible
## 3.1 File hosts
  - File host chứa danh sách các server đích được quản lý bởi Ansible.
  - Vị trí file mặc định: /etc/ansible/hosts
  - Cấu hình ví dụ như sau:
  ```
  [web_servers]
  centos-8 ansible_host=192.168.33.128 ansible_ssh_user=root
  ```
## 3.2 Cấu hình SSH key
  - Trên Node Ansible Management
    - Tạo ssh key:
      ```
      ssh-keygen -t rsa
      ```
    - Copy file ~/.ssh/id_rsa.pub lên Node Client bằng cách sử dụng lệnh sau:
      ```
      ssh-copy-id -i ~/.ssh/id_rsa.pub root@192.168.33.128
      ```
## 3.3 Modules system
  - Kiểm tra kết nối giữa Node Ansible Management và Node Client, sử dụng -m ping:
    ```
    ansible -m ping all
    ```
## 3.4 Tạo file playbook
  - Tạo Ansible playbook install Nginx trên máy Ansible Management. Tạo file mới với tên nginx-install.yml
    ```
    vi nginx-install.yml
    ```
  - Trong file playbook, định nghĩa hosts, tasks, and roles:
    ```
    ---
    - name: Install Nginx
      hosts: web_servers
      become: yes
    
      tasks:
        - name: Install EPEL repository
          yum:
            name: epel-release
            state: present
            update_cache: true
    
        - name: Install Nginx
          yum:
            name: nginx
            state: present
    
        - name: Start Nginx service
          service:
            name: nginx
            state: started
            enabled: yes
    ```
  - Trong file playbook trên, định nghĩa 3 tasks:
    - Install the EPEL repository, cung cấp Nginx package
    - Install Nginx
    - Start Nginx service và enable khi khởi động
## 3.5 Chạy Playbook
  - Sử dụng command:
    ```
    ansible-playbook nginx-install.yml
    ```
