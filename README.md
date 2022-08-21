<img src="misc/gumble.svg" width="200" align="right">

# gumble

gumble is a [Mumble](https://mumble.info/) client implementation in Go

## Sub-projects

- gumble ([docs](https://pkg.go.dev/layeh.com/gumble/gumble))
    - Client library
- gumbleopenal ([docs](https://pkg.go.dev/layeh.com/gumble/gumbleopenal))
    - [OpenAL](http://kcat.strangesoft.net/openal.html) audio system for gumble
- gumbleffmpeg ([docs](https://pkg.go.dev/layeh.com/gumble/gumbleffmpeg))
    - [ffmpeg](https://www.ffmpeg.org/) audio source for gumble
- gumbleutil ([docs](https://pkg.go.dev/layeh.com/gumble/gumbleutil))
    - Extras that can make working with gumble easier

## Example

```go
package main

import (
  "github.com/talkkonnect/gumble/gumble"
  "github.com/talkkonnect/gumble/gumbleutil"
)

func main() {
  gumbleutil.Main(gumbleutil.Listener{
    UserChange: func(e *gumble.UserChangeEvent) {
      if e.Type.Has(gumble.UserChangeConnected) {
        e.User.Send("Welcome to the server, " + e.User.Name + "!")
      }
    },
  })
}
```

## Modified By Suvir

- Ran Generate to add channel listener features to gumble

## License

MPL 2.0

## Original Author

Tim Cooper (<tim.cooper@layeh.com>)
