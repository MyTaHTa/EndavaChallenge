# Endavachallenge

This is a simple implementation of Bitwarden_rs server API on Azure Cloud (containerized web app + database running on linux)

https://dev.azure.com/EndavaDevOps//bitwardenrs/_home - DevOps Project HomePage

https://portal.azure.com/#@mtzvetkovawsgmail.onmicrosoft.com/resource/subscriptions/5007edd0-4dd4-4f11-ae02-8bec017df56c/resourceGroups/bitwardenrs-rg/overview - Azure Portal HomePage
The example implements https://github.com/dani-garcia/bitwarden_rs

It can be tested with all apps from the official version https://bitwarden.com/#download

What is happening there in short
1. A linux agent will download Docker and a template for Azure Conteiner registry.
2. Once you have the Conteiner registry deployed in Azure the Docker will start building an Image.
3. The Image is pushed to the container.
4. Now you can Release your Linux Web App so choose a web plan and try it.
5. Get a Azure backup plan + Availability test and get the APP running on SSL from the switch menu.

In the long version you may also want:
1. Get a linux VM up and running with latest updates on ''Ubuntu'' (maybe)
2. Install Docker + Docker compose
3. Pull something from https://github.com/dani-garcia/bitwarden_rs or build your own (docker pull bitwardenrs/server:latest)
4. A storage account on Azure for the backup plan of the VM.
5. Buy a domain/or create a subdomain if you already have one.
6. Go and get some A/AAA records pointing to your server/proxy IP address. (IPv4 or IPv6).
7. IF you dont want to spend money on SSL certificate get a cert bot and make a cron job to generate free SSL certificate every 2 months.
8. Disable the http port (80) and get the app running over https (433) you already have an SSL :)  When using a proxy, it's preferrable to configure HTTPS at the proxy level and not at the application level, this way the WebSockets (3012) connection is also secured.
9. Now go and change the SSH port to something like this (12445234312312356, yes you can't do it) but pls not 22
10. Now install ufw and allow your port if you want to have SSH connection (maybe it will need some maintenance from time to time) close every other port that you dont need just to be sure that the Russians are not upon you...
11. OR if you dont change the SSH portand  you dont want some random Chinees bots digging day and night for your password = Fail2Ban...

This is getting seriously long, sorry, but someone may need it :)
