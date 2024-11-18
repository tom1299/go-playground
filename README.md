# Simple go experimentation
* Goal: Learn as much golang in order to run / contribute to [stakater/Reloader](https://github.com/stakater/Reloader)
* First changes to do are:
    * Update dependencies (preferably the kubernetes client version)
    * Add a test case
    * Try to contribute to an issue

## Questions
* How to have to different golang versions installed on the same computer (something like venvs in python)
* Look at viper: https://github.com/spf13/viper

## Continue
Here: https://spf13.com/presentation/building-an-awesome-cli-app-in-go-oscon/ (slide 192)

## Building
Build a go application for different operating systems: `env GOOS=windows GOARCH=amd64 go build .`

## Updating go version (Copilot answer)

1. Open the [`go.mod`](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fhome%2Freuhl%2Fgit%2Fgithub%2Fgo-playground%2Fgo.mod%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "/home/reuhl/git/github/go-playground/go.mod") file in your project.
2. Locate the [`go`](command:_github.copilot.openSymbolFromReferences?%5B%22go%22%2C%5B%7B%22uri%22%3A%7B%22%24mid%22%3A1%2C%22fsPath%22%3A%22%2Fhome%2Freuhl%2Fgit%2Fgithub%2Fgo-playground%2Fgo.mod%22%2C%22external%22%3A%22file%3A%2F%2F%2Fhome%2Freuhl%2Fgit%2Fgithub%2Fgo-playground%2Fgo.mod%22%2C%22path%22%3A%22%2Fhome%2Freuhl%2Fgit%2Fgithub%2Fgo-playground%2Fgo.mod%22%2C%22scheme%22%3A%22file%22%7D%2C%22pos%22%3A%7B%22line%22%3A0%2C%22character%22%3A7%7D%7D%5D%5D "Go to definition") directive, which specifies the current Go version.
3. Change the version number to the desired Go version.
4. Save the [`go.mod`](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fhome%2Freuhl%2Fgit%2Fgithub%2Fgo-playground%2Fgo.mod%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "/home/reuhl/git/github/go-playground/go.mod") file.
5. Run `go mod tidy` to ensure the module dependencies are updated.

### Example

If you want to update the Go version from [`1.18`](command:_github.copilot.openSymbolFromReferences?%5B%221.18%22%2C%5B%7B%22uri%22%3A%7B%22%24mid%22%3A1%2C%22fsPath%22%3A%22%2Fhome%2Freuhl%2Fgit%2Fgithub%2Fgo-playground%2Fgo.mod%22%2C%22external%22%3A%22file%3A%2F%2F%2Fhome%2Freuhl%2Fgit%2Fgithub%2Fgo-playground%2Fgo.mod%22%2C%22path%22%3A%22%2Fhome%2Freuhl%2Fgit%2Fgithub%2Fgo-playground%2Fgo.mod%22%2C%22scheme%22%3A%22file%22%7D%2C%22pos%22%3A%7B%22line%22%3A2%2C%22character%22%3A3%7D%7D%5D%5D "Go to definition") to `1.19`, modify the [`go.mod`](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fhome%2Freuhl%2Fgit%2Fgithub%2Fgo-playground%2Fgo.mod%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "/home/reuhl/git/github/go-playground/go.mod") file as follows:

```go
module go-playground

go 1.19

require github.com/spf13/cobra v1.8.1

require (
	github.com/inconshreveable/mousetrap v1.1.0 // indirect
	github.com/spf13/pflag v1.0.5 // indirect
)
```

Then, run the following command in your terminal:

```sh
go mod tidy
```

## Requesting certificates using lego

Thomas-Reuhl_dtag: Can I build a go module which requires golang `1.18` with go `1.23` ?

GitHub Copilot: Yes, you can build a Go module that requires Go `1.18` with Go `1.23`. Go is backward compatible, so a newer version of the Go compiler can build code that was written for an older version.

To specify that your module requires at least Go `1.18`, you can set the `go` directive in your [`go.mod`](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fhome%2Freuhl%2Fgit%2Fgithub%2FReloader-fork%2Fgo.mod%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "/home/reuhl/git/github/Reloader-fork/go.mod") file like this:

```go
module your-module-name

go 1.18

require (
    // other dependencies
)
```

Then, you can build your module with Go `1.23` using the following command in your terminal:

```sh
go build
```

This will use the Go `1.23` compiler to build your module, while still respecting the `go 1.18` directive in your [`go.mod`](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fhome%2Freuhl%2Fgit%2Fgithub%2FReloader-fork%2Fgo.mod%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "/home/reuhl/git/github/Reloader-fork/go.mod") file.

Thomas-Reuhl_dtag: So the compiler ensures backward compatibility ?

GitHub Copilot: Yes, the Go compiler ensures backward compatibility. This means that code written for an older version of Go (e.g., Go 1.18) should compile and run correctly with a newer version of the Go compiler (e.g., Go 1.23). The Go team places a strong emphasis on maintaining backward compatibility to ensure that upgrading to a newer version of Go does not break existing code.

Thomas-Reuhl_dtag: Is there a go module for requesting a certificate like I can do with cert-bot ? 

GitHub Copilot: Yes, there is a Go module called `lego` that you can use to request certificates from Let's Encrypt, similar to what you can do with Certbot. The `lego` library is a Let's Encrypt client and supports the ACME protocol.

Here's a basic example of how you can use `lego` to request a certificate:

1. Install the `lego` library:

```sh
go get -u github.com/go-acme/lego/v4
```

2. Create a Go program to request a certificate:

```go
package main

import (
    "crypto/rsa"
    "crypto/x509"
    "encoding/pem"
    "fmt"
    "github.com/go-acme/lego/v4/certificate"
    "github.com/go-acme/lego/v4/lego"
    "github.com/go-acme/lego/v4/registration"
    "github.com/go-acme/lego/v4/providers/dns/cloudflare"
    "github.com/go-acme/lego/v4/lego"
    "github.com/go-acme/lego/v4/registration"
    "log"
    "os"
)

func main() {
    // Replace with your email and domain
    email := "your-email@example.com"
    domain := "your-domain.com"

    // Create a user
    user := NewUser(email)

    // Create a config
    config := lego.NewConfig(user)
    config.CADirURL = lego.LEDirectoryProduction

    // Create a client
    client, err := lego.NewClient(config)
    if err != nil {
        log.Fatal(err)
    }

    // Register the user
    reg, err := client.Registration.Register(registration.RegisterOptions{TermsOfServiceAgreed: true})
    if err != nil {
        log.Fatal(err)
    }
    user.Registration = reg

    // Create a DNS provider (e.g., Cloudflare)
    provider, err := cloudflare.NewDNSProvider()
    if err != nil {
        log.Fatal(err)
    }

    // Set the DNS provider
    client.Challenge.SetDNS01Provider(provider)

    // Request a certificate
    request := certificate.ObtainRequest{
        Domains: []string{domain},
        Bundle:  true,
    }
    cert, err := client.Certificate.Obtain(request)
    if err != nil {
        log.Fatal(err)
    }

    // Save the certificate
    saveCert(cert)
}

func saveCert(cert *certificate.Resource) {
    err := os.WriteFile("cert.pem", cert.Certificate, 0600)
    if err != nil {
        log.Fatal(err)
    }
    err = os.WriteFile("key.pem", cert.PrivateKey, 0600)
    if err != nil {
        log.Fatal(err)
    }
    err = os.WriteFile("ca.pem", cert.IssuerCertificate, 0600)
    if err != nil {
        log.Fatal(err)
    }
}

type User struct {
    Email        string
    Registration *registration.Resource
    key          *rsa.PrivateKey
}

func NewUser(email string) *User {
    key, err := rsa.GenerateKey(rand.Reader, 2048)
    if err != nil {
        log.Fatal(err)
    }
    return &User{
        Email: email,
        key:   key,
    }
}

func (u *User) GetEmail() string {
    return u.Email
}

func (u *User) GetRegistration() *registration.Resource {
    return u.Registration
}

func (u *User) GetPrivateKey() crypto.PrivateKey {
    return u.key
}
```

This example demonstrates how to use the `lego` library to request a certificate from Let's Encrypt using the DNS-01 challenge with Cloudflare as the DNS provider. You will need to replace the email, domain, and DNS provider configuration with your own details.