# standards

Flow technology standards - largely influenced by Mike's prior work at
[Gilt](https://github.com/gilt/standards)

## Open Source Way

At Flow, we follow the open source way - that is, when asking questions about how we design software, we will defer to how the open source community works.

Examples:

  - *How much documentation do we write?*
  
    Let's look at our favorite open source projects and see how their documentation looks. One example we like is the [react project](https://facebook.github.io/react/)

  - *What level of testing do we use?*

    Let's look at our favorite open source projects and see how their testing looks. One example we like is the [play framework itself](https://www.playframework.com/documentation)

  - *What type of API should I build?*

    Let's look at our favorite open source projects and look at their APIs. One example we like is [Stripe](https://stripe.com/docs/api)


## Comprehensive

We build software that is comprehensive. In practice this means that we are transparent and complete with the information that we provide.

Examples:

  - if we write personalization software, we build in the ability to
    understand why a recommendation was or was not made.

  - in our authorization software, we always return a detailed summary
    that describes why the authorization was either granted or denied.
  
## Security

  - Deny access by default: That is, something must be true in order
    for authorization to be granted. If no decision is made, we deny
    access by default.
