# cbc_video_extractor
Bookmarklet that extracts the main M3U8 file from the CBC Player.

## M3U8 File
The URL to the m3u8 file gets copied into the Clipboard after running the bookmarklet.

## MP4 File or any other video format
To get a MP4 file of the video, use **VLC Player** to Convert/Save the Network URL to your desired format.


See the code below:

```javascript
javascript:var p=window.performance.getEntries(),urls=[];if(p.forEach(function(e){e.name.indexOf("m3u8")>0&&e.name.indexOf("index_0")>0&&urls.push(e.name)}),1==urls.length){var url=urls[0].substring(0,urls[0].indexOf("?"));navigator.clipboard.writeText(url),alert("Video URL Copied")}else urls.length>1?(console.log(urls),alert("Multuple URLs detected - see console")):alert("No video detected - play the video first");
```