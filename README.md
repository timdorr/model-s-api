Need a Tesla to develop with? Use [my referral link](http://ts.la/timothy8449) to get a $1000 discount and unlimited Supercharging.

# Tesla JSON API

[View Documentation](http://docs.timdorr.apiary.io/)

This is unofficial documentation of the Tesla JSON API used by the iOS and Android apps.
The API provides functionality to monitor and control the Model S (and future Tesla vehicles) remotely.
The project provides both documention of the API and  Ruby library  for accessing it.

> If any folks at Tesla are reading this, I'd love to help coordinate a developer program for your APIs. If there's any way I can be helpful, please feel free to get in contact. Also, I'd love to be in the beta firmware program :wink:

## Ruby Gem [![Gem Version](https://img.shields.io/gem/v/tesla_api.svg)](http://rubygems.org/gems/tesla_api) [![Build Status](https://img.shields.io/travis/timdorr/model-s-api/master.svg)](https://travis-ci.org/timdorr/model-s-api) [![Coverage Status](https://img.shields.io/coveralls/timdorr/model-s-api.svg)](https://coveralls.io/r/timdorr/model-s-api?branch=master)

This gem provides a basic wrapper around the API to easily query and command the car remotely. 
It also provides access to the streaming API and a means to process data coming from it.

## Installation

Add this line to your application's Gemfile:
```ruby
gem 'tesla_api'
```

Or install it yourself:
```sh
gem install tesla_api
```

## Usage

Here's a quick example:

```ruby
require 'tesla_api'

tesla_api = TeslaApi::Client.new(email, client_id, client_secret)
tesla_api.login!(password) # Or tesla_api.token = token if you have an existing token.
model_s = tesla_api.vehicles.first # => <TeslaApi::Vehicle>

model_s.wake_up
model_s.auto_conditioning_start unless model_s.climate_state["is_auto_conditioning_on"]

model_s.set_charge_limit(90)
model_s.charge_start

charge_state = model_s.charge_state
puts "Your Model S is #{charge_state["charging_state"]} " +
     "with a SOC of #{charge_state["battery_level"]}% " + 
     "and an estimate range of #{charge_state["est_battery_range"]} miles"
```

## Copyright

Ruby portions are Copyright (c) 2014 Tim Dorr. Released under the terms of the
MIT license. See LICENSE for details.
