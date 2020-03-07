# Cài đặt và cấu hình
1. Tạo tài khoản aws
2. Tạo một instance <span class="gold-text">AWS EC2 Ubuntu 18.04</span>
3. Lưu key <span class="gold-text">xxx.pem</span> của instance về local 
4. Vào tab <span class="gold-text">Elastic Ips</span> tạo một Ip mới và associate với instance vừa tạo
5. Connect với instance từ local bằng lệnh
    ```bash
    ssh -i "xxx.pem" ubuntu@[your aws host]
    ```
6. Cài đặt essential package
    ```bash
    sudo apt-get update && sudo apt-get install build-essential
    ```
7. Cài đặt erlang
    1. Thêm repository vào apt
    ```bash
    wget -O- https://packages.erlang-solutions.com/ubuntu/erlang_solutions.asc | sudo apt-key add -
    ```
    2. Upgrade apt repository
    ```bash
    sudo apt update && sudo apt upgrade
    ```
    3. Cài đặt erlang
    ```bash
    sudo apt -y install erlang
    ```
8. Cài đặt EMQ
    1. Clone repository từ git
    ```bash
    git clone -b v4.0.0 https://github.com/emqx/emqx-rel.git
    ```
    2. Cài đặt sử dụng make
    ```bash
    cd emqx-rel && make
    ```
    3. Kiểm tra cài đặt thành công
    ```bash
    cd _build/emqx/rel/emqx && ./bin/emqx console
    ```
    4. Chạy server (thoát cái lệnh trên nhé ;))
    ```bash
    ./bin/emqx start
    ```


<style>
.gold-text {
  color: 	#D4AF37
}
</style>