# Influencer backend

This app is ready to deploy to Heroku [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/sethherr/grape-doorkeeper)


## Set up

First `bundle install` and `rake db:setup`

Run `rake start` to get the server running locally. It runs at [http://localhost:3001](http://localhost:3001)

You will want to change [config/initializers/secret_token.rb](config/initializers/secret_token.rb) and export `DEVISE_SECRET_KEY` (see config/initializers/devise.rb).

You will also probably want to delete the [imaginary item](app/models/imaginary_item.rb) class and [serializer](app/serializers/item_serializer.rb), which are included for demonstration in [the me/items endpoint](app/controllers/api/v1/me.rb#L24-L33).

This app includes [omniauth-bike-index](https://github.com/bikeindex/omniauth-bike-index). For Bike Index login to work, export environment variables `BIKEINDEX_APP_ID` and `BIKEINDEX_APP_SECRET`. You'll need a Bike Index app, which you can create at [BikeIndex.org/oauth/applications/new](https://BikeIndex.org/oauth/applications/new).

*Bike Index uses a similar grape, Swagger, doorkeeper setup&mdash;this is an example of [creating an OmniAuth strategy for doorkeeper](https://github.com/doorkeeper-gem/doorkeeper/wiki/Create-a-OmniAuth-strategy-for-your-provider)*.

## Testing

Rspec and guard - run `bundle exec guard` to watch your spec files for changes and rerun tests for those files.

There is a spec for the `api/v1/me` API route and for the swagger docs to help get you started.
