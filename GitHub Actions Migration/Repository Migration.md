## State Import
-   Current GitHub Repositories owned by BillHeroInc are imported into the github workspace state in terraform cloud OR a How-To doc exists for how to bring repositories into the terraform state as needed
	-   [x] Can we import the repository and mark everything as ignoreChanges until teams migrate?
		-   Yes, but only if we set ignore changes to `all` temporarily
-   Current GitHub Teams are imported OR a How-To doc exists for how to bring teams into the terraform state as needed
-   Current GitHub Environments are imported (be wary of altering these because they should only be altered with consent of owning teams) OR a How-To doc exists for how to bring environments into the terraform state as needed
-   Current GitHub Environment Secrets are imported (be wary of altering these because they should only be altered with consent of owning teams) OR a How-To doc exists for how to bring environment secrets into the terraform state as needed


**How to import repository state**
1. Define a basic module for the repo
	-  `module "[repo-name]" {  
  			source = "./modules/repository"  
 			repository_name = "[repo-name]"  
 			writer_teams = []  
		}`
2. Import the resources:
	1. `terraform import module.[repo-name].github_repository.repository [repo-name]`
	2. `terraform import module.[repo-name].github_branch_protection_v3.approver-teams [repo-name:main-branch-name]`
	3. `terraform import module.[repo-name].default-branch [tbd]`
	4. `terraform import module.[repo-name].github_repository_file.codeowners .github/CODEOWNERS:[main-branch-name]`