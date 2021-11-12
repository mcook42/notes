[[GitHub Actions Migration]]
 
 ## Tasks
 
 - [ ] CI/CD Script & Environment variable migrations  [[Environment Secrets & CI CD Migration]]
 - [ ] Repository Import Documentation
	 - Is this something I will have to do, or can it be done by other teams?
	 - What are the reprecussions of importing the repositories into the terraform state prior to the migration? Can we do this and mark everything with `ignoreChanges`?
 - [x] How to share secrets from main terraform repo to `terraform-github`?
	 - How can we make it as self-service as possible? The current set up would require changing each environment's `main.tf` & `outputs.tf` when adding a new service-account.  Could we leverage the pattern Viraj follows in the perf-test-targets?
		 - CLOUD says this is the best we can do with terraform limitations

### State Import
-   [[Repository Migration]]
	-  [x] Can we import the repository and mark everything as ignoreChanges until teams migrate?
		-   Yes, but only if we set ignore changes to `all` temporarily
-   [x] Current GitHub Teams are imported OR a How-To doc exists for how to bring teams into the terraform state as needed
-   Current GitHub Environments are imported (be wary of altering these because they should only be altered with consent of owning teams) OR a How-To doc exists for how to bring environments into the terraform state as needed
	-   Can this section be skipped in leiu of teams deleting/replacing their environments?
		-   No. This would leave dangling environments, possibly, which would leave us open to old creds being used for nefarious activity
-   Current GitHub Environment Secrets are imported (be wary of altering these because they should only be altered with consent of owning teams) OR a How-To doc exists for how to bring environment secrets into the terraform state as needed
	-   Should likely be just a How-To migrate doc, since the old keys need to be moved over to the new system anyway

