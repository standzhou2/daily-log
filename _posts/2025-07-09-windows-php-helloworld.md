1. **下载 PHP**  
   [PHP Windows 归档下载地址](https://windows.php.net/downloads/releases/archives/)

2. **解压**  
   解压到（假定你下载的是5.6.4的版本）：`D:\php-5.6.40-Win32-VC11-x64`

3. **设置 PHP 解释器的 配置文件**
   ```bash
   cd D:\php-5.6.40-Win32-VC11-x64
   cp php.ini-development php.ini
   ```

4. **命令使用**

   - 查看命令帮助信息
     ```bash
     .\php.exe --help
     ```

   - 启动内置 HTTP 服务器，监听 8888 端口，根目录为 `d:\phppage`
     ```bash
     .\php.exe -S localhost:8888 -t d:\phppage
     ```

   - 编写 Hello World 页面，放在 d:\phppage\index.php
     ```php
     <?php
     echo "Hello, World!";
     ?>
     ```

   - 浏览器访问：
     ```
     http://localhost:8888
     ```

5. **PHP 扩展**

   - 如果要使用扩展（如 mysql），需在 `php.ini` 中将扩展信息打开，编辑如下：

     ```ini
     extension_dir = "ext"
     extension=php_mysql.dll
     ```
