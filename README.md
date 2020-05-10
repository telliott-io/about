# About [telliott.io](https://github.com/telliott-io) (or...overengineering a personal website for the heck of it)

This GitHub org contains various projects that make up my personal site: https://telliott.io.

It was made with the aim of being able to migrate between multiple clouds easily, using infrastructure-as-code and GitOps practices.

The result is way more involved than a personal site has any real right to be, but it's been great for learning new technologies and trying things out in a low-stakes environment.

## Background

As we embarked upon a move to a multi-cloud Kubernetes deployment model [at work](https://www.yext.com), I had a heck of a lot to learn in a short space of time. So I wanted to try and deploy my own
multi cloud site first to get a feel for common techniques and decisions that might come back to bite us later.

## Goals

The [telliott-io GitHub organization](https://github.com/telliott-io) has two main purposes:

* Learn DevOps practices for building cloud-native applications
* Provide myself a platform for building out new projects quickly in future

The first is key to what made me want to do this in the first place. The second is to keep me honest with the first, so anything I build will be at least somewhat reusable.

These are vague and kinda meta goals, so I also set out with a couple of specific use cases:

* I should be able to move the site between two cloud providers with zero human interaction after triggering the move, and this should result in minimal to no downtime [**IN PROGRESS**](https://github.com/orgs/telliott-io/projects/1)
* I should be able to create a new application from a template, push to GitHub and automatically have it deployed to "production". [**IN PROGRESS**](https://github.com/orgs/telliott-io/projects/3)
* Someone else should be able to fork a few of these repos and stand up their own site in their own cloud accounts with minimal additional configuration. [**IN PROGRESS**](https://github.com/orgs/telliott-io/projects/3)

## Technologies

I've picked up a few new technologies with this project. Some I had in mind when I first set out, and
some presented themselves as the best tool for the job.

* [Kubernetes](https://kubernetes.io/) - container orchestration
* [Terraform](https://www.terraform.io/) - infrastructure as code
* [ArgoCD](https://argoproj.github.io/argo-cd/) - GitOps-style deployment to Kubernetes
* [GitHub Actions](https://github.com/features/actions) - Continuous Integration

## Cloud Providers

The site currently supports use of a few different cloud providers, and I can hopefully expand this list as time goes on.

### Kubernetes

* [Google Cloud](https://cloud.google.com/kubernetes-engine)
* [DigitalOcean](https://www.digitalocean.com/products/kubernetes/)

### CDN

* [Cloudflare](https://www.cloudflare.com/)

## Key Repos

* [infra](https://github.com/telliott-io/infra) - this is the starting point, defining the infrastructure on which everything else runs. All infrastructure is defined as Terraform plans.
* [bootstrap](https://github.com/telliott-io/bootstrap) - a Helm chart loaded by the infrastructure Terraform to populate the cluster using [ArgoCD's bootstrap model](https://argoproj.github.io/argo-cd/operator-manual/cluster-bootstrapping/).
* [applications](https://github.com/telliott-io/applications) the actual set of applications to be deployed to the cluster with ArgoCD.
* [front](https://github.com/telliott-io/front) the application powering the front page of [telliott.io](https://telliott.io).

## Projects Hosted Here

* [Emojicode Playground](https://emojicode.telliott.io/) execute Emojicode programs from your web browser