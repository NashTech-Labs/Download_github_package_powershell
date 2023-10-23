# Download_github_package_powershell
Download the package from GitHub through the Powershell script. We can download any version or the latest version of GitHub.

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
      ref: <branch name>
      endpoint: '{}'
steps:
- template: downloadpackage.yml@download
    parameters:
        packagename: "" 
        packageversion: "latest"
        path: $(Build.SourcesDirectory)/folderPackage
        nugetURL: "https://nuget.pkg.github.com/{organisation}/{packagename}/index.json"
        nugetversionURL: "https://nuget.pkg.github.com/{organisation}/download/{packagename}/{packageversion}/{packagename}.{packageversion}.nupkg"

```
