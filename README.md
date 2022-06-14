# Demo App Notify Send/Receive Event

This repo contains **two apps** which you will load into your Zendesk instance.

The first app **sends** a notification event, along with some data, to another app. 

The second app **receives** the event and its data and displays it.

These apps are a demonstration of the notification event/endpoint used within Zendesk apps.

## Getting started

Follow these steps to get a local copy up and running.

### Prerequisites

- Zendesk Command Line (ZCLI)

[Using Zendesk Command Line](https://developer.zendesk.com/documentation/apps/app-developer-guide/zcli/#installing-and-updating-zcli)

### Installation

**1. Clone the repo**

```
git clone https://github.com/example.git
```

**2. Install the apps**

Create the Receive app first:

* `cd receive_notifications` 
* Run `zcli apps:create` and enter your admin and test instance information
* Make note of the app_id value displayed in the terminal - you'll need it later

Create the Send app:  

* `cd send_notifications`
* Navigate to assets/iframe.html and edit the following values
* In `sendNotification()`, enter the Receive Notification `app_id` that you took down earlier
* Replace `YOURSUBDOMAIN` with your own subdomain associated with your Zendesk instance
* Either enter a valid `agent_id` or remove `agent_id` (don't forget to remove the preceding comma from the JSON object if you remove `agent_id`)
* `zcli apps:create`

Do a refresh of your Apps and click the Send app's 'send' button. You should see the current date and time show up in the Receive app's display.

### Run apps locally

To test either app individually in your local environment, use the following steps.

**Run Receive App**

1. Navigate to app directory

```
cd receive_notification
```

2. Run the app

```
zcli apps:server
```

**Run Send App**

1. Navigate to app directory

```
cd send_notification
```

2. Run the app

```
zcli apps:server
```

[Testing your Zendesk app locally](https://developer.zendesk.com/documentation/apps/app-developer-guide/zcli/#testing-your-zendesk-app-locally)

<!-- Links to relevant resources such as help center articles or dev docs -->

## Additional Resources

- [Send Notifications to App](https://developer.zendesk.com/rest_api/docs/core/apps#send-notification-to-app)
- [ZAF Client API](https://developer.zendesk.com/api-reference/apps/apps-core-api/client_api/)
- [Zendesk Apps Guide](https://developer.zendesk.com/documentation/apps/)
- [Apps Support API documentation](https://developer.zendesk.com/api-reference/apps/apps-support-api/introduction/)

<!-- Issue reporting with link to repo issues page -->

## Issues

You can [create an issue on Github](https://github.com/zendesk/example/issues/new),
reach out in our [Developer Community](https://support.zendesk.com/hc/en-us/community/topics),
or report the issue in the [Zendesk Developers Slack group](https://docs.google.com/forms/d/e/1FAIpQLScm_rDLWwzWnq6PpYWFOR_PwMaSBcaFft-1pYornQtBGAaiJA/viewform).
