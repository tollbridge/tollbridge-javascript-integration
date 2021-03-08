# Tollbridge JavaScript Integration

[Tollbridge](https://tollbridge.co) is a user-authentication, subscription and paywall software as a service. This documentation will help you to implement Tollbridge's JavaScript based authentication in your application in just a few minutes.


## Head

Visit the **Integration** section of your Tollbridge admin account and copy the *Head* section and add into the `<head>` of your webpage.

```text
<meta name="tollbridge" content="1,2,3">
```


## Body

Visit the **Integration** section of your Tollbridge admin account and copy the *Body* just below the `<body>` of your webpage.

```text
<script type="text/javascript" src="https://xxxx.tollbridge.co/js/tollbridge.js"></script>
<tollbridge-config
    app-id="xxxx.tollbridge.co"
    client-id="XXXX-XXXX-XXXX-XXXX-XXXX"
    callback-url="https://www.example.com/callback">
</tollbridge-config>
```

## Callback

Visit the **Integration** section of your Tollbridge admin account and copy the *Callback HTML* to a separate page on your website. This will be the page that you point your `callback-url` to in your settings config.

```text
<html>
<head>
    <title>Authenticating...</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes" />
    <meta name="robots" content="noindex">
    <style type="text/css">html{background:#eee;height:100%}body{text-align:center;display:-webkit-flex;display:flex;height:100%;-webkit-flex-flow:column wrap;flex-flow:column wrap;-webkit-justify-content:center;justify-content:center;margin:0;padding:10px}.loading{font-size:50px;height:1em;-webkit-animation:fadeout .5s 60s;animation:fadeout .5s 60s;-webkit-animation-fill-mode:forwards;animation-fill-mode:forwards}.loading span{-webkit-animation:fadein .5s .5s alternate infinite;animation:fadein .5s .5s alternate infinite}.loading span:nth-child(2){-webkit-animation-delay:.75s;animation-delay:.75s}.loading span:nth-child(3){-webkit-animation-delay:1s;animation-delay:1s}p,h2{text-align:center;font-family:helvetica;opacity:0;-webkit-animation:fadein .5s 3s;animation:fadein .5s 3s;-webkit-animation-fill-mode:forwards;animation-fill-mode:forwards}p{font-size:smaller;word-break:break-word;-webkit-animation-delay:5s;animation-delay:5s}.overflow{background:#000;color:#fff;max-width:100%;text-align:left}@-webkit-keyframes fadein{from{opacity:0;-webkit-transform:scale(.2)}to{opacity:1;-webkit-transform:scale(1)}}@-webkit-keyframes fadeout{to{opacity:0;height:0}}@keyframes  fadein{from{opacity:0;transform:scale(.2)}to{opacity:1;transform:scale(1)}}@keyframes  fadeout{to{opacity:0;height:0}}</style>
</head>
<body>
    <script type="text/javascript" src="https://xxxx.tollbridge.co/js/tollbridge.js"></script>
    <tollbridge-config
        app-id="xxxx.tollbridge.co"
        client-id="XXXX-XXXX-XXXX-XXXX-XXXX"
        callback-url="https://www.example.com/callback">
    </tollbridge-config>
    <div class="loading"><span>•</span><span>•</span><span>•</span></div>
</body>
</html>
```

# Account Links

You can also override the default return URL by passing `?redirect=https://www.example.com` along with the URL's below.
If you have a custom domain set within Tollbridge, you can replace `xxxx.tollbridge.co` with your custom domain.

## Login

```text
<a href="https://xxxx.tollbridge.co/login">Login</a>
```

## Google Login

```text
<a href="https://xxxx.tollbridge.co/login/google">Google Login</a>
```

## Facebook Login

```text
<a href="https://xxxx.tollbridge.co/login/facebook">Facebook Login</a>
```

## LinkedIn Login

```text
<a href="https://xxxx.tollbridge.co/login/linkedin">LinkedIn Login</a>
```

## Register

```text
<a href="https://xxxx.tollbridge.co/register">Register</a>
```

## Subscribe

```text
<a href="https://xxxx.tollbridge.co/plans">Subscribe</a>
```

## Profile/MyAccount

```text
<a href="https://xxxx.tollbridge.co/profile">Profile</a>
```

## Logout

```text
<a href="https://xxxx.tollbridge.co/logout">Logout</a>
```

# JavaScript API

## Auth Check

`tollbridge.auth()` will return true or false if the user has an active auth session

## User

**Request**

```
tollbridge.api('me').then(function(json) {
    console.log(json);
}, function(e) {
    console.log(e.error.message);
});
```

**Response**

```
{
   "id" : "40fc0d79-7174-4d37-98f5-e4dfddf5caa9",
   "name" : "Jane Jones",
   "firstname" : "Jane",
   "lastname" : "Jones",
   "email" : "jane@example.com",
   "plan" : "2",
   "avatar" : "https:\/\/www.gravatar.com\/avatar\/000000000000000000000000?d=mp&f=y&s=200"
}
```
