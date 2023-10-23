# Download_github_package_powershell
Downloading the github package from the github through the powershell script. We can download any version or latest version of github

### Usage
To use this template, follow these steps:

1. Include the `downloadpackage.yml` file in your Azure repository.

2. In your Azure DevOps pipeline YAML file, add the following code to reference the template:

```yaml
resources:
  repositories:
    - repository: download
      type: github
      name: {repo}
      ref: <respective branch name>
      endpoint: '{}'
steps:
- template: downloadpackage.yml@download
    parameters:
        packagename: "" 
        packageversion: "latest"
        path: $(Build.SourcesDirectory)/folderPackage

```
