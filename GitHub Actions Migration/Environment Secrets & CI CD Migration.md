[[Environment Secrets & CI CD Migration]]
## Setting up GH w/ with CI/CD
Choose your own adventure questions:
1. Do you have a current repository and/or CI/CD pipeline set up?
	- You'll need to work with SRE to get your resources imported into the terraform state
	- TBD
1. Do you need to set up new resources?
	1. Setting up a repository w/o CI/CD
	2. Setting up a repo w/ CI/CD

## Birds
1. Define the roles needed in the service-account in terraform proper (silver,platinum,gold)
	1. Use Birds Lambda
2. Add the service account resources to the outputs in terraform proper
3. Create environment(s) in `terraform-github`
	1. Start with Dev and test from the next steps before moving on to other envs
4. Move birds over to gh workflow for deploying lambdas
5. Test a birds deployment