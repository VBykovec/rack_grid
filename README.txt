Rack::Grid

  NOTE: Check out rack-gridfs, as it is better maintained (http://github.com/skinandbones/rack-gridfs)

  Rack::Grid is used to serve a GridFS file from rack.
  Especially useful combined with mongoid_grid or matic_grid

Installation

  # gem install rack_grid

Usage Example with Sinatra.

  # app.rb
  require 'rack_grid'
  configure do
    use Rack::Grid, {
      :host => 'localhost',    # MongoDB Hostname (default: localhost)
      :port => 27017,          # MongoDB Port (default: 27017)
      :username => 'user',     # Optional MongoDB Username
      :password => 'pass',     # Optional MongoDB Password
      :prefix => 'grid',       # URL Prefix (eg: /grid/xxxxxxx/file.ext)
      :cache_control => {
        :max_age => 300
      },                       # Cache Control setting
      :database => 'mydb'      # Required database name
    }
  end

  # view.erb
  <img src="/grid/4ba69fde8c8f369a6e000003/filename.jpg" alt="My Image" />


