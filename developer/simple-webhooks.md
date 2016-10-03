# Simple Webhooks

Webhooks are a new way to send messages to a channel. They can be used by anybody with the link and a method to create POST requests without authentication and provide new ways to format messages. Currently, the ability to create webhooks are only in Canary and this feature is in Alpha. Therefor, things may change.

### Step 1: The interface

You need either the Administrator or the Manage Webhooks permission to create a webhook. There are two places in which you can create them. The first is through the Server Settings menu.

![ExistingWebhooks](http://i.imgur.com/acgWRZ7.png)

As you can see, I have already created a couple of them.

**A.** This is where you go to manage the webhooks

**B.** This is what you click on to create a webhook

**C.** These are your already created webhooks

**D.** This is the profile picture of your webhook (it can be changed on the fly when you send the request)

**E.** This is the username of your webhook (it can be changed on the fly when you send the request)

**F.** This tells you what channel the webhook is for (webhooks only work on the channel they are assigned)

**G.** This is who created the webhook and at what point

**H.** This is where you click to edit the webhook

This is the view if you go into the channel settings and click Webhooks. It's similar, but only shows the webhooks for that channel.

![ChannelView](http://i.imgur.com/AU29AoK.png)

### Step 2: Creating a webhook

So now, we're going to create one. I'm going to go through the Server Settings menu. Clicking the Edit button will give you a similar screen to edit an existing one.

![CreateWebhook](http://i.imgur.com/cIBKfj2.png)

**A.** This is where you click to change the profile picture

**B.** This is the current information of the bot

**C.** These buttons are for Delete, Cancel, and Save. They should be self explanitory

**D.** This is where you change the username

**E.** This is a dropdown box to select the channel the webhook is set for. It will only send to this channel

**F.** The webhook url. You want to save this, as this is where you send the information to post the messages

Edit the information to your liking, then click **Save**.

### Step 3: Sending a POST request

For this guide, I am going to install Postman. It's a Chrome extension that allows you to easily send HTTP requests. If you already know how to send POST requests, you can simply read the steps.

> Link to Postman: https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=en

Once it's installed, it should look like this.

![NewPostman](http://i.imgur.com/AA0s1nU.png)

Now we need to configure it. It should look like this in the Body tab.

![SetupPostman](http://i.imgur.com/V3sJCip.png)

**A.** This should be set to POST

**B.** This is the URL of your webhook

**C.** This should be set to raw for raw input

**D.** This should be set to JSON

**E.** This is where we input the code

### Step 4: Compose a message

Right now, I'm going to give you some sample code on how to send a simple message.

```json
{
    "content": "Hello! I am a sample message of how to use a webhook."
}
```

Enter this in the field marked **E.** on the above drawing, and click Send. You should see a new message in your channel. This used the webhook's name and avatar that you chose.

![FirstWebhook](http://i.imgur.com/ShIz7KS.png)

But what if you want to change it up for just one message?

```json
{
    "username": "Webhook Guide",
    "avatar_url": "https://pixabay.com/static/uploads/photo/2014/04/03/10/11/exclamation-mark-310101_960_720.png",
    "content": "Oh look, my avatar and name have changed!"
}
```

![BetterWebhook](http://i.imgur.com/1kq4vYx.png)

Congratulations! You have sent a message as a webhook.

### Other information

You cannot set the username as Clyde.
You can use md notation (like Reddit). [Example text](https://thecrossroads.xyz/)
