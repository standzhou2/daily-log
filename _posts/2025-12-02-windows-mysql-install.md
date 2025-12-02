以下是通过 ZIP 方式在 Windows 上安装 MySQL 的步骤：

### 1. 下载 MySQL ZIP 包
- 前往 [MySQL 官方下载页面](https://dev.mysql.com/downloads/mysql/)。
- 选择适合你的操作系统的 ZIP 安装包（一般为 Windows (x86, 64-bit), ZIP Archive）。
- 下载后解压到指定目录（例如 `C:\mysql`）。

---

### 2. 配置 MySQL
1. **创建配置文件**
   - 在解压目录中创建一个名为 `my.ini` 的文件。
   - 添加以下内容并根据需要调整参数：
     ```ini
     [mysqld]
     # 设置MySQL安装目录
     basedir=C:\mysql
     # 设置数据存储目录
     datadir=C:\mysql\data
     # 设置端口号
     port=3306
     # 允许最大连接数
     max_connections=200
     # 默认字符集
     character-set-server=utf8mb4
     ```

2. **初始化数据库**
   - 打开命令提示符（以管理员身份运行）。
   - 进入 MySQL 的解压目录下的 `bin` 文件夹，例如：
     ```cmd
     cd C:\mysql\bin
     ```
   - 初始化数据库：
     ```cmd
     mysqld --initialize --console
     ```
   - 记录输出的随机临时密码（形如 `root@localhost: <随机密码>`）。

---

### 3. 安装并启动 MySQL 服务
1. **安装服务**
   ```cmd
   mysqld --install MySQL
   ```
   如果成功，将显示 `Service successfully installed.`。

2. **启动服务**
   ```cmd
   net start MySQL
   ```

3. **停止服务（可选）**
   ```cmd
   net stop MySQL
   ```

---

### 4. 登录 MySQL
1. **进入 MySQL CLI**
   ```cmd
   mysql -u root -p
   ```
   系统会提示你输入之前初始化时生成的随机密码。

2. **修改 MySQL 密码（可选）**
   如果需要更改密码，可以执行以下命令：
   ```sql
   ALTER USER 'root'@'localhost' IDENTIFIED BY '新密码';
   FLUSH PRIVILEGES;
   ```

---

### 5. 配置环境变量（可选）
- 将 `C:\mysql\bin` 添加到系统的环境变量 `PATH` 中，方便直接运行 MySQL 命令。

---

完成上述步骤后，你就可以在 Windows 上通过 ZIP 方式成功安装并运行 MySQL！

### 6. 常见命令
```
# 登录 MySQL
mysql -u root -p

# 输入密码后，在 MySQL 提示符下执行：
CREATE DATABASE mydb CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

# 执行sql文件
SOURCE /path/to/your/file.sql;

mysql -u 用户名 -p database_name < /path/to/file.sql

```
