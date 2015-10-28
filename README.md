# Dropbox_Send_Forms
A rails app that uses 'dropbox-sdk', 'wicked_pdf', and 'wkhtmltopdf' to upload pdfs of forms to a dropbox account.

I had a client who wanted a website integrated with Dropbox so that when a user completed an application form
the form would be uploaded to the client's Dropbox account. I thought that pdf files would be the best medium
for uploading so I used the 'wicked_pdf' and 'wkhtmltopdf' gems to first make pdf copies of the forms and then
send them to a folder in the client's Dropbox account. All of this happens once the user clicks the submit button.

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

Step 6. Almost there! There's one last thing to do. Go to app/controllers/documents_controller.rb. There are three lines in this controller that need editing. They're in the edit, create, and update methods. The lines begin with 'wkhtmltopdf' and you need to type in the path to that gem in your app. The path looks like: /Users/your_user_name/.rvm/gems/ruby-2.2.2/bin/wkhtmltopdf
Well, this is what it looks like on my app, using a Macbook, rvm for my ruby installation, and ruby version 2.2.2. Your path could be different.

Once you have the right path for wkhtmltopdf you're all set! Go to the app's home page, create a user account, and complete the form. You should see that a pdf of the form has been uploaded to the Dropbox app you just created. There is also a "pdfs" folder in the root directory that will receive the form pdfs. First they go there, then they are uploaded to Dropbox.

#Extra Info

There are a LOT of options you can put on the pdf files from the documents controller. I would recommend taking a look at the 'wicked_pdf' gem here: https://github.com/mileszs/wicked_pdf
The README covers the options, how to put them in the controller, and has a link to the 'wkhtmltopdf' gem for more information on that. Compare the examples given for 'wicked_pdf' and what I did in the documents controller, and you should get a good idea of how it all works.
