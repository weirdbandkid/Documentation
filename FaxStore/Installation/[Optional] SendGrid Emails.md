FaxStore comes shipped with the option to have an email system using popular API framework [SendGrid](https://sendgrid.com). Currently FaxStore uses emails for the following;


- When a customer purchases an item it sends them a confirmation email with a list of what they bought.

- You're also able to email a specific user or all users with a custom email to notify users of changes.

---

Create an account on the [SendGrid API](https://app.sendgrid.com) website. Once you have reached the dashboard go to API Keys and create a key.

You might need to authenticate a domain. If so follow those steps provided.

*Ensure to copy the key and save it as it can't be displayed again.*

![sendgrid](https://faxes.zone/i/UocQE.gif)

Place your API key into the `sendGridToken` option in the config file.

Lastly make sure `useEmails` is set to `true` in the config.

---

If you already have the store set up and running restart it to have the changes take effect.
Otherwise [continue to step six](/c/faxstore/stepsix)
