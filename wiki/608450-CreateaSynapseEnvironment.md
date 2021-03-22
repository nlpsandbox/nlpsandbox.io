<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Introduction

Synapse is a collaborative platform for researchers and developers. Synapse is developed by [Sage Bionetworks] to offer services that support:

- Organization of digital research assets (e.g., files, SQL tables, Docker images)
-  Provenance to give researchers credit for their work
- Collaboration among researchers

The NLP Sandbox builds on the successes of previous scientific challenges that have been organized using Synapse. The NLP Sandbox relies on the following features of Synapse to enable its users to develop and benchmark new NLP Sandbox Tools:

- Creation and management of Teams
- Unlimited storage of private Docker images
- Benchmarking the performance of NLP Sandbox tools on public and private datasets

The sections below describe how to set up your development environment on Synapse so that you can start developing and benchmarking your NLP Sandbox tool.

### Create a Synapse account

If you don't have a Synapse account, you can create one at [synapse.org]. Please make sure to complete your profile information.

### Get Certified

You will need to certify your Synapse account to perform the following actions:

- Upload files to Synapse
- Push Docker images to Synapse
- Benchmark the performance of NLP Sandbox tools

Follow these steps to certify your Synapse account:

1. Go to the page [User Types including Certified Users].
2. Click on the button "Become a Certified User".
3. Complete the certification form.

You can verify that your account is certified by visiting your [Synapse Profile]. You will see a "Certified" badge to the right on your profile page.

![Synapse Certified Account]

### Create a Synapse Team

Playing - ahem - Working together will make your experience developing and benchmarking NLP Sandbox tools more enjoyable. When you submit a tool for evaluation, Synapse will ask if the submission is made on behalf of a User or a Team. Submitting as a Team offers more flexibility if you decide to invite team members to collaborate with you in the future.

Head to your [Synapse Teams page] to create a new Team. If you are looking for Team members, check out the [NLP Sandbox Users & Teams] page. You can also re-use an existing Synapse Team that you have for other projects.

### Create a Synapse Project

[Synapse projects] offer unlimited storage for public and private Docker images, which is the submission format required by the NLP Sandbox. Synapse projects also offer other collaborative tools such as Wikis, file sharing, and a discussion forum. Sharing settings can be set individually for each of these features.

![Synapse Project Docker]

Finally, be sure to give your Team access to this project by clicking on the button **Project Settings** and adding them to the project with the appropriate level of permissions.

### Register for the NLP Sandbox

Click on this button to register yourself:

${jointeam?teamId=3413388&isChallenge=false&isMemberMessage=You have successfully registered for the NLP Sandbox%2E&text=Register&isSimpleRequestButton=true&requestOpenText=Your registration is in progress%2E&successMessage=Your registration is in progress%2E}

Click on this button to register your team:

${registerChallengeTeam?challengeId=4422&buttonText=Register your Team}

### Conclusion

Your Synapse environment is now ready! Head to the next page of this tutorial to learn how to build an NLP Sandbox tool that can be benchmarked and shared in the NLP Sandbox.

{column}
{row}

<!-- Links -->

[Sage Bionetworks]: https://sagebionetworks.org/
[synapse.org]: https://www.synapse.org/
[User Types including Certified Users]: https://docs.synapse.org/articles/accounts_certified_users_and_profile_validation.html
[Synapse Profile]: https://www.synapse.org/#!Profile:v/profile
[Synapse Teams page]: https://www.synapse.org/#!Profile:v/teams
[NLP Sandbox Users & Teams]: #!Synapse:syn22277124/wiki/604836
[Synapse Project Docker]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/synapse/synapse-project-docker-repository.png
[Synapse projects]: https://docs.synapse.org/articles/getting_started.html
[Synapse Certified Account]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/synapse/synapse-certified-account.png
