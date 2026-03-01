FROM mcr.microsoft.com/powershell:lts-windowsservercore-ltsc2022

SHELL ["pwsh", "-NoLogo", "-NoProfile", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

RUN [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; \
    Set-PSRepository -Name PSGallery -InstallationPolicy Trusted

RUN New-Item -Path C:\ztAssessment -ItemType Directory -Force

WORKDIR C:\ztAssessment

RUN Install-Module Az.Accounts -Repository PSGallery -Scope AllUsers -Force -AllowClobber
RUN Install-Module Az.Websites -Repository PSGallery -Scope AllUsers -Force -AllowClobber
RUN Install-Module Microsoft.Graph.Authentication -Repository PSGallery -Scope AllUsers -Force -AllowClobber
RUN Install-Module ZeroTrustAssessment -Repository PSGallery -Scope AllUsers -Force -AllowClobber
