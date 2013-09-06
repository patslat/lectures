#Delayed Job

##About
Delayed Job is a useful gem for pushing your application's slower tasks into the
background. It creates a table in your database that acts as a TODO list of tasks. 
Doing this allows your server to process work asynchronously, so
that your responses are not unnecessarily delayed. 

##Installation
Since we're using active record you're going to want to install that
version of DJ. `gem 'delayed_job_active_record'` and bundle install.  

```bash
rails generate delayed_job:active_record
rake db:migrate
```

##Use
Delayed Job provides a delay method that you can use to
queue work to be run in the background of your application:

`@photo.delay.upload`

This will create an entry into the delayed_jobs table with instructions
to call #upload on the specified Photo.

If you have methods that are always meant to be processed asynchronously
you can specify this desire in your model with `handle_asynchronously`

```ruby
class CatCircle
    def flip_hats
        1_000_000_000.times do { flip_hat }
        save
    end
    handle_asynchronously :flip_hats
end
```
`handle_asynchronously` can take a few options to specify priorty
(represented by an int value) or a time proc

```ruby
handle_asynchronously :daily_reminder, run_at => Proc.new { 1.day.from_now }

#...
handle_asynchronously :of_utmost_urgency, priority => 9001
```

