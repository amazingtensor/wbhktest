# webhook
Exploration into Twitter API, using Git's webhook and Ruby.

Configure local server to listen to webhooks. The server can then be process the pushed information for other purposes. For example, setting up a "real" web application by logging JSON output to a database.

Presetup:

In the Settings of the target repository you want to trigger, add a webhook and make it active.

Download, extract, and run ngrok to expose localhost port to the internet https://ngrok.com/download. The ngrok.exe command should look like ```ngrok http 4567 ```

First install Ruby. Then, run the Command Prompt with Ruby and install the sinatra gem.

Setup:
Create a ruby script by copying the following code and save as ruby_sinatra_test.rb into the same directory your prompt is currently in.
```ruby
require 'sinatra'
require 'json'

post '/payload' do
  push = JSON.parse(request.body.read)
  puts "I got some JSON: #{push.inspect}"
end
```

Run ruby ruby_sinatra_test.rb

Create an issue
