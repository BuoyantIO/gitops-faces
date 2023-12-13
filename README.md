# Faces Demo, GitOps Edition

This repo contains the application configuration for the [Faces demo],
which has been used for a great many things at this point, notably many
[Buoyant] [Service Mesh Academy] workshop and [KubeCrash] events.

## Using The GitOps Edition

This repo is intended to be used as part of a GitOps workflow; it was created
specifically for the [Real World GitOps with Argo CD and Linkerd] [Service
Mesh Academy] workshop. You can find that workshop source in the
[real-world-argo-linkerd] repo, and going through that workshop is the best
way to use this repo.

Alternately, you can also just fork this repo and play around with whatever
GitOps setup you have going. You'll need a Kubernetes cluster into which
you've already installed [Linkerd], [Emissary-ingress], and the [Faces demo],
and both Emissary and Faces must be part of the Linkerd mesh.

Once that's done, point your favorite GitOps setup to the `k8s` directory in
this repo: the manifests there will configure Emissary and the Faces demo so
that if you point your browser at the Emissary ingress service, you'll see

- The Linkerd Viz dashboard at `/`
- The Faces demo at `/faces/`
- The `face` workload at `/face/` -- this is necessary for the Faces demo to
  work! but you won't be pointing a browser directly to it.

**Note**: The configuration here does _not_ configure anything fancy: no
retries, timeouts, circuit breaking, or any of that stuff. It's just the bare
minimum to get the demo working, to give you a place to stand to play with
using GitOps to configure whatever you want.

[Faces demo]: https://github.com/BuoyantIO/faces-demo
[Buoyant]: https://buoyant.io
[Service Mesh Academy]: https://buoyant.io/service-mesh-academy/
[KubeCrash]: https://kubecrash.io/
[Real World GitOps with Argo CD and Linkerd]: https://buoyant.io/register/real-world-gitops-with-argo-cd-and-linkerd
[real-world-argo-linkerd]: https://github.com/BuoyantIO/real-world-argo-linkerd
[Linkerd]: https://linkerd.io
[Emissary-ingress]: https://www.getambassador.io/docs/latest/topics/install/install-ambassador-oss/
