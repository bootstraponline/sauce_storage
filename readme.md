#### Sauce Storage

See the [API docs](http://saucelabs.com/docs/rest#storage).

```ruby
s = SauceStorage.new username: 'my_user_name', key: '00', debug: true
```

Or if you have SAUCE_USERNAME and SAUCE_ACCESS_KEY in ENV vars.

```ruby
s = SauceStorage.new debug: true
```

List all files.

```ruby
s.files
```
 
Upload a file.

```ruby
s.upload '/tmp/sauce/test.zip'
```