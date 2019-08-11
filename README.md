# Calendly Ruby Gem

* Version: 1.1.0

This is a fork of @nurdymuny's `calendly` gem:

https://github.com/nurdymuny/calendly-ruby

I have added support for a new API method (list webhooks), cleaned up the README, added a project URL to the gemsepc, etc. - @sbraford

## Installation

add to Gemfile

```
gem 'calendly', git: 'git@github.com:nurdymuny/calendly-ruby.git'
```

Or to get the version taht includes the updates

```
gem 'calendly', git: 'git@github.com:sbraford/calendly-ruby.git'
```


run `bundle install`

set token on config initializers/calendly.rb
http://developer.calendly.com/v1/docs/getting-your-authentication-token

configure calendly

```
Calendly.configure do |config|
  config.token = "YOUR-TOKEN-HERE"
end
```

## Usage
--------------

Calendly API docs:

http://developer.calendly.com

### Test Authentication Token

http://developer.calendly.com/docs/test-authentication-token

See if you can connect:

```
Calendly.test_authentication
```
### Create a Webhook Subscription

http://developer.calendly.com/docs/webhook-subscriptions

Create the subscription, pass in the url and events you wish to subscribe it to

```
Calendly.webhook_subscription({url: 'url', events: ["invitee.created", "invitee.canceled"]})
```

Returns parsed JSON as a ruby Hash like:
```
{'id': 12345}
```

### List Webhook Subscriptions

https://developer.calendly.com/docs/get-list-of-webhook-subscriptions

List your subscriptions

```
Calendly.list_webhook_subscriptions
```

### Delete Webhook Subscription

http://developer.calendly.com/docs/delete-webhook-subscription

Delete a webhook subscription

```
Calendly.delete_webhook(hook_id)
```

### Sample Invitee

http://developer.calendly.com/docs/invitee-samples

Show sample invitee data

```
Calendly.sample_invitee
```

Could be useful for testing, etc.
