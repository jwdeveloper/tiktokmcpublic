## Getting started

#### How to connect?

When you found a person want to connect to use Command `tiktok connect`,
there are a few possible way of connecting

- `/tiktok connect https://www.tiktok.com/@bangbetmenygy/live`
- `/tiktok connect @bangbetmenygy`
- `/tiktok connect bangbetmenygy`

#### Why I'm getting connection errors?

- `It is not possible connecting to Private live`
- `It is not possible connecting to +18 live`
- `It is not possible connecting if your server has China/Russian/Ukrainian IP`
- `It is not possible connecting if you are under connection limit`



## Skript

Ok now you are connected but how to adjust this plugin?
First of all you need to learn a bit `Skript`. It is a 
plugin that allows you to create scripts for spigot.

You can find all the TikTok related scripts at the path

`.../plugins/Skript/scripts/tiktok`

Just modify or edit them as you want. Where you are done
reload the script you were working on with the command 

`/skript reload (skript name)`

Now I will tell you more about scripting 

## Gifts

Gift event pattern: `on [%number_of_gifts%] gift[s] [%gift-name%]`

The most basic way of handling gifts is to do `on gift`
it is just triggered when any gift is sent

```
on gift:
 set {_gift} to event.gift.name #Getting gift name
 set {_user} to event.user.name #Getting user name
  
 #Sending message to player with embeded gift and user name
 send  "A gift %{_gift}%  was send by user %{_user}%!" to the player
```

<br>

However, you more likely want to define at what kind of gift
event should be trigged. To do so we can place the gift `name` after
`gift`. This will be invoked when someone send to us `rose`

```
on gift rose:
 set {_gift} to event.gift.name #Getting gift name
 set {_user} to event.user.name #Getting user name
  
 #Sending message to player with embeded gift and user name
 send  "A gift %{_gift}%  was send by user %{_user}%!" to the player
```

<br>

The previous example was nice, but probably you also want to define
at what amount of gifts event should be triggered.
Let's say we want event that triggers when user send us `5 roses`.
We can do it like that

``` 
on 5 gift rose:
 set {_gift} to event.gift.name #Getting gift name
 set {_user} to event.user.name #Getting user name
  
 #Sending message to player with embeded gift and user name
 send  "A gift %{_gift}%  was send by user %{_user}%!" to the player
```

or using plural word `gifts` instead of `gift`. It is only made for estetic

``` 
on 5 gifts rose:
 set {_gift} to event.gift.name #Getting gift name
 set {_user} to event.user.name #Getting user name
  
 #Sending message to player with embeded gift and user name
 send  "A gift %{_gift}%  was send by user %{_user}%!" to the player
```

<br>

That's it when it comes to gifts I hope you didn't get confused!

## Events

Event pattern: `on tiktok %event-name%`

There more events than just gifts. You might
use them to control your mini-game or make it more fun!

### on tiktok comment


```
on tiktok comment:
 #possible properties
 
  set {followers} to event_mentionedUser_followers #number
  set {following} to event_mentionedUser_following #number
  set {id} to event_mentionedUser_id #number
  set {name} to event_mentionedUser_name #text
  set {link} to event_mentionedUser_picture_link #text
  set {profileName} to event_mentionedUser_profileName #text
  set {messageId} to event_messageId #number
  set {roomId} to event_roomId #number
  set {text} to event_text #text
  set {timeStamp} to event_timeStamp #number
  set {userLanguage} to event_userLanguage #text
  set {followers} to event_user_followers #number
  set {following} to event_user_following #number
  set {id} to event_user_id #number
  set {name} to event_user_name #text
  set {link} to event_user_picture_link #text
  set {profileName} to event_user_profileName #text
  set {visibleToSender} to event_visibleToSender #true/false

  send  "on tiktok comment event has been invoked!" to the player
```
### on tiktok connected


```
on tiktok connected:
 #possible properties
 

  send  "on tiktok connected event has been invoked!" to the player
```
### on tiktok disconnected


```
on tiktok disconnected:
 #possible properties
 
  set {reason} to event_reason #text

  send  "on tiktok disconnected event has been invoked!" to the player
```
### on tiktok error


```
on tiktok error:
 #possible properties
 
  set {cause} to event_exception_cause #Throwable
  set {depth} to event_exception_depth #number
  set {detailMessage} to event_exception_detailMessage #text

  send  "on tiktok error event has been invoked!" to the player
```
### on tiktok follow


```
on tiktok follow:
 #possible properties
 
  set {messageId} to event_messageId #number
  set {roomId} to event_roomId #number
  set {timeStamp} to event_timeStamp #number
  set {totalFollowers} to event_totalFollowers #number
  set {followers} to event_user_followers #number
  set {following} to event_user_following #number
  set {id} to event_user_id #number
  set {name} to event_user_name #text
  set {link} to event_user_picture_link #text
  set {profileName} to event_user_profileName #text

  send  "on tiktok follow event has been invoked!" to the player
```
### on tiktok gift


```
on tiktok gift:
 #possible properties
 
  set {combo} to event_combo #number
  set {diamondCost} to event_gift_diamondCost #number
  set {id} to event_gift_id #number
  set {name} to event_gift_name #text
  set {link} to event_gift_picture_link #text
  set {messageId} to event_messageId #number
  set {roomId} to event_roomId #number
  set {timeStamp} to event_timeStamp #number
  set {followers} to event_toUser_followers #number
  set {following} to event_toUser_following #number
  set {id} to event_toUser_id #number
  set {name} to event_toUser_name #text
  set {link} to event_toUser_picture_link #text
  set {profileName} to event_toUser_profileName #text
  set {followers} to event_user_followers #number
  set {following} to event_user_following #number
  set {id} to event_user_id #number
  set {name} to event_user_name #text
  set {link} to event_user_picture_link #text
  set {profileName} to event_user_profileName #text

  send  "on tiktok gift event has been invoked!" to the player
```
### on tiktok join


```
on tiktok join:
 #possible properties
 
  set {messageId} to event_messageId #number
  set {roomId} to event_roomId #number
  set {timeStamp} to event_timeStamp #number
  set {totalUsers} to event_totalUsers #number
  set {followers} to event_user_followers #number
  set {following} to event_user_following #number
  set {id} to event_user_id #number
  set {name} to event_user_name #text
  set {link} to event_user_picture_link #text
  set {profileName} to event_user_profileName #text

  send  "on tiktok join event has been invoked!" to the player
```
### on tiktok like


```
on tiktok like:
 #possible properties
 
  set {likes} to event_likes #number
  set {messageId} to event_messageId #number
  set {roomId} to event_roomId #number
  set {timeStamp} to event_timeStamp #number
  set {totalLikes} to event_totalLikes #number
  set {followers} to event_user_followers #number
  set {following} to event_user_following #number
  set {id} to event_user_id #number
  set {name} to event_user_name #text
  set {link} to event_user_picture_link #text
  set {profileName} to event_user_profileName #text

  send  "on tiktok like event has been invoked!" to the player
```
### on tiktok reconnecting


```
on tiktok reconnecting:
 #possible properties
 

  send  "on tiktok reconnecting event has been invoked!" to the player
```
### on tiktok subscribe


```
on tiktok subscribe:
 #possible properties
 
  set {messageId} to event_messageId #number
  set {roomId} to event_roomId #number
  set {timeStamp} to event_timeStamp #number
  set {followers} to event_user_followers #number
  set {following} to event_user_following #number
  set {id} to event_user_id #number
  set {name} to event_user_name #text
  set {link} to event_user_picture_link #text
  set {profileName} to event_user_profileName #text

  send  "on tiktok subscribe event has been invoked!" to the player
```