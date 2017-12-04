# jQuery-FlashingNotifications
Success and error notifications with good UX design and simple code

![gif](https://github.com/maciejsaw/jQuery-FlashingNotifications/raw/master/readme-files/flashing.gif)

# Features
- Animations with CSS transitions
- Custom text, links and HTML inside messages
- Responsive, universal design
- Supports long multiline messages
- Prevents users from seeing multiple errors at once
- Easy to add your custom styles because CSS is nice & clean, based on BEM
- Design tested with usability research on real products

# Quick start
1. Open this Codepen https://codepen.io/maciejsawicki/pen/EbMmpK 
2. Copy HTML to your HTML. Ideally at the top of ```body```
3. Copy CSS to your CSS styles (no need to copy images, as they are encoded with SVG in the code)
4. Copy JS to your JS scripts

To check if it works, try typing in the console ```FlashingNotifiactions.showAndHideNotification('success', "It works!",)```. If everything is fine you should see the green notification.

# Specification

## showAndHideNotification
Shows the notification and hides it. 
Because of UX design decision, the notifications of specific type will not stack. This prevents users from being bombarded by errors. Only tha last received message of specific type will be shown. If a message is received while a different message of this type was shown, the old message will be hidden and then the new message will be shown.
```FlashingNotifiactions.showAndHideNotification(notificationType, notificationText, timeToWaitBeforeHiding)```

#### notificationType
It changes the type of notification, so changes its color and icon. Note that the success type won't have the close button, because user shouldn't be bothered with it and it's not essential for him to acknowledge that he read the message.
Available options: ```'neutral'```, ```'success'```, ```'error'```
Default: ```'neutral'```

#### notificationText
It changes the text inside notification.
It support HTML, so you can place links inside and whatever your want.
Default: depends on notification type: ```'Notification!'```, ```'Success!'```, ```'Oops... Something went wrong.'```

#### timeToWaitBeforeHiding
It changes the delay before the notification is hidden. 
There's no separate option to make the message persistent, you need to enter a big number here to make sure that user will read this message and when he does he can close it with the button. 
Default: ```'3500'```

For example, to show green success message that shows "Message sent!" and hides after 8 seconds, you need to use this code
```FlashingNotifiactions.showAndHideNotification('success', "Message sent!", 8000)```

## hideNotification
Hides selected notification type
```FlashingNotifiactions.hideNotification(notificationType)```

## hideAllNotifications
Hides all notifications
```FlashingNotifiactions.hideAllNotifications()```

# FAQ
#### How can I add my own style?
Just modify the CSS that you copied from this Codepen https://codepen.io/maciejsawicki/pen/EbMmpK as described in the "Quick start" section
#### How can I change position of the message?
You can't, because the position on top is for most cases the right design decision. This is the most generic placement that works on all screen sizes and proved to work well on usability tests.

# Dependencies
- It requires jQuery or Zepto 
- The code is super simple and it uses only basic jQuery functions so it should be very easy for you to rewrite it to work with any JS framework like React, Vue.js, Angular etc. 
