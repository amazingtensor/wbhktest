# webhook
Exploration into Twitter API, using Git's webhook and Ruby.

Configure local server to listen to webhooks. The server can then be process the pushed information for other purposes. For example, setting up a "real" web application by logging JSON output to a database.

Presetup: Signup for a Twitter API.

First install Ruby. Then, run the Command Prompt with Ruby and install the sinatra gem.

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
