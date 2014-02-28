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
