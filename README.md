getting-started-golang
======================

[![wercker status](https://app.wercker.com/status/eeb2240b621c0181c460d73a18971de2/s "wercker status")](https://app.wercker.com/project/bykey/eeb2240b621c0181c460d73a18971de2)

A sample application in Go for wercker.

This application uses the `google/golang` container obtained from the [Docker Hub](https://registry.hub.docker.com/u/google/golang/)

## Setup & Build
Clone this repo and cd into the directory:

```
git clone https://github.com/wercker/getting-started-golang.git
cd getting-started-golang
```

then build the executable:
```
go build
```

## Running
You can run the executable in a couple of different ways. The first is to simply launch the executable:
```
./getting-started-golang
```

Now point your browser at `http://localhost:5000` to see:
```
Hello World!
```
or at `http://localhost:5000/cities.json` to see:
```
"{'cities':'San Francisco', 'Amsterdam', 'Berlin', 'New York', 'Tokyo'}"
```

The second is to use the
```
wercker dev --expose-ports
```
command to launch the binary within a Docker container, using the base image defined in the `box/id` property at the top of the `wercker.yml`. The `dev` target inside `wercker.yml` uses the `internal/watch` step to dynamically reload the runtime container when sourcefile changes are detected, which allows you to quickly test changes without having to kill/rebuild/relaunch the container. So for instance, add another city to the array on `main.go/10' like so:

```
data, _ := json.Marshal("{'cities':'San Francisco', 'Amsterdam', 'Berlin', 'New York', 'Tokyo', 'London'}")
```

and then refresh your browser pointing to `http://localhost:5000/cities.json` to see:
```
"{'cities':'San Francisco', 'Amsterdam', 'Berlin', 'New York', 'Tokyo', 'London'}"
```

---
Sign up for wercker: http://www.wercker.com
Learn more at: http://devcenter.wercker.com
