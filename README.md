# Unisender::Rails

It is a wrapper to use uni_sender gem

## Installation

Add this line to your application's Gemfile:

    gem 'unisender-rails'

And then execute:

    $ bundle install

Or install it yourself as:

    $ gem install unisender-rails

## Usage

Make a mailer:

    rails g unisender_rails:mailer my_mailer
    or 
    rails generate unisender_rails:mailer my_mailer

Make defaults in your mailer:

    class MyMailer < ActionMailer::Base
      default :from => "your@email.com"
      self.unisender_settings = {:api_key => 'your api here',
                                 :list_id => your users group list id }
      def sign_up
  	    mail(:to => 'your@client.com',
             :subject => 'Subject')
      end
    end

Use the mailer:

    MyMailer.sign_up.deliver!

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
