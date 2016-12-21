{{{
"title": "Boxes",
"date": "09-01-2016",
"author": "",
"attachments": [],
"contentIsHTML": false
}}}

### Boxes
Boxes are the templates that store application automation. An instance is a box you install on virtual infrastructure provisioned to a public, private cloud provider, or your own infrastructure. Take a [quick tour](https://www.ctl.io/knowledge-base/ElasticBox/login-and-quick-tour/#tour) to understand the layout of boxes and instances in ElasticBox.

Boxes contain scripts, variables, and metadata to automate processes when instantiated on cloud infrastructure. Stitched together, boxes model complex processes like deploying or upgrading multi-tier enterprise scale applications.

So how do boxes work? A typical application stack may consist of multiple boxes, each one modeling a step of the application’s install. For example, one might model the install of runtime requirements (such as PHP libraries). Another might model the install of a web server (such as Apache). And a third might model connecting to a source control repository (such as Git), pulling the latest code, and installing it on the virtual server. When stacked and instantiated these three boxes install an application. At the same time, each box is independent, reusable and can be consumed by other applications.

**In This Article:**
* [Understanding Box Basics](https://www.ctl.io/knowledge-base/ElasticBox/boxes/#understanding-box-basics)

### Understanding Box Basics
**New Box**
To create a new one, click **New**. Select a box type to match your automation:
* [Script](https://www.ctl.io/knowledge-base/ElasticBox/script-box/) - To automate using Bash, PowerShell, Salt, Ansible, Puppet, or Chef.
* [Deployment Policy](https://www.ctl.io/knowledge-base/ElasticBox/deploymentpolicy-box/) - To select and share infrastructure resources, networking, and more from a cloud provider.
* [Application](https://www.ctl.io/knowledge-base/ElasticBox/application-box/) - To configure several boxes to deploy an application with a single click.
* [CloudFormation](https://www.ctl.io/knowledge-base/ElasticBox/cloudformation-box/) - To automate using AWS CloudFormation templates.
* [Container](https://www.ctl.io/knowledge-base/ElasticBox/docker-container-service/) - To automate using container technology like Docker.

Give it a name, optionally a description, and define some basic metadata:

| Metadata | Box Type | What it Means |
|--------------|--------------|---------------------|
| Requirements | Script,<br> CloudFormation,<br> Container | It’s good practice to tag the runtime that the box requires to deploy. ElasticBox auto suggests tags like Linux, Ubuntu, Java and so on. When ready to launch the box, you are presented with deployment policies that match the requirements. These deployment policies provide the right infrastructure or services the box needs to deploy.<br>**Note:** In CloudFormation boxes, the tags help look instances for bindings. |
| Automatic<br>Updates | Script,<br>CloudFormation,<br>Container | Select the level of updates to automatically apply to instances you launch of a box version:<br>* **Off** - It’s turned off by default.<br>* **All Updates** - Applies all changes.<br>* **Minor & Patch Updates** - Applies minor and patch changes to the version deployed.<br>* **Patch Updates** - Applies only the patch changes to the version deployed. |
| Provider | Deployment<br>Policy | Select the cloud provider registered in ElasticBox for which you will carve out infrastructrure resources in the policy. |
| Claims | Deployment<br>Policy | Tag the services and infrastructure that a policy provides like Linux, Ubuntu 12.04, load balancing, and so on for deployments. Add claims so that boxes with matching requirements can successfully deploy using the right policy. |

**Box Sections**
Once you create a box, you can configure and manage it in these sections.
![core-concepts-boxes1.png](../images/ElasticBox/core-concepts-boxes1.png)

| Section | Description |
|------------|----------------|
| Configuration | Automate how a piece of software deploys in the virtual environment by by parameterizing with [variables](https://www.ctl.io/knowledge-base/ElasticBox/parameterizing-boxes-with-variables/) and [events](https://www.ctl.io/knowledge-base/ElasticBox/start-stop-and-upgrade-boxes/). |
| Versions | Keep track deployment configuration changes with the help of versioning. Versions let you consume different configurations of the same box in multiple deployments. From this tab, you can create a new version, see a diff of what changed, or restore a version as the box draft. |
| Share | Invite team members to [collaborate](https://www.ctl.io/knowledge-base/ElasticBox/workspaces-and-collaboration/) and improve the configuration or just let them deploy the box. |
| Deploy | [Launch a new instance](https://www.ctl.io/knowledge-base/ElasticBox/deploying-managing-instances/) of the box draft with this option. This lets you select a specific deployment policy to launch on a cloud provider. |
| Gear Menu | From here, you can edit basic metadata of the box or delete it. |

### Contacting ElasticBox Support
We’re sorry you’re having an issue in [ElasticBox](https://www.ctl.io/elasticbox/). Please review the [troubleshooting tips](https://elasticbox.com/documentation/troubleshooting/troubleshooting-tips/), or contact [ElasticBox support](mailto:support@elasticbox.com) with details and screen shots where possible.

For issues related to API calls, send the request body along with details related to the issue. In the case of a box error, share the box in the workspace that your organization and ElasticBox can access and attach the logs.
* Linux: SSH and locate the log at /var/log/elasticbox/elasticbox-agent.log
* Windows: RDP into the instance to locate the log at ProgramDataElasticBoxLogselasticbox-agent.log