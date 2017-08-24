getting-started-golang
======================

[![wercker status](https://app.wercker.com/status/eeb2240b621c0181c460d73a18971de2/s "wercker status")](https://app.wercker.com/project/bykey/eeb2240b621c0181c460d73a18971de2)

A sample application in Go for wercker.

This application uses the `google/golang` container obtained from the [Docker Hub](https://registry.hub.docker.com/u/google/golang/)

## Setup, Build and Run
Clone this repo and cd into the directory:

```
> git clone git@github.com:wercker/getting-started-golang.git
> cd getting-started-golang
```

then build and launch the executable:

```
> go build
> ./getting-started-golang
```

Now point your browser at `http://localhost:5000/cities.json` to see:
```
"{'cities':'San Francisco', 'Amsterdam', 'Berlin', 'New York', 'Tokyo'}"
```

---
Sign up for wercker [here](http://wercker.com)
Learn more on our [dev center](http://devcenter.wercker.com)
