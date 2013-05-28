#### Sauce Storage

See the [API docs](http://saucelabs.com/docs/rest#storage).

Create a storage object by providing username, key, and optionally debug.

```ruby
s = SauceStorage.new username: 'my_user_name', key: '00000000-0000-0000-0000-000000000000', debug: true
```

If `SAUCE_USERNAME` and `SAUCE_ACCESS_KEY` are defined as environment variables, username and key may be omitted.

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

--

Jenkins example.

```bash
export SAUCE_USERNAME="username"
export SAUCE_ACCESS_KEY="00000000-0000-0000-0000-000000000000"

# upload.rb is a file you create that uploads your apk
ruby upload.rb

export APP_NAME="Android Appium Jenkins"
export APP_PACKAGE="com.my.Pkg"
export APP_ACTIVITY="startAct"
export APP_WAIT_ACTIVITY="splashAct"
export SAUCE_PATH="sauce-storage:my.apk"

# run.rb is a file you create to run your tests.
ruby run.rb
```

Sample upload.rb

```ruby
require File.expand_path '../sauce_storage', __FILE__

s = SauceStorage.new debug: true
apk = File.expand_path '../' * 1 + 'my.apk', __FILE__

s.upload apk
```

Sample run.rb

 - [See ruby_lib_android's run.rb](https://github.com/appium/ruby_lib_android/blob/master/lib/run.rb)
