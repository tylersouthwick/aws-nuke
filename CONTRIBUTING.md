# Contributing

Thank you for wanting to contribute to *aws-nuke*.

Because of the amount of AWS services and their rate of change, we rely on your
participation. For the same reason we can only act retroactive on changes of
AWS services. Otherwise it would be a fulltime job to keep up with AWS.


## How Can I Contribute?

### Some Resource Is Not Supported by *aws-nuke*

If a resource is not supported yet by *aws-nuke*, you have two options to
resolve this:

* File [an issue](https://github.com/rebuy-de/aws-nuke/issues/new) and describe
  what resource is missing. We will take care and add it as soon as we have
  some time.
* Add the resource yourself and open a Pull-Request. Please follow the
  guidelines below to see how to create such a resource.


### Some Resource Does Not Get Deleted

Please check the following points before creating a bug issue:

* Is the resource actually supported by *aws-nuke*? If not, please follow the
  guidelines above.
* Are there permission problems? In this case *aws-nuke* will print errors,
  that usually contain the status code `403`.
* Did you just get scared by an error that was printed? *aws-nuke* does not
  know about dependencies between resources. To work around this it will just
  retry deleting all resources in multiple iterations. Therefore it is normal
  that there are a lot of dependency errors in the first one. The iterations
  are separated by lines starting with `Removal requested: ` and only the
  errors in the last block indicate actual errros.

File [an issue](https://github.com/rebuy-de/aws-nuke/issues/new) and describe
as accurately as possible how to generate the resource on AWS that cause the
errors in *aws-nuke*. Ideally this is provided in a reproducable way like
a Terraform template or AWS CLI commands.


### I Have Ideas to Improve *aws-nuke*

You should take these steps, if you have an idea how to import *aws-nuke*:

1. Check the [issues page](https://github.com/rebuy-de/aws-nuke/issues),
   whether someone already had the same or a similar idea.
2. Also check the [closed
   issues](https://github.com/rebuy-de/aws-nuke/issues?utf8=%E2%9C%93&q=is%3Aissue),
   because this might already have been implemented, but not yet released. Also
   the idea might no be viable for unobvious reasons.
3. Join the discussion, if there is already an related issue. If this is not
   the case, open a new issue and describe your idea. Afterwards, we can
   discuss this idea and form a proposal.


### I Just Have a Question

Join our ICR channel [`#aws-nuke`](https://webchat.freenode.net/?channels=aws-nuke) at `chat.freenode.net`.


## Resource Guidelines

* pagination
* remove single resources only
* filter non-removable resources
* add properties
* string not necessary
* SDK not updated?

## Styleguide

### Go

* gofmt
* early return
* https://github.com/golang/go/wiki/CodeReviewComments#initialisms
* https://github.com/golang/go/wiki/CodeReviewComments

### Git

* rebase instead of merge
