# Dummy Crossplane configuration

This repository defines a [Crossplane
configuration](https://docs.crossplane.io/v1.11/concepts/packages/#configuration-packages)
that depends on only `provider-dummy` which includes a dummy external API for
contained experimentation with the least amount of setup - such as requiring no
credentials.

This repository is only intended for learning and experimentation. The APIs may
have breaking changes any time.

## What's Inside

* [`crossplane.yaml`](./crossplane.yaml): The definition file for a configuration.
* [`apis`](./apis): The `CompositeResourceDefinition` and `Composition`
  resources that make up APIs.
* [`examples`](./examples/): Example YAMLs for the defined APIs.

## Getting Started

1. In Upbound Console, create a control plane that depends on a configuration
   repository forked from this one.
2. Deploy the external server of the `provider-dummy` somewhere that is publicly
   exposed. See example deployment [here](https://github.com/upbound/provider-dummy/blob/main/cluster/server-deployment.yaml).
   * You can also install the provider to Upbound in no-op mode and deploy
     controller and server somewhere else together by following the instructions
     [here](https://github.com/upbound/provider-dummy#no-op-mode).
3. Create a `ProviderConfig` for `provider-dummy` with the endpoint of the
   server.
4. Create your first resource from [`examples`](./examples/) folder!
