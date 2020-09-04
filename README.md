# Abell Page Action

Example of using Abell Pages Action (Experimental)

**Demo:** [https://saurabhdaware.github.io/use-github-action](https://saurabhdaware.github.io/use-github-action) 

## Host your GitHub Page with Abell Pages Action

- Create `.github/workflows/abell-deploy.yml` with content
```yaml
on:
  push:
    branches: [master] # branch to trigger deploy, mostly default branch

jobs:
  abell-deploy:
    runs-on: ubuntu-latest
    name: Abell Website Deployment
    steps:
    - name: Checkout
      uses: actions/checkout@v2
    - name: Abell Pages Action
      id: abell-pages
      uses: saurabhdaware/abell-pages-action@master
      with:
        site-path: 'https://github.com/saurabhdaware/abell-readme-layout'
        deploy-branch: 'master' # branch to deploy from, mostly default branch
```
- In Repository Settings -> GitHub Pages, set source branch to `gh-pages` and directory to `/docs`.
- Tadaa 🎉 Your website will be hosted on `https://<your-github-username>.github.io/<repository-name>`


For reference, you can look into [.github/workflows/abell-deploy.yml](.github/workflows/abell-deploy.yml)

Thanks!