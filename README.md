# jenkins
**GitHub = AWS CodeCommit** <br>
&emsp;Both are hosted Git repositories where you store your source code.<br>
2.&emsp; **GitHub Actions = AWS CodeBuild + AWS CodePipeline** <br>
Explanation: GitHub Actions does two things at once. It provides the automation workflow (the pipeline) and the compute runners that execute the code compilation. In AWS, this is split into two separate services: **CodePipeline** coordinates the steps, while **CodeBuild** provides the temporary server power to execute them.<br>
**Jenkins Pipeline = AWS CodePipeline + AWS CodeBuild** <br>
Explanation: Just like GitHub Actions, a single Jenkins server handles both the pipeline structure (Jenkinsfile) and runs the actual build jobs on its nodes.<br>

**Summary Cheat Sheet**<br>
Think of it this way: AWS likes to break everything down into specialized, modular services, whereas Jenkins and GitHub Actions bundle things together:<br>
### CI/CD Tool Mapping Reference


| What it does | AWS Service | GitHub Equivalent | Jenkins Equivalent |
| :--- | :--- | :--- | :--- |
| **Stores Code** | CodeCommit | GitHub Repositories | Git / Bitbucket |
| **Orchestrates the Flow** | **CodePipeline** | GitHub Actions (Workflows) | Jenkins Pipeline |
| **Executes the Build/Tests** | **CodeBuild** | GitHub Actions (Runners) | Jenkins Agents / Nodes |
| **Deploys to Servers** | CodeDeploy | GitHub Actions (Deploy steps) | Jenkins Deploy Plugins |
