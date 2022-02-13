# github-demo

## 如何使用github

### 使用SSH連線
1. 新增金鑰
```bash=
# 1.建立金鑰
ssh-keygen
# 或
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
> Enter file in which to save the key (/c/Users/user/.ssh/id_rsa):
# 金鑰存放路徑，直接按 Enter 
> Enter passphrase (empty for no passphrase):
# 密碼，可設定可不設定，設定的話每次上傳會多需要輸入一次密碼
> Enter same passphrase again:
# 再輸入一次密碼
> The key fingerprint is:
# 之後會顯示你的 fingerprint，到這裡就完成 key 的產生了

# 2.啟動金鑰代理
eval "$(ssh-agent -s)"
# 3.將私鑰加入到 SSH 代理上
ssh-add ~/.ssh/<私鑰檔名>
# 4.查看公鑰
cat ~/.ssh/<公鑰檔名>.pub
```
2. 上傳金鑰到github
+ 方法一：存儲庫金鑰
  + 進入 repository 頁面
  + 到 Settings > Deploy keys
  + Add deploy key，填入 Title 與 Key 後
  + 打勾 Allow write access 後即可送出。
+ 方法二：全域金鑰
  + 進入 GitHub 頁面
  + 到 Settings > SSH and GPG keys 的設定頁面
  + New SSH Key，填入 Title 與 Key 後即可送出。

3. 測試ssh
```bash=
# 驗證ssh
ssh -T git@github.com
> Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
# 如果收到上面的訊息 就可以開始上傳檔案了
```

## 透過Pull Request來合併分支
### Step.1：Local端
+ 新增分支  
![image](https://user-images.githubusercontent.com/74607966/153766314-4b5c71a5-b6c3-43e3-94d6-db300e360d5e.png)
+ 修改完成後Push分支  
![image](https://user-images.githubusercontent.com/74607966/153766406-480b5d42-edce-4431-8427-4f5750329120.png)
### Step.2：Github端
+ 點擊New Pull Request(或是直接點擊Compare & pull request)  
![image](https://user-images.githubusercontent.com/74607966/153766463-51ea179d-83db-4a65-b729-59c6d67b90eb.png)
+ 選擇分支後，點Create  
![image](https://user-images.githubusercontent.com/74607966/153766547-50c7e895-0038-4888-8ee9-6ced82af1287.png)
+ 輸入一些評論後，點Create pull request  
![image](https://user-images.githubusercontent.com/74607966/153766597-59a0ccd2-74ae-48c7-9677-5a942a9b5658.png)
+ 合併分支  
![image](https://user-images.githubusercontent.com/74607966/153766752-6eb21c8c-e235-47a8-bcd7-a2b1afbfe3f3.png)
+ 完成後，可將分支刪除  
![image](https://user-images.githubusercontent.com/74607966/153766795-ca0e71d2-e032-44aa-b2b3-113dfb1c3dac.png)
+ 確認成功合併
![image](https://user-images.githubusercontent.com/74607966/153767088-f7ab6354-b848-4b40-9cd4-1e8fa1955c7a.png)
