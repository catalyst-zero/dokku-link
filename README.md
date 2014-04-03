# dokku-link

A [dokku](https://github.com/progrium/dokku) plugin to link apps.

## install
```
cd /var/lib/dokku/plugins
git clone https://github.com/catalyst-zero/dokku-link
```

## link

Imagine you want to link app A with app B, so A is able to talk with B. B is
the dependency and need to be created first. Just do `echo "B" >
/home/dokku/A/LINK`. And
[redeploy](https://github.com/scottatron/dokku-rebuild) your app. Now A is able
to access a ENV var `B_CONNECTION` that will look something like
`172.17.0.85:5000`.

## ports

It is possible to link more dinamically. `echo "B:PORT" > /home/dokku/A/LINK`.
If `PORT` is not given, the default port `5000` will be used.

## environments

Long story short, you can always use the `APP_CONNECTION` ENV var.

Having applications for different environments leads to app names like
`A.staging`, `B.development`, etc.. Linking to `app.environment` will strip the
`.environment` part. In that way you always can access the connection ENV var
`APP_CONNECTION`. Otherwise things would be complicated having different names
for that ENV var like `APP_STAGING_CONNECTION`, etc..
