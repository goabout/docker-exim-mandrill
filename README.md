Go About Mailer Docker image
============================

This is the Git repo of the Go About Docker image for a mailer that uses
[Exim](http://www.exim.org/) for sending mail through
[Mandrill](https://mandrillapp.com/).


## Usage

    docker run -e fallback_user=USER -e domain=DOMAIN -e mandrill_username=USERNAME -e mandrill_api_key=API_KEY goabout/exim-mandrill


## Variables

The images uses
[jcassee/templated-entrypoint](https://github.com/jcassee/templated-entrypoint)
for parameterization. The following variables are available:

* **hostname**: The mailer hostname. If unset, the container hostname is used.
* **domain**: Used to force a sender domain. If an outgoing message has a sender
              address with a different domain, it will be substituted by
              "fallback_user+original_user%original_domain@domain".
              If unset, no rewriting will take place.
* **fallback_user**: The user (local part) used for substituted senders.
                     Default: "root"
* **mandrill_username**: The Mandrill account username.
* **mandrill_api_key**:  The Mandrill account API key.
