FROM mcr.microsoft.com/powershell

SHELL ["pwsh","-Command"]

RUN Invoke-WebRequest https://aka.ms/vs/17/release/vc_redist.x64.exe -OutFile vc_redist.x64.exe; `
    Start-Process .\vc_redist.x64.exe -ArgumentList '/install','/quiet','/norestart' -Wait; `
    Remove-Item .\vc_redist.x64.exe

RUN New-Item /ztAssessment -ItemType Directory

WORKDIR "/ztAssessment"

RUN Install-Module Az.Accounts -Force
RUN Install-Module Az.Websites -Force
RUN Install-Module Microsoft.Graph.Authentication -Force
RUN Install-Module ZeroTrustAssessment -Force
