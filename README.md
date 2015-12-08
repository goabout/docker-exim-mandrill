Go About Mailer Docker image
============================

This is the Git repo of the Go About Docker image for a mailer that uses [Exim](http://www.exim.org/) for sending mail through [Mandrill](https://mandrillapp.com/).

## Usage

    docker run -e domain=DOMAIN -e mandrill_username=USERNAME -e mandrill_api_key=API_KEY goabout/exim-mandrill