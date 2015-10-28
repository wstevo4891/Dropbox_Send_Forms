# Dropbox_Send_Forms
A rails app that uses dropbox-sdk and wicked_pdf to upload pdfs of forms to a dropbox account

#Installation

1. git clone https://github.com/wstevo4891/Dropbox_Send_Forms.git

2. Run bundle install

3. rake db:migrate

4. Start a rails server and go to localhost to see the home page

#Getting Started

Before you can use this app, you need to have a Dropbox account and create an app for receiving files

Step 1. You need a Dropbox account.

Step 2. Got one? Good, now go to https://www.dropbox.com/developers

Step 3. Click on "Create your app", choose "Dropbox API", "App Folder", name your app, and click "Create app" at the bottom.

Step 4. On the next screen, you will see "App key" and "App secret" under the row with your app's name. You need to
        copy these and paste them onto the appropriate lines in config/initializers/dropbox_config.rb

Step 5. There's another secret key you need to copy. Below the "App key/App secret" row, you will see the "OAuth2" row.
        At the bottom is "Generated Access token" and a button that says "Generate." Click the button and copy the generated
        access token. Paste that token between the quotes on the OAUTH2_ACCESS_TOKEN line in dropbox_config.rb

Step 6.
