ARG version=ltsc2016
FROM mcr.microsoft.com/windows/servercore:$version

RUN powershell (new-object System.Net.WebClient).Downloadfile('http://javadl.oracle.com/webapps/download/AutoDL?BundleId=210185', 'C:\jre-8u91-windows-x64.exe')
RUN powershell start-process -filepath C:\jre-8u91-windows-x64.exe -passthru -wait -argumentlist "/s,INSTALLDIR=c:\Java\jre1.8.0_91,/L,install64.log"
RUN del C:\jre-8u91-windows-x64.exe

RUN powershell (new-object System.Net.WebClient).Downloadfile('https://dl.ubnt.com/unifi/5.10.23/UniFi-installer.exe', 'C:\UniFi-installer.exe')
RUN powershell start-process -filepath C:\UniFi-installer.exe -passthru -wait -argumentlist "/S"
