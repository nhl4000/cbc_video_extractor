# cbc_video_extractor
Bookmarklet that extracts the main M3U8 file from the CBC Player

javascript:var p=window.performance.getEntries(),urls=[];if(p.forEach(function(e){e.name.indexOf("m3u8")>0&&e.name.indexOf("index_0")>0&&urls.push(e.name)}),1==urls.length){var url=urls[0].substring(0,urls[0].indexOf("?"));navigator.clipboard.writeText(url),alert("Video URL Copied")}else urls.length>1?(console.log(urls),alert("Multuple URLs detected - see console")):alert("No video detected - play the video first");