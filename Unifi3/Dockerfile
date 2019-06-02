ARG version=ltsc2016
FROM mcr.microsoft.com/windows/servercore:$version

RUN powershell -Command \
 $ErrorActionPreference =  'Stop'; \
 (New-Object System.Net.WebClient).Downloadfile('http://javadl.oracle.com/webapps/download/AutoDL?BundleId=210185', 'C:\jre-8u91-windows-x64.exe') ; \
 Start-Process -filepath C:\jre-8u91-windows-x64.exe -passthru -wait -argumentlist "/s,INSTALLDIR=c:\Java\jre1.8.0_91,/L,install64.log" ; \
 Remove-Item C:\jre-8u91-windows-x64.exe -Force
 
RUN powershell -Command \
 $ErrorActionPreference =  'Stop'; \
 (New-Object System.Net.WebClient).Downloadfile('https://dl.ubnt.com/unifi/5.10.23/UniFi-installer.exe', 'C:\UniFi-installer.exe') ; \
 Start-Process -filepath C:\UniFi-installer.exe -passthru -wait -argumentlist "/S" ; \
 Remove-Item C:\UniFi-installer.exe -Force

EXPOSE 6789/tcp 8080/tcp 8443/tcp 8880/tcp 8843/tcp 3478/udp
