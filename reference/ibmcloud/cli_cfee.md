---

copyright:
  years: 2018, 2020
lastupdated: "2020-03-31"

keywords: cli, cloud foundry enterprise environment, cfee, ibmcloud cfee, cfee environment, cfee instance, target user, list cfee

subcollection: cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}
{:codeblock: .codeblock}

# Working with the Cloud Foundry Enterprise Environment service (ibmcloud cfee)
{: #ibmcloud_commands_cfee}

With {{site.data.keyword.cfee_full}} (CFEE) you can instantiate multiple, isolated, enterprise-grade Cloud Foundry platforms on-demand. Instances of the IBM Cloud Foundry Enterprise service run within your own account in the {{site.data.keyword.cloud_notm}}. The environment is deployed on isolated hardware (Kubernetes clusters). You have full control over the environment, including access control, capacity, version updates, resource usage, and monitoring.

Use the following commands to manage CFEE environments, orgs, spaces, users, and roles.
{: shortdesc}

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

List CFEE environments:
```
ibmcloud cfee environments
```
{: codeblock}

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Show details of a CFEE environment:
```
ibmcloud cfee environment NAME [--id]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>NAME (required)</dt>
   <dd>The name of the environment to be shown.</dd>
   <dt>--id</dt>
   <dd>Show ID only.</dd>
  </dl>

<strong>Examples</strong>:

Show details of a CFEE environment `env_example`:
```
ibmcloud cfee environment env_example
```
{: codeblock}

Show id of a CFEE environment `env_example`:
```
ibmcloud cfee environment env_example --id
```
{: codeblock}

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

List all orgs:
```
ibmcloud cfee orgs [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env NAME</dt>
   <dd>The The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

List all orgs:
```
ibmcloud cfee orgs
```
{: codeblock}

List all orgs of CFEE environment `env_example`:
```
ibmcloud cfee orgs --env env_example
```
{: codeblock}

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Display details of an org:
```
ibmcloud cfee org ORG [--guid] [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
   <dt>--guid</dt>
   <dd>Display org GUID only, all other output for the org is suppressed.</dd>
  </dl>

<strong>Examples</strong>:

Show details of a CFEE org `org_example`:
```
ibmcloud cfee org org_example
```
{: codeblock}

Show details of a CFEE org `org_example` of CFEE environment `env_example`:
```
ibmcloud cfee org org_example --env env_example
```
{: codeblock}

Show GUID of a CFEE org `org_example`:
```
ibmcloud cfee org org_example --guid
```
{: codeblock}

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Create an org:
```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization to be created.</dd>
   <dt>--env NAME</dt>
   <dd>The The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>Quota to assign to the newly created org (use default quota if not specified).</dd>
  </dl>

<strong>Examples</strong>:

Create a CFEE org `org_example`:
```
ibmcloud cfee org-create org_example
```
{: codeblock}

Create a CFEE org `org_example` of CFEE environment `env_example`:
```
ibmcloud cfee org-create org_example --env env_example
```
{: codeblock}

Create a CFEE org `org_example` with quota `quote_example`:
```
ibmcloud cfee org org-create org_example --quota quota_example
```
{: codeblock}

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Delete an org:
```
ibmcloud cfee org-delete ORG [-f, --force] [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization to be deleted.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
   <dt>-f, --force</dt>
   <dd>Force deletion without confirmation.</dd>
  </dl>

<strong>Examples</strong>:

Delete a CFEE org `org_example`:
```
ibmcloud cfee org-delete org_example
```
{: codeblock}

Delete a CFEE org `org_example` of CFEE environment `env_example`:
```
ibmcloud cfee org-delete org_example --env env_example
```
{: codeblock}

Delete a CFEE org `org_example` without confirmation:
```
ibmcloud cfee org org-delete org_example -f
```
{: codeblock}

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Display users in specified organization by role:
```
ibmcloud cfee org-users ORG [-a, --all] [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>-a, --all</dt>
   <dd>List all users in the specified org.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Display users in CFEE org `org_example`:
```
ibmcloud cfee org-users org_example
```
{: codeblock}

Display users in CFEE org `org_example` of CFEE environment `env_example`:
```
ibmcloud cfee org-users org_example --env env_example
```
{: codeblock}

List all users in CFEE org `org_example`:
```
ibmcloud cfee org-users org_example -a
```
{: codeblock}

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

Assign an org role to a user (org manager required):
```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user to be assigned.</dd>
   <dt>ORG (required)</dt>
   <dd>The name of the organization this user is assigned to.</dd>
   <dt>ROLE (required)</dt>
   <dd>The name of the organization role this user is assigned to. For example:
   <ul>
   <li>OrgManager: This role can invite and manage users, select and change plans, and set spending limits.</li>
   <li>BillingManager: This role can create and manage the billing account and payment information.</li>
   <li>OrgAuditor: This role has read-only access to org information and reports.</li>
   </ul>
   </dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Assign role `BillingManager` to user `test@exmaple.com` in org `org_example`:
```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```
{: codeblock}

Assign role `BillingManager` to user `test@exmaple.com` in org `org_example` of CFEE environment `env_example`:
```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Remove an org role from a user (org manager or user only):
```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user to be removed.</dd>
   <dt>ORG (required)</dt>
   <dd>The name of the organization this user is removed from.</dd>
   <dt>ROLE (required)</dt>
   <dd>The name of the organization role this user is removed from. For example:
   <ul>
   <li>OrgManager: This role can invite and manage users, select and change plans, and set spending limits.</li>
   <li>BillingManager: This role can create and manage the billing account and payment information.</li>
   <li>OrgAuditor: This role has read-only access to org information and reports.</li>
   </ul>
   </dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Remove role `BillingManager` of user `test@exmaple.com` from org `org_example`:
```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```
{: codeblock}

Remove role `BillingManager` of user `test@exmaple.com` from org `org_example` of CFEE environment `env_example`:
```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

List all spaces:
```
ibmcloud cfee spaces [-o,--org ORG] [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Defaults to the current organization if not specified.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

List all spaces:
```
ibmcloud cfee spaces
```
{: codeblock}

List all spaces of org `org_example` and CFEE environment `env_example`
```
ibmcloud cfee spaces -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

Show the info of specified space:
```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>SPACE (required)</dt>
   <dd>Name of space to be shown.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
   <dt>--guid</dt>
   <dd>Retrieve and display the space's guid. All other output for the space is suppressed.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Defaults to the current organization if not specified.</dd>
   <dt>--security-group-rules</dt>
   <dd>Retrieve the rules for all the security groups associated with the space.</dd>
  </dl>

<strong>Examples</strong>:

Show details for a space that is named `space_example`:
```
ibmcloud cfee space space_example
```
{: codeblock}

Retrieve and display the guid of space `space_example`:
```
ibmcloud cfee space space_example --guid
```
{: codeblock}

Show the rules for all the security groups associated with space `space_example`:
```
ibmcloud cfee space space_example --security-group-rules
```
{: codeblock}

Show details for space `space_example`, and of org `org_example`, and CFEE environment `env_example`:
```
ibmcloud cfee space space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Create a space:
```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>SPACE (required)</dt>
   <dd>Name of space to be created.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Defaults to the current organization if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Create a space that is named `space_example`:
```
ibmcloud cfee space-create space_example
```
{: codeblock}

Create a space that is named `space_example`, under the org `org_example`, and in the CFEE environment `env_example`:
```
ibmcloud cfee space-create space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Rename a space:
```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>OLD_NAME (required)</dt>
   <dd>The old name of the space that is to be renamed.</dd>
   <dt>NEW_NAME (required)</dt>
   <dd>The new name of the space that it is to be renamed to.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Defaults to the current organization if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Rename space `space_example` to `new_pace_example`:
```
ibmcloud cfee space-rename space_example new_pace_example
```
{: codeblock}

Rename space `space_example` to `new_pace_example` under org `org_example` and CFEE environment `env_example`:
```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Delete a space:
```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>SPACE (required)</dt>
   <dd>Name of space to be deleted.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
   <dt>-f, --force</dt>
   <dd>Force deletion without confirmation.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Organization name. Defaults to the current organization if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Delete space `space_example`:
```
ibmcloud cfee space-delete space_example
```
{: codeblock}

Delete space `space_example` under org `org_example` and CFEE environment `env_example` without confirmation:
```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

Assign a space role to a user:
```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user to be assigned.</dd>
   <dt>ORG (required)</dt>
   <dd>The name of the organization this user is assigned to.</dd>
   <dt>SPACE (required)</dt>
   <dd>The name of the space this user is assigned to.</dd>
   <dt>ROLE (required)</dt>
   <dd>The name of the space role this user is assigned to. For example:
   <ul>
   <li>SpaceManager: This role can invite and manage users, and enable features for a space.</li>
   <li>SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.</li>
   <li>SpaceAuditor: This role can view logs, reports, and settings for the space.</li>
   </ul></dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Assign user `test@exmaple.com` to org `org_example` and space `space_example` as `SpaceManager` role:
```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```
{: codeblock}

Assign user `test@exmaple.com` to org `org_example` and space `space_example` as `SpaceManager` role under environment `env_example`:
```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

Remove a space role from a user:
```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>USER_EMAIL (required)</dt>
   <dd>The email of the user to be removed.</dd>
   <dt>ORG (required)</dt>
   <dd>The name of the organization this user is removed from.</dd>
   <dt>SPACE (required)</dt>
   <dd>The name of the space this user is removed from.</dd>
   <dt>ROLE (required)</dt>
   <dd>The name of the space role this user is removed from. For example:
   <ul>
   <li>SpaceManager: This role can invite and manage users, and enable features for a space.</li>
   <li>SpaceDeveloper: This role can create and manage apps and services, and see logs and reports.</li>
   <li>SpaceAuditor: This role can view logs, reports, and settings for the space.</li>
   </ul></dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Remove user `test@exmaple.com` to org `org_example` and space `space_example` as `SpaceManager` role:
```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```
{: codeblock}

Remove user `test@exmaple.com` to org `org_example` and space `space_example` as `SpaceManager` role under environment `env_example`:
```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

Get all space roles of current user under specific org:
```
ibmcloud cfee space-roles ORG [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Get all space roles of current user under org `org_example`:
```
ibmcloud cfee space-roles org_example
```
{: codeblock}

Get all space roles of current user under org `org_example` and environment `env_example`:
```
ibmcloud cfee space-roles org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

Display users in specified space by role:
```
ibmcloud cfee space-users ORG SPACE [--env NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>ORG (required)</dt>
   <dd>The name of the organization.</dd>
   <dt>SPACE (required)</dt>
   <dd>The name of the space.</dd>
   <dt>--env NAME</dt>
   <dd>The CFEE environment name. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

<strong>Examples</strong>:

Display all users in space `space_example` and org `org_example`:
```
ibmcloud cfee space-users org_example space_example
```
{: codeblock}

Display all users in space `space_example` and org `org_example` and environment `env_example`:
```
ibmcloud cfee space-users org_example space_example --env env_example
```
{: codeblock}

## ibmcloud cfee create
{: #ibmcloud_cfee_create}

Make a request to create an instance of Cloud Foundry Enterprise Environment:
```
ibmcloud cfee create [-n, --name NAME] [--location LOCATION] [--cells CELLS] [--virtual-dedicated-hardware] [--private-access] [--private-vlan ID, --public-vlan ID] [--plan ID] [-c PARAMETERS_AS_JSON]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
  <dt>-n, --name NAME (required)</dt>
  <dd>Specify the name of the CFEE. The name must be 24 or fewer characters, begin with a letter, and contain only alphanumeric characters, `-`, `_` and `.`.</dd>
  <dt>--location LOCATION (required)</dt>
  <dd>Specify the data center to provision this CFEE into (for example, dal10). To find available data centers, run `ibmcloud cfee create-locations`.</dd>
  <dt>--cells CELLS</dt>
  <dd>Specify the number of cells for this CFEE. The default is 2, and minimum is 1. In a one cell CFEE, there can't be high availability.</dd>
  <dt>--private-access</dt>
  <dd>Specific the network access type for the PostgreSQL database that is provisioned as part of CFEE. Only set flag if account is VRF and Service Endpoint enabled. If this flag is set, the private access endpoint is used.</dd>
  <dt>--virtual-dedicated-hardware</dt>
  <dd>With dedicated hardware, your worker nodes are hosted on infrastructure that is devoted to your account. With shared hardware, infrastructure resources, such as the hypervisor and physical hardware, are shared with other IBM customers, but each worker node is single-tenant to you. `Shared` is the default if the flag is NOT set. Using a `dedicated` worker has extra costs.</dd>
  <dt>--private-vlan ID</dt>
  <dd>Specify ID of private VLAN. By default, an available set of VLANs is used or a pair is created for you.</dd>
  <dt>--public-vlan ID</dt>
  <dd>Specify ID of public VLAN. By default, an available set of VLANs is used, or a pair is created for you.</dd>
  <dt>--plan ID</dt>
  <dd>Specify ID of plan. By default, a Standard plan is used.</dd>
  <dt>-c PARAMETERS_AS_JSON</dt>
  <dd>Valid JSON object that contains api-specific configuration parameters, provided either inline or in a file. For a list of supported configuration parameters, see the [Provision new CFEE environment](/apidocs/cfaas#provision-new-cfee-environment) API docs for the particular catalog entry. This optoin is necessary for provisioning multi-zone CFEEs. Note: All other flags are ignored, and the fields resource_group_id, access_token, and refresh_token are handled by the CLI command.</dd>
</dl>

<strong>Examples</strong>:

Create an instance named `test-cfee` in `dal10`:
```
ibmcloud cfee create test-cfee dal10
```
{: codeblock}

Create a `dedicated` instance named `test-cfee` in `dal10` with `4` cells:
```
ibmcloud cfee create test-cfee dal10 --cells 4 --isolation dedicated
```
{: codeblock}

## ibmcloud cfee create-locations
{: #ibmcloud_cfee_create_locations}

Make request to get a list of available data centers for the targeted regions:
```
ibmcloud cfee create-locations
```
{: codeblock}

<strong>Prerequisites</strong>:  Endpoint, Login

## ibmcloud cfee create-permission-get
{: #ibmcloud_cfee_create_permission_get}

Check whether a user has all the permissions that are required to create a CFEE instance. The command checks the following access policies for the target user: Editor to the CFEE services, administrator role to the Kubernetes Service, editor for the platform role and manager for the service access role to the Cloud Object Storage service, and developer role to the current space in the current org for provisioning Compose for PostgreSQL

```
ibmcloud cfee create-permission-get USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
  <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>The name of the access group to check. The default access group is `cfee-provision-access-group`.</dd>
  </dl>
  
<strong>Examples</strong>:

Check that CFEE creates permissions for the user `name@example.com`:
```
ibmcloud cfee create-permission-get name@example.com
```
{: codeblock}

Check that CFEE creates permissions for the user `name@example.com`, and in access group `test-access-group`:
```
ibmcloud cfee create-permission-get name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-permission-set
{: #ibmcloud_cfee_create_permission_set}

Give user all the permissions required to create a CFEE instance. The command creates the following access policies for the target user:  Editor role to the CFEE service, administrator role to the Kubernetes service, editor for the platform role and manager for the service access role to the Cloud Object Storage service, and developer role to the current space in the current org for provisioning Compose for PostgreSQL

```
ibmcloud cfee create-permission-set USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>Prerequisites</strong>:  Endpoint, Login, Target

<strong>Command options</strong>:
  <dl>
   <dt>USER_NAME (required)</dt>
   <dd>The name of the user.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>The name of the access group to give permissions in. The default access group is `cfee-provision-access-group`.</dd>
  </dl>
  
<strong>Examples</strong>:

Give CFEE create permissions to user `name@example.com` through the default access group:
```
ibmcloud cfee create-permission-set name@example.com
```
{: codeblock}

Give CFEE create permissions to user `name@example.com` through access group `test-access-group`:
```
ibmcloud cfee create-permission-set name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-status
{: #ibmcloud_cfee_create_status}

Check the provisioning status of a CFEE instance:
```
ibmcloud cfee create-status NAME or ID [--poll]
```
{: codeblock}

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>NAME or ID (required)</dt>
   <dd>The name or ID of the CFEE instance.</dd>
   <dt>--poll</dt>
   <dd>Specify whether to make this call recurring, which polls until in a stable state.</dd>
  </dl>
   
## ibmcloud cfee delete
{: #ibmcloud_cfee_delete}

Deletes a particular CFEE environment:
```
ibmcloud cfee delete --env {Name|ID} [-f, --force]
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env NAME or ID</dt>
   <dd>Specify an environment to check by name or ID.</dd>
   <dt>-f, --force</dt>
   <dd>Force CFEE delete without confirmation. Use with caution.</dd>
  </dl>
<strong>Examples</strong>:

Delete the `env_example` CFEE environment, confirming before the environment is deleted:
```
ibmcloud cfee delete --env env_example
```
{: codeblock}

Delete the `env_example` CFEE environment without requiring confirmation:
```
ibmcloud cfee delete --env env_example --force
```
{: codeblock}

## ibmcloud cfee monitoring-enable
{: #ibmcloud_cfee_monitoring-enable}

Enable monitoring on the targeted CFEE environment:
```
ibmcloud cfee monitoring-enable
```
{: codeblock}

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
  </dl>

## ibmcloud cfee monitoring-disable
{: #ibmcloud_cfee_monitoring-disable}

Disable monitoring on the targeted CFEE environment:
```
ibmcloud cfee monitoring-disable
```
{: codeblock}

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
  </dl>

## ibmcloud cfee monitoring-status
{: #ibmcloud_cfee_monitoring-status}

Check the status of the most recent monitoring (enablement or disablement) operation in the targeted CFEE environment:
```
ibmcloud cfee monitoring-status [--poll]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--poll</dt>
   <dd>Specify whether to make this call recurring, which polls until in a stable state</dd>
  </dl>

## ibmcloud cfee status
{: #ibmcloud_cfee_status}

Check the status of a CFEE instance:
```
ibmcloud cfee status {NAME|ID} [--poll]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>NAME or ID (required)</dt>
   <dd>The name or ID of the CFEE instance.</dd>
   <dt>--poll</dt>
   <dd>Specify whether to make this call recurring, which polls until in a stable state.</dd>
  </dl>

<strong>Examples</strong>:

Get the status of CFEE environment `env_example`:
```
ibmcloud cfee status env_example
```
{: codeblock}

Get the status of CFEE environment `env_example` in JSON format:
```
ibmcloud cfee status env_example --output json
```
{: codeblock}

Poll the status of CFEE environment `env_example`:
```
ibmcloud cfee status env_example --poll
```
{: codeblock}

## ibmcloud cfee version
{: #ibmcloud_cfee_version}

Get the version of an environment, or get the latest available CFEE version:
```
ibmcloud cfee version [--env {NAME|ID} | --latest] [--details]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env NAME or ID</dt>
   <dd>The CFEE environment name or ID. Defaults to the current CFEE environment if not specified.</dd>
  </dl>
  <dl>
   <dt>--latest</dt>
   <dd>Specify to find the latest CFEE version available.</dd>
  </dl>
  <dl>
   <dt>--details</dt>
   <dd>Specify if you want CFEE package version information to be included in the output.</dd>
  </dl>
  <dl>
  </dl>

<strong>Examples</strong>:

Get version information for the currently targeted CFEE environment:
```
ibmcloud cfee version
```
{: codeblock}

Get version information with package details for the currently targeted CFEE environment:
```
ibmcloud cfee version --details
```
{: codeblock}

Get version information with package details for the currently targeted CFEE environment in JSON format:
```
ibmcloud cfee version --details --output json
```
{: codeblock}

Get version information with package details for the CFEE environment `env_example` in JSON format:
```
ibmcloud cfee version --env env_example --details --output json
```
{: codeblock}

Get the latest available CFEE version information with details:
```
ibmcloud cfee version --latest --details
```
{: codeblock}

## ibmcloud cfee update
{: #ibmcloud_cfee_update}

Check or initiate a CFEE environment update to the next available version of CFEE:
```
ibmcloud cfee update --env {NAME|ID} [-f, --force] [--dryrun]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env NAME or ID</dt>
   <dd>Specify an environment to check by name or ID.</dd>
  </dl>
  <dl>
   <dt>-f or --force</dt>
   <dd>Force CFEE to update without confirmation. Use with caution.</dd>
  </dl>
  <dl>
   <dt>--dryrun</dt>
   <dd>Check if the update is possible and display actions to be taken based on current and target CFEE versions. No actual update is initiated.</dd>
  </dl>

<strong>Examples</strong>:

Initiate the update of the CFEE environment `env_example`. The user must confirm before the update is initiated:
```
ibmcloud cfee update --env env_example
```
{: codeblock}

Initiate the update of the CFEE environment `env_example` without requiring user confirmation:
```
ibmcloud cfee update --env env_example --force
```
{: codeblock}

Perform a dry-run initiation of the update of the CFEE environment `env_example`:
```
ibmcloud cfee update --env env_example --dryrun
```
{: codeblock}

## ibmcloud cfee show-alert-manager-config
{: #ibmcloud_cfee_show-alert-manager-config}

Get the Prometheus Alertmanager configuration for a CFEE environment:
```
ibmcloud cfee show-alert-manager-config [--env {NAME|ID}]
```
{: codeblock}

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env Name or ID</dt>
   <dd>The CFEE environment name or ID. Defaults to the current CFEE environment if not specified.</dd>
  </dl>

## ibmcloud cfee logging-enable
{: #ibmcloud_cfee_logging-enable}

Enable logging on a CFEE environment by using the {{site.data.keyword.la_full_notm}} service:
```
ibmcloud cfee logging-enable --service-guid SERVICE_GUID [--env {NAME|ID}]
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env Name or ID</dt>
   <dd>The CFEE environment name or ID. Defaults to the current CFEE environment if not specified.</dd>
   <dt>--service-guid</dt>
   <dd>Specify the GUID of your {{site.data.keyword.la_short}} instance. You can find this value by running `ibmcloud resource service-instance SERVICE_NAME`.</dd>
  </dl>
  
<strong>Examples</strong>:

Enable logging for the currently targeted CFEE environment by using the {{site.data.keyword.la_short}} instance's GUID:
```
ibmcloud cfee logging-enable --service-guid ab123456-12ab-1234-a1b1-ab123c123456
```
{: codeblock}

Enable logging for CFEE environment `env_example` by using the {{site.data.keyword.la_short}} instance's GUID:
```
ibmcloud cfee logging-enable --env example_env --service-guid ab123456-12ab-1234-a1b1-ab123c123456
```
{: codeblock}
  

## ibmcloud cfee logging-disable
{: #ibmcloud_cfee_logging-disable}

Disable logging with {{site.data.keyword.la_short}} on the targeted CFEE environment:
```
ibmcloud cfee logging-disable [--env {NAME|ID}]
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env Name or ID</dt>
   <dd>The CFEE environment name or ID. Defaults to the current CFEE environment if not specified.</dd>
  </dl>
  
## ibmcloud cfee logging-status
{: #ibmcloud_cfee_logging-status}

Check the status of the most recent logging enablement or disablement operation on a CFEE environment:
```
ibmcloud cfee logging-status [--env {NAME|ID}]
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env Name or ID</dt>
   <dd>The CFEE environment name or ID. Defaults to the current CFEE environment if not specified.</dd>
  </dl>
  
  <strong>Examples</strong>:
  
Get logging status for the currently targeted CFEE environment:
```
ibmcloud cfee logging-status
```
{: codeblock}

Get logging status for CFEE environment `env_example` in JSON format:
```
ibmcloud cfee logging-status --env env_example --output json
```
{: codeblock}

## ibmcloud cfee auditing-enable
{: #ibmcloud_cfee_auditing-enable}

Enable auditing on a CFEE environment by using events from the {{site.data.keyword.at_full_notm}} service:
```
ibmcloud cfee auditing-enable --service-guid SERVICE_GUID --ingestion-key KEY [--env {NAME|ID}]
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env Name or ID</dt>
   <dd>The CFEE environment name or ID. Defaults to the current CFEE environment if not specified.</dd>
   <dt>--service-guid SERVICE_GUID</dt>
   <dd>Specify the GUID of your {{site.data.keyword.at_short}} instance. You can find this value by running `ibmcloud resource service-instance SERVICE_NAME`.</dd>
   <dt>--ingestion-key KEY</dt>
   <dd>The ingestion key of your {{site.data.keyword.at_short}} instance. You can find this value in the {{site.data.keyword.at_short}} dashboard by going to **Settings > Organization > API Keys**.></dd>
  </dl>
  
  <strong>Examples</strong>:

Enable auditing for the currently targeted CFEE environment by using the {{site.data.keyword.at_short}} instance's GUID and ingestion key:
```
ibmcloud cfee auditing-enable --service-guid ab123456-12ab-1234-a1b1-ab123c123456 --ingestion-key 123456abc123456
```
{: codeblock}

Enable auditing for CFEE environment `env_example` by using the {{site.data.keyword.at_short}} instance's GUID and ingestion key:
```
ibmcloud cfee auditing-enable --env example_env --service-guid ab123456-12ab-1234-a1b1-ab123c123456 --ingestion-key 123456abc123456
```
{: codeblock}

## ibmcloud cfee auditing-disable
{: #ibmcloud_cfee_auditing-disable}

Disable {{site.data.keyword.at_short}} auditing on a CFEE environment:
```
ibmcloud cfee auditing-disable [--env {NAME|ID}]
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env Name or ID</dt>
   <dd>The CFEE environment name or ID. Defaults to the current CFEE environment if not specified.</dd>
  </dl>
  
## ibmcloud cfee auditing-status
{: #ibmcloud_cfee_auditing-status}

Get the {{site.data.keyword.at_short}} auditing configuration for a CFEE environment:
```
ibmcloud cfee auditing-status [--env {NAME|ID}]
```
<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--env Name or ID</dt>
   <dd>The CFEE environment name or ID. Defaults to the current CFEE environment if not specified.</dd>
  </dl>
  
<strong>Examples</strong>:

Get auditing status for the currently targeted CFEE environment:
```
ibmcloud cfee auditing-status
```
{: codeblock}

Get auditing status for CFEE environment `env_example` in JSON format:
```
ibmcloud cfee auditing-status --env env_example --output json
```
{: codeblock}
