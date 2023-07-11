<h1 style="text-align: center;">Jenkins</h1>
### Contents
* First job set up
* Sparta app set up
* Webhook creation

### First Job Set Up
1. 'New item' on dashboard
![](https://i.imgur.com/NoRfGn9.png)
2. Name your job and select Freestyle Project
![](https://i.imgur.com/sJJ0WhH.png)
3. In Build select 'Execute Shell' from the 'Add build step' menu, enter and save
![](https://i.imgur.com/3zGK9hA.png)
4. 'Build now' option on project dashboard
![](https://i.imgur.com/At8AsgM.png)
5. When it is Built can see project Build History
6. Check Console Output to see if run correctly

### Sparta app set up
1. New Item
2. Put HTTPS repository code into Github project url
![](https://i.imgur.com/yLHeQf5.png)
3. Put SSH repository code into Source code management -> Git -> Respository URL
4. Add credentials and copy in entire private key contents
5. Specify branch as main (Used to be master in older versions)
![](https://i.imgur.com/ZuYuAIe.png)
6. Build environment provide node to path
![](![](https://i.imgur.com/pdaY98T.png)
7. Build -> shell execution -> cd into app folder, npm install, npm test
![](https://i.imgur.com/Kx09Blc.png)
8. Office 365 connector -> Restrict where this project can be run -> sparta-ubuntu-node (remove space at end to clear error)
![](https://i.imgur.com/maLWMs6.png)


### Webhook
1. Go to your GitHub repository and click on ‘Settings’.
2. Click on Webhooks and then click on ‘Add webhook’.
3. In the ‘Payload URL’ field, paste your Jenkins environment URL. At the end of this URL add /github-webhook/. In the ‘Content type’ select: ‘application/json’ and leave the ‘Secret’ field empty.
4. In the page ‘Which events would you like to trigger this webhook?’ choose ‘Let me select individual events.’ Then, check ‘Pull Requests’ and ‘Pushes’. At the end of this option, make sure that the ‘Active’ option is checked and click on ‘Add webhook’.
![](https://i.imgur.com/Xh1AFmu.png)
5. In Jenkins, Click on the ‘Source Code Management’ tab.
6. Click on Git and paste your GitHub repository URL in the ‘Repository URL’ field.
7. Click on the ‘Build Triggers’ tab and then on the ‘GitHub hook trigger for GITScm polling’. Or, choose the trigger of your choice.
![](https://i.imgur.com/J8DqJb2.png)
