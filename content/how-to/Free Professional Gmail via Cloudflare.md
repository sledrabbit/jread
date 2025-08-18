---
tags:
  - how-to
---

Purchasing a domain such as `yourcompany.com` does not include the ability for you to send and receive emails. Typical email hosting offerings throw a `$x/user/month` fee or something like an Office 365 subscription on top of your domain registration. This #how-to will help you connect your Gmail account with your domain via Cloudflare to avoid yet another subscription.

## Prerequisites

* Have a Gmail account ready for use
* Purchase a custom domain
* Set Cloudflare to be your domain's DNS provider[^1] 

>[!tip]
> If you do not already have a domain, Cloudflare domains are sold at cost (cheap) and the DNS will already be configured.

After Cloudflare is handling your site's DNS, the next step is to setup Email Routing [^2]. Save the custom email address for later.

## Configure Gmail to Use Your Domain

The first thing you need to do is enable two-factor authentication [^3] for your Gmail account because this is required to generate an app password.

Next create an app password [^4] and save that password somewhere.

Finally, click the settings gear in your Gmail account's main page > `See All Settings` > `Accounts and Import` > `Send mail as:` > `Add another email address`.

A pop-up window should appear titled *Add another email address you own*.

Field | Value
-- | --
Name | Display name that recipient sees, e.g. `Jack Sparrow`
Email address | Your custom email address from Cloudflare Email Routing

* *Uncheck* `treat as an alias`
* *Click* `Next Step`

Field | Value
-- | --
SMTP | smtp.gmail.com
Username | Your actual Gmail address
Password | app password

* *Click* `Add Account`

You'll receive a confirmation email from the Gmail Team. Verify by clicking on the link and now you can send emails from your custom domain!


[^1]: https://developers.cloudflare.com/dns/zone-setups/full-setup/setup/#add-site-to-cloudflare

[^2]: https://developers.cloudflare.com/email-routing/

[^3]: https://support.google.com/accounts/answer/185839?hl=en&co=GENIE.Platform%3DDesktop

[^4]: https://support.google.com/mail/answer/185833?hl=en&sjid=4109086082113104851-NC
