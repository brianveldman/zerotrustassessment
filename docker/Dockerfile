FROM mcr.microsoft.com/powershell

SHELL ["pwsh","-Command"]

RUN New-Item /ztAssessment -ItemType Directory

WORKDIR "/ztAssessment"

RUN Install-Module Az.Accounts -Force
RUN Install-Module Az.Websites -Force
RUN Install-Module Microsoft.Graph.Authentication -Force
RUN Install-Module ZeroTrustAssessment -Force
