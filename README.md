# getting-started-golang

[![wercker status](https://app.wercker.com/status/eeb2240b621c0181c460d73a18971de2/s "wercker status")](https://app.wercker.com/project/bykey/eeb2240b621c0181c460d73a18971de2)

A sample application in Go for Wercker.

This application uses the `golang` container obtained from the [Docker Hub](https://hub.docker.com/_/golang/)

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
{"cities":["Amsterdam","Berlin","New York","San Francisco","Tokyo"]}
```

The second, and more useful, way is to use the `wercker dev` command to launch the binary within a Docker container, using the base image defined in the `box/id` property at the top of the `wercker.yml`, like so:
```
wercker dev --expose-ports
```
The `dev` target inside `wercker.yml` uses the `internal/watch` step to dynamically reload the runtime container when sourcefile changes are detected, which allows you to quickly test changes without having to kill/rebuild/relaunch the container. For instance, add another city to the array on `main.go:15` like so:

```
Cities: []string{"Amsterdam","Berlin","New York","San Francisco","Tokyo","London"},
```

and then refresh your browser pointing to `http://localhost:5000/cities.json` to see:
```
{"cities":["Amsterdam","Berlin","New York","San Francisco","Tokyo","London"]}}
```

---
Sign up for Wercker: http://www.wercker.com

Learn more at: http://devcenter.wercker.com
