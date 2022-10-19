# 2022-10-19
## Operating System (OS)
- what is Operating System?
-常見的作業系統:
  - 伺服器常用作業系統
   -檔案伺服器（Files server）網路附接儲存(NAS)
   -資料庫伺服器（database server）MySQL，MariaDB
   -郵件伺服器（mail server）Sendmail、Postfix
   -網頁伺服器（Web server）Apache、lighttpd
   -FTP伺服器（FTP server）vs-ftpd
    (https://zh.wikipedia.org/zh-tw/%E6%9C%8D%E5%8A%A1%E5%99%A8)
   
  -手機作業系統
   -Android
   -Symbian
   -iOS
   
  -雲端作業系統 
   -Glide OS (https://sls.weco.net/node/21342)
- 作業系統的功能與服務 
- 作業系統的運作模式:Dual mode operation - 雙重模式
- user mode vs Kernel Mode
   - 為了避免一個使用者的程式修改其他使用者的程式甚至是系統核心， 並且更進一步，讓作業系統可以壟斷所有的硬體資源，
    大部分的機器(或者 CPU)至少會有二個執行特權(privilege)：Kernel mode (又稱 System mode) 與 User mode。
    
   - 1. 之所以要有 Kernel mode 和 User mode 之分，是因為我們希望作業系統可以壟斷所有的硬體操作，讓一般的程式不能亂搞。
  
   - 2. Kernel mode 就是萬能的，只要是 CPU 能管的硬體，Kernel mode 的程式就可以透過 machine code 來操作該硬體。
  
   - 3. 3. User mode is basically a "restricted" mode. Do nothing but some harmless behavior.
  [https://medicineyeh.wordpress.com/2015/02/10/kernel-mode-%E8%88%87-user-mode-%E7%9A%84%E6%A6%82%E5%BF%B5/]
  
 - kernal vs shell
   -核心（Kernel|內核）
      - 外核心系統，也被稱為縱向結構作業系統，是一種比較極端的設計方法,它的設計理念是讓使用者程式的設計者來決定硬體介面的設計。外核心本身非常的小，它通常只負責系統保護和系統資源復用相         關的服務。
     
      - 傳統的核心設計（包括單核和微核）都對硬體作了抽象，把硬體資源或裝置驅動程式都隱藏在硬體抽象層下。比方說，在這些系統中，如果分配一段物理儲存，應用程式並不知道它的實際位置。

      - 而外核的目標就是讓應用程式直接請求一塊特定的物理空間，一塊特定的磁碟塊等等。系統本身只保證被請求的資源當前是空閒的，應用程式就允許直接存取它。既然外核系統只提供了比較低階的硬         體操作，而沒有像其他系統一樣提供進階的硬體抽象，那麼就需要增加額外的執行庫支援。這些執行庫執行在外核之上，給使用者程式提供了完整的功能。
  
## Linux Operating System[教學影片](https://youtu.be/rYYKST4rG40)
- linux kernal [英文版WIKI](https://en.wikipedia.org/wiki/Linux_kernel) [中文版WIKI](https://zh.wikipedia.org/wiki/Linux%E5%86%85%E6%A0%B8)
   - [The Linux Kernel Archives](https://www.kernel.org/)
   - [torvalds/linux: Linux kernel source tree](https://github.com/torvalds/linux)
   - [Linux Kernel Programming](https://www.tenlong.com.tw/products/9781789953435?list_name=srh)
- linux shell [英文版WIKI](https://en.wikipedia.org/wiki/Unix_shell) [中文版WIKI](https://zh.wikipedia.org/wiki/Unix_shell)
    - A Unix shell is a `command-line interpreter` or shell that provides a command line user interface for Unix-like operating systems. 
    - The shell is both an interactive command language and a scripting language, and is used by the operating system to control the execution of the system using shell scripts
    - 有許多shell: BASH(Bourne Again SHell) csh(The C shell)
    - 檢查你(使用者)登入時所用的shell
        - finger root 
    - [How to Change your Login Shell](https://gps.uml.edu/tutorials/unix-linux/unix/shell.htm#:~:text=To%20change%20your%20shell%20use,prompts%20for%20the%20new%20one.)
        - chsh
  - Linux commands(指令)
    - 請下載ova[SecurityFirst2022](https://github.com/MyFirstSecurity2020/SecurityFirst2022/tree/main/DAY1/HappyLinuxDay/1.linux%E5%9F%BA%E7%A4%8E%E5%85%A5%E9%96%80) 
    - [Linux 指令大全：工程師活用命令列技巧的常備工具書 (全新升級版) ](https://www.tenlong.com.tw/products/9786263331075?list_name=srh)
    - 學習linux 指令
      - find --help
      - 指令與指令參數 
      - ls -al  | ls -A  | ls -a |ls -l | 
    - 基本指令 ls , pwd, cd, 
    - linux檔案處理指令  cp rm chmod...
    - linux檔案壓縮與打包指令 zip tar uzip ...
    - linux系統管理指令  ps top ...
    - Linux記憶體臉管理指令 free ...
    - Linux硬碟管理指令 df(diskfree)  du(disk usage)
    - linux使用者管理指令  useradd userdel passwd
    - Linux網路指令 wget ssh ...
  - shell programming(Linux Shell Script)
    - 網站學習資源 [Shell 教程](https://www.runoob.com/linux/linux-shell.html)
    - 書[shell 腳本實戰](https://www.tenlong.com.tw/products/9787115506887?list_name=srh)
    - 教學影片[Shell Scripting Tutorial | Shell Scripting Crash Course | Linux Certification Training | Edureka](https://www.youtube.com/watch?v=GtovwKDemnI)
    - [簡明 Linux Shell Script 入門教學](https://blog.techbridge.cc/2019/11/15/linux-shell-script-tutorial/)
    - 簡單範例
```
gedit xxx.sh
chmod +755 xxx.sh
./xxx.sh 
```
```
# 宣告使用 /bin/bash
#!/bin/bash

echo "=== 將目前執行 process 的 PID 依照數字大小排序，取出前 10 名 === "

# ps 為列出 process 相關資訊，透過 | pipe 管線傳遞資料。
# awk 可以根據 pattern 進行資料處理（這邊印出第一欄 PID）
# sort 是進行排序，其排序時，預設都是把資料當作字串來排序
# 若想讓資料根據實際數值的大小來排序，可以加上 -n 參數。
# -r 則是由大到小排序，預設是由小到大
ps | awk '{print $1}' | sort -rn | head -10
```
  - linux `distribution(發行版本)`
    - kali
    - Red Hunt
    - security Onion
    - Ubuntu  
## Windows Operating System
- Windows kernal
- Windows shell (Windows 有兩個命令行 shell：Command shell 和PowerShell)
  - cmd(Command shell)
  - [windows commands](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands) 
  - 作業1: 20個 windows 指令(含網路指令 ping netstat ....)
  - 作業2: 開啟記事本(notepad.exe | calc.exe)  使用taskkill殺掉
     - [How To Kill A Process In Windows 11](https://www.c-sharpcorner.com/article/how-to-kill-a-process-in-windows-11/) 
  - 作業3: task manager 
      - netstat /?
      - netstat -ano
      - taskkill /PID 18354 /F 
   - powershell
     - powershel cmdlet 
       - 指令格式: 動詞-名詞 get-process 
     - powershell programming
       - 👍[PowerShell 使用者入門 powershell 101](https://learn.microsoft.com/zh-tw/powershell/scripting/learn/ps101/01-getting-started?view=powershell-7.2)
       - 👍[適用於系統管理的範例指令碼](https://learn.microsoft.com/zh-tw/powershell/scripting/samples/sample-scripts-for-administration?view=powershell-7.2)
       - [PowerShell Documentation](https://learn.microsoft.com/en-us/powershell/)
       - [PowerShell 流程自動化攻略](https://www.tenlong.com.tw/products/9789865026677?list_name=srh) 
 

### 經典教科書 [作業系統, 10/e (授權經銷版)(Silberschatz: Operating System Concepts, 10/e)](https://www.tenlong.com.tw/products/9789865522506?list_name=srh)
```
Part 1 總　論
CHAPTER 1　概　　說
CHAPTER 2　作業系統結構

Part 2 行程管理
CHAPTER 3　行程觀念
CHAPTER 4　執行緒與並行性
CHAPTER 5　CPU 排班

Part 3 行程同步
CHAPTER 6　同步工具
CHAPTER 7　同步範例
CHAPTER 8　死　結

Part 4 記憶體管理
CHAPTER 9　主記憶體
CHAPTER 10　虛擬記憶體

Part 5 儲存裝置
CHAPTER 11　大量儲存結構檔案系統
CHAPTER 12　輸入/輸出系統

Part 6 檔案系統
CHAPTER 13　案系統介面檔
CHAPTER 14　檔案系統的製作
CHAPTER 15　檔案系統內部

Part 7 安全與保護
CHAPTER 16　安　全
CHAPTER 17　保　護

Part ８ 進階主題
CHAPTER 18　虛擬機
CHAPTER 19　網路與分散式系統

Part 9 個案研究
CHAPTER 20　Linux 系統
CHAPTER 21　Windows 10
```
