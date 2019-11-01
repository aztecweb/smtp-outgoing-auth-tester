# SMTP outgoing auth tester

Simple way to test outgoing server service using [msmtp](https://marlam.de/msmtp/).

You just need to set the outgoing server settings on the `.msmtprc` configuration file and the *To:* and *From:* addresses on the `test.mail` to send a test email.

For more information about the settings that can be used on configuration file, you can check the [msmtp documentation](https://marlam.de/msmtp/msmtp.html).

## Run the send

```bash
cat test.mail | docker run --rm -i \
    --entrypoint=msmtp \
    -v $(pwd)/.msmtprc:/root/.msmtprc \
    alvistack/msmtp -t
```
