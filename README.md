# GoJsFuck
## Fork of [UnJsFuck](https://github.com/vineesh12344/gojsfuck) which wasn't packaged properly

[![Go Report Card](https://goreportcard.com/badge/github.com/vineesh12344/gojsfuck)](https://goreportcard.com/report/github.com/vineesh12344/gojsfuck)
<a href="https://github.com/vineesh12344/gojsfuck/actions"><img src="https://github.com/vineesh12344/gojsfuck/actions/workflows/build_tests.yml/badge.svg"/></a>
[![codecov](https://codecov.io/gh/vineesh12344/gojsfuck/branch/main/graph/badge.svg?token=WJRP98YJCW)](https://codecov.io/gh/vineesh12344/gojsfuck)

Encode/Decode [JSFuck](https://github.com/aemkei/jsfuck/) (0.5.0) obfuscated Javascript.

Helpful resources:
* https://jsfuck.com/ - test encoding (results may differ)
* https://enkhee-osiris.github.io/Decoder-JSFuck/ - test decoding

## Usage
Use latest release [binary](https://github.com/vineesh12344/gojsfuck/releases) or install the tool with:
```sh
go install github.com/vineesh12344/gojsfuck
```

### Encode
```sh
unjsfuck encode ./test/test_plain.js
```

### Decode
```sh
unjsfuck decode ./test/test_enc.js
```

### Test
```sh
go test . -v
```


## Package usage
### Install
```sh
go get github.com/vineesh12344/gojsfuck
```

### Import
```go
import "github.com/vineesh12344/gojsfuck/jsfuck"
```

### Decode
```go
yourEncodedJS := "..."

decoder := jsfuck.New()
decoder.Init()
fmt.Println(decoder.Decode(yourEncodedJS))
```
### Encode
```go
yourPlainJS := "alert(123);"

encoder := jsfuck.New()
encoder.Init()

encoded := encoder.Encode(yourPlainJS)

// Wrap in eval and parent scope execution
wrapped := jsFuck.Wrap(encoded, true, true) 
fmt.Println(wrapped)
```