<h1>Repository of YAML templates for testing terraform modules from Azure Pipelines</h1>

<p>
In this repository you can find 3 different versions of YAML templates to test terraform modules using Azure Pipelines.

Default stages in each template are:
 <ul>
    <li>build - in this stage the artifact will be made based on configuration on the branch</li>
    <li>deploy - in this stage terraform configuration will be applied on selected environment and the configuration is read from saved state in the artifact</li>
 </ul>

 You can find 3 different templates configuration on the repository
<ul>
    <li>
        <h2>templates-1</h2>
        <p>This version is supporting additional variables "lastProvisioning" and "lastProvisioningDate". Both values will be passed from pipeline system variables - "who started a pipeline" and "when pipeline was started". You need to add this two variables to your configuration.
        </p>
    </li>
    <li>
        <h2>templates-2</h2>
        <p>This version is not supporting additional variables mentioned in previous description.</p>
    </li>
    <li>
        <h2>templates-3</h2>
        <p>This version is supporting different input regarding "environment" variables files witch are located in <a href="./variables/">variables</a> folder. You can prepare different configuration for the same environment (in different files) and switch between them without doing additional commits. For example: to start DR Terraform module test you will need to change value for variable "isMultiRegional" and commit this change to branch. But if you prepare another file with proper values then you can pass the name of the file when starting pipeline. It will be quicker to test.</p>
    </li>
</ul>
</p>


