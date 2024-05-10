# How to activate Windows

1. Press windows key and typed "cmd" in the search bar
2. Right click **"Command Prompt" and choose "Run as administrator"**
3. Click "yes" when it asks "Do you want to allow this app to make changes to your device?"
4. Once in command prompt, copy the following text: `slmgr /ipk`
5. Paste it into command prompt and **do not press Enter on your keyboard**
6. Go into your windows search bar and type "System Information", then open "**System Information"**
7. At the top, it will say OS Name. Remember what your OS Name is, in my case it is "Microsoft Windows 10 Home". Dependant on what your OS Name is, copy the code from below.

```cmd
Win 10 Home: TX9XD-98N7V-6WMQ6-BX7FG-H8Q99  
Win 10 Home N: 3KHY7-WNT83-DGQKR-F7HPR-844BM  
Win 10 Home Single Language: 7HNRX-D7KGG-3K4RQ-4WPJ4-YTDFH  
Win 10 Home Country Specific: PVMJN-6DFY6-9CCP6-7BKTT-D3WVR  
Win 10 Professional: W269N-WFGWX-YVC9B-4J6C9-T83GX  
Win 10 Professional N: MH37W-N47XK-V7XM9-C7227-GCQG9  
Win 10 Education: NW6C2-QMPVW-D7KKK-3GKT6-VCFB2  
Win 10 Education N: 2WH4N-8QGBV-H22JP-CT43Q-MDWWJ  
Win 10 Enterprise: NPPR9-FWDCX-D2C8J-H872K-2YT43  
Win 10 Enterprise N: DPH2V-TTNVB-4X9Q3-TJR4H-KHJW4
```

8. Paste the string of letters and numbers into command prompt, make sure there is a space between **"slmgr /ipk"** and your string of numbers and letters. It should look something like this: `slmgr /ipk 7HNRX-D7KGG-3K4RQ-4WPJ4-YTDFH`
9. Press enter on your keyboard and wait for a few seconds, a message should pop up on your screen: **"Installed product key (...)"**. Press ok
10. Paste this into command prompt: `slmgr /skms kms8.msguides.com`
11. Press enter and a message should pop up on your screen: **"Key Management Service machine name set to kms8.msguides.com successfully."** Press ok
12. Then, paste this into command prompt: `slmgr /ato`
13. Press enter, and wait for 10-60 seconds and this message should pop up: **"Activating Windows (...) Product activated successfully."**. Press ok

Windows should now be activated.