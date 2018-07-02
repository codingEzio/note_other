### 示例代碼
```youtube-dl --add-header "accept-encoding: identity" --proxy "127.0.0.1:1087" --no-check-certificate VIDEO_URL --verbose```

### 命令分塊
- ```youtube-dl```
	- ```-add-header "accept-encoding: identity" -no-check-certificate```
	- ```--proxy "127.0.0.1:1087"```
	- ```--verbose```
	- ```VIDEO_URL``` or ```PLAYLIST_URL```

### 下載
- 創建別名 <small>( 此处仅为示例, 随时会变更噢 )</small>
	- ```alias ytb="youtube-dl --add-header 'accept-encoding: identity' --proxy '127.0.0.1:1087' --no-check-certificate  --verbose "```
- 選擇分辨率
	- 參數 ```-F``` 察看 所有可用的分辨率
	- 選好後鍵入 ```-f``` 加上相應的 *format code* 
	- 如此: ```-f 308+251```
		> 視頻的格式碼須置於前

### 關於下載播放列表
- 優勢會存在 一些視頻被刪除或是變為了私有狀態 <br>此時加上參數 ```-i``` 即可 <small>( 其為 *--ignore-errors* )</small>

### 注意
- 複製視頻地址時 將 `\` 類似的轉義字符刪去 <small>( 视频 URL 须加上双引号 )</small>
- 另, Chrome 端的 IINA 插件也可基于之 而在线观看

### 手機端 Termux 
- ```termux-setup-storage``` <small>( 創建一個系统可讀到的文件夾 )</small>
- 下載后將文件 ```mv``` 至 ```storage/movies``` 即可