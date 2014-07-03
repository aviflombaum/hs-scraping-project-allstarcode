---
  tags: scraping, nokogiri, kids
  languages: ruby
---

##FREE SCRAPE

We're going to use this as the starting point for your final project. Part of building a web application is learning how to break the whole down into it's much smaller and more manageable pieces. 
Getting the data is the first part.

So the very first step is to think about what kind of data you want to use in your app. Are you interested in a specific person's tweets? When you're tagged in a photo in facebook? Maybe when a certain friend checks in on foursquare? Maybe your favorite sports's stats on game nights? Make sure that the site you have keeps track of the time that something is posted. It will be hard to eventually automate all of this if there isn't a time of when things are posted.

Once you've made a decision, we're going to use Nokogiri to scrape. You'll need to remember to require both nokogiri and open-uri in your ruby file in order to make HTTP calls to a site's content.

The browser dev tools will be very useful for finding the CSS selectors to choose the data you want.

Pry is a really helpful gem for debugging. It allows you to drop directly into your code at a specific moment and see exactly what your objects are and what data your variables represent. Sometimes your code can act in unexpected ways and pry lets you dig and get to the bottom of it.

First we need to download Nokogiri to your computers. In terminal, enter `gem install nokogiri`. 

Before you use it, you have to have Pry installed on your computer. To download it, in terminal enter `gem install pry`. To use it, you'll need to `require 'pry'` at the top of `scraping.rb`. You'll then put `binding.pry` directly in the body of the method you'd like to inspect. 

```RUBY
def my_method
  binding.pry
  ##code that's acting weird
end
```
To execute this, you'll need to trigger the method that contains the `binding.pry`. You can do that by calling the method below your code and then you'd just run your ruby file `ruby file-name.rb` in terminal. You'll immediately get dropped into the environment of that method in terminal. From there, you can call other methods, variables, etc. and get a sense of what they truly are and do.

Once you have all your data, you'll want to start thinking about how you want to organize it. If you're getting tweets, maybe you want to create a hash with key-value pairs for the tweet body and tweet time. If you're getting the weather, you'd want to maybe create a hash for storing wind-speed, humidity, min-temp, and max-temp.

An example might look like this:
```RUBY
daily_weather = {
  :wind_speed => my_wind_speed_scraped_data,
  :humidity_index => humidity_scraped_data,
  :min_temp => min_temp_scraped_data,
  :max-temp => max_temp_scraped_data
}
```

Once you have an idea of how you want to collect your data, you'll want to actually build it into that datatype. You can go back and take a look at the scraping-kickstarter lab for a refresher on how we collected that data from kickstarter into a hash.