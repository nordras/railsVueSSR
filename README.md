# Rails Vue server side rendenring

This project wase made based on web tutorials for personal studies, it' free

Att
Igor (Nordras)

```
git init
git clone git@github.com:nordras/railsVueSSR.git
bundle
```

[Do the devise installation](#devise)  

```
rails generate devise:install
rails generate devise User
rake db:migrate
rails generate devise:views -v sessions
```

```
rails webpacker:instal
rails webpacker:install:vue
rails vue:setup

rails s
```

---

#### Devise install instructions <a name="devise"></a>

After bundle install (with devise gem), if you haven't yet you must do some manually setup:

  1. Ensure you have defined default url options in your environments files. Here
     is an example of default_url_options appropriate for a development environment
     in config/environments/development.rb:
     ```
       config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }
     ```
     In production, :host should be set to the actual host of your application.

  2. Ensure you have defined root_url to *something* in your config/routes.rb.
     For example:

       root to: "home#index"

  3. Ensure you have flash messages in app/views/layouts/application.html.erb.
     For example:
     ```
       <p class="notice"><%= notice %></p>
       <p class="alert"><%= alert %></p>
     ```
  4. You can copy Devise views (for customization) to your app by running:
    ```
    rails g devise:views
    ``` 
---
