# App Notify Send/Receive Event Demo

Following the below, you'll get **two new apps** loaded into your Zendesk instance.

The first app **sends** a notification event, along with some data, to another app. 

The second app **receives** the event and its data and displays it.

These apps are a demonstration of the notification feature/endpoint used within Zendesk apps.

## Getting started

Follow these steps to get a local copy up and running.

### Prerequisites

- Zendesk Command Line (ZCLI)

[Using Zendesk Command Line](https://developer.zendesk.com/documentation/apps/app-developer-guide/zcli/#installing-and-updating-zcli)

### Installation

**Clone the repo**

```
git clone https://github.com/example.git
```

**Run the apps**

Create the 'Receive' app first:

1. `cd receive_notifications` 
2. Run `zcli apps:create` and enter your admin and test instance information
3. Write down the app_id value displayed in the terminal

Create the 'Send' app:  

4. `cd send_notifications`
5. Edit assets/iframe.html and change the following of values...
6. In `sendNotification()`, enter the Receive Notification `app_id` that you took down earlier.
7. Either enter a valid `agent_id` or remove `agent_id` (don't forget to remove the preceding comma from the JSON object if you remove `agent_id`)
8. `zcli apps:create`

Do a refresh of your Apps and click the Send app's 'send' button. You should see the current date and time show up in the Receive app's display.

# Reference
* https://developer.zendesk.com/rest_api/docs/core/apps#send-notification-to-app  
* https://developer.zendesk.com/apps/docs/apps-v2/api_reference#client.onname-handler-context
