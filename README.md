##Drone plugin for notification on Microsoft Teams

Sample drone.yml content for notification  
```yaml
  notify:
    image: diyfr/drone_plugin_teams
    secrets : [teams_webhook]
    content:
      title: "New Version published"
      text: "A new version of Sample project  was published"
      themeColor: "EA4300"
    when:
      branch: master
```
Required : 
teams_webhook :  webhook url   (Get it ! : Channel option, Connectors, add and select Incoming Webhook)  
text : Message content  

If you doesn't want using Secret you can specify webhook url directly :

```yaml
  notify:
    image: diyfr/drone_plugin_teams
    webhook: "https://outlook.office.com/webhook/125565465445......"
    content:
      title: "New Version published"
      text: "A new version of Sample project  was published"
      themeColor: "EA4300"
    when:
      branch: master
```
You can add environemnt value in message :
```yaml
      text: "A new version of Sample project  was published commit message : ${CI_COMMIT_MESSAGE}"
```
