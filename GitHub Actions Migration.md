[[GitHub Actions Migration]]
 
 ## Tasks
 
 - [ ] CI/CD Script & Environment variable migrations  [[Environment Secrets & CI CD Migration]]
 - [ ] Repository Import Documentation
	 - Is this something I will have to do, or can it be done by other teams?
	 - What are the reprecussions of importing the repositories into the terraform state prior to the migration? Can we do this and mark everything with `ignoreChanges`?
 - [ ] How to share secrets from main terraform repo to `terraform-github`?
	 - How can we make it as self-service as possible? The current set up would require changing each environment's `main.tf` & `outputs.tf` when adding a new service-account.  Could we leverage the pattern Viraj follows in the perf-test-targets?