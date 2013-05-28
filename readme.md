#### Sauce Storage

See the [API docs](http://saucelabs.com/docs/rest#storage).

Create a storage object by providing username, key, and optionally debug.

```ruby
s = SauceStorage.new username: 'my_user_name', key: '00', debug: true
```

If SAUCE_USERNAME and SAUCE_ACCESS_KEY are defined as environment variables, username and key may be omitted.

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