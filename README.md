# Webhook exploration
This repositor explores API communication with webhooks and http requests, starting with and introduction using Git's webhook and Ruby.

Configure local server to listen to webhooks. The server can then be process the pushed information for other purposes. For example, setting up a "real" web application by logging JSON output to a database.

Presetup:

In the Settings of the your own target repository you want to trigger, add a webhook and make it active.

Download, extract, and run ngrok to expose localhost port to the internet https://ngrok.com/download. The ngrok.exe command should look like ```ngrok http 4567 ```

First install Ruby. Then, run the Command Prompt with Ruby and install the sinatra gem.

Setup:
Create a ruby script by copying the following code and save as ruby_sinatra_test_server.rb into the same directory your prompt is currently in. (Alternatively you can clone ruby_sinatra_test_server.rb from this repository.)
```ruby
require 'sinatra'
require 'json'

post '/payload' do
  push = JSON.parse(request.body.read)
  puts "I got some JSON: #{push.inspect}"
end
```

In a ruby command prompt, run ```ruby ruby_sinatra_test_server.rb``` to start the "server" and leave the terminal running.

Create an issue for your repository and submit. 

Your ruby server terminal will output a message stream like:
```
~/Developer/platform-samples/hooks/ruby/configuring-your-server $ ruby server.rb
== Sinatra/1.4.4 has taken the stage on 4567 for development with backup from Thin
>> Thin web server (v1.5.1 codename Straight Razor)
>> Maximum connections set to 1024
>> Listening on localhost:4567, CTRL+C to stop
I got some JSON: {"action"=>"opened", "issue"=>{"url"=>"...```

You're ready to move onto better things like [securing your webooks] (https://developer.github.com/webhooks/securing/)!
