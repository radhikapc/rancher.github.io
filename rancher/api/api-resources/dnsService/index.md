---
title: API
layout: rancher-default
---

## dnsService

A "dnsService" in the API is referred to as a Service Alias in the UI and the Rancher documentation. In the API documentation, we'll use the UI terminology. A service alias allows the ability to add a DNS record for your services to be discovered.

​
### Resource Fields

Field | Type | Create | Update | Default | Notes
---|---|---|---|---|---
description | string | Optional | Yes | - | 
environmentId | [environment]({{site.baseurl}}/rancher/api/api-resources/environment/) | Yes | - | - | The identifier of which stack the service belongs to
externalId | string | - | - | - | 
fqdn | string | - | - | - | The fqdn of a service when the [Route 53 DNS service]({{site.baseurl}}/rancher/rancher-services/dns-service/) has started. The format will be `<serviceName>.<stackName>.<environmentName>.<yourHostedZoneName>`.
id | int | - | - | - | The unique identifier for the dnsService
launchConfig | [launchConfig]({{site.baseurl}}/rancher/api/api-resources/launchConfig/) | Optional | - | - | The Docker run configuration of a container
metadata | map[json] | Optional | Yes | - | The user added [metadata]({{site.baseurl}}/rancher/metadata-service/#adding-user-metadata-to-a-service) to a service.
name | string | Yes | Yes | - | 
selectorLink | string | Optional | - | - | The [selector value]({{site.baseurl}}/rancher/labels/#selector-labels) used to select a [service]({{site.baseurl}}/rancher/api/api-resources/service/) to link to the service based on a service's labels.
upgrade | [serviceUpgrade]({{site.baseurl}}/rancher/api/api-resources/serviceUpgrade/) | - | - | - | 

<br>
Please read more about the [common resource fields]({{site.baseurl}}/rancher/api/common/). 
These fields are read only and applicable to almost every resource. We have segregated them from the list above.
​

### Operations



<span class="action">
<span class="header">
Create
<span class="headerright">POST:  <code>/v1/dnsService</code></span>
</span>
<div class="action-contents">
{% highlight json %} 
{

	"description": "string",

	"environmentId": "reference[environment]",

	"launchConfig": {

		"accountId": "reference[account]",

		"build": {

			"context": "string",

			"dockerfile": "string",

			"forcerm": true,

			"nocache": true,

			"remote": "string",

			"rm": true

		},

		"capAdd": "array[enum]",

		"capDrop": "array[enum]",

		"command": [

			"string1",

			"string2",

			"...stringN"

		],

		"count": 0,

		"cpuSet": "string",

		"cpuShares": 0,

		"createIndex": 0,

		"created": "date",

		"dataVolumeMounts": "map[reference[volume]]",

		"dataVolumes": [

			"string1",

			"string2",

			"...stringN"

		],

		"dataVolumesFrom": "array[reference[container]]",

		"dataVolumesFromLaunchConfigs": [

			"string1",

			"string2",

			"...stringN"

		],

		"deploymentUnitUuid": "string",

		"description": "string",

		"devices": [

			"string1",

			"string2",

			"...stringN"

		],

		"dns": [

			"string1",

			"string2",

			"...stringN"

		],

		"dnsSearch": [

			"string1",

			"string2",

			"...stringN"

		],

		"domainName": "string",

		"entryPoint": [

			"string1",

			"string2",

			"...stringN"

		],

		"environment": {

			"key1": "value1",

			"key2": "value2",

			"keyN": "valueN"

		},

		"expose": [

			"string1",

			"string2",

			"...stringN"

		],

		"externalId": "string",

		"extraHosts": [

			"string1",

			"string2",

			"...stringN"

		],

		"firstRunning": "date",

		"healthCheck": {

			"healthyThreshold": 0,

			"interval": 0,

			"name": "string",

			"port": 0,

			"requestLine": "string",

			"responseTimeout": 0,

			"unhealthyThreshold": 0

		},

		"healthState": "enum",

		"hostname": "string",

		"id": 0,

		"imageUuid": "string",

		"instanceLinks": "map[reference[instance]]",

		"kind": "string",

		"labels": {

			"key1": "value1",

			"key2": "value2",

			"keyN": "valueN"

		},

		"logConfig": {

			"config": {

				"key1": "value1",

				"key2": "value2",

				"keyN": "valueN"

			},

			"driver": "string"

		},

		"lxcConf": {

			"key1": "value1",

			"key2": "value2",

			"keyN": "valueN"

		},

		"memory": 0,

		"memorySwap": 0,

		"nativeContainer": true,

		"networkContainerId": "reference[container]",

		"networkIds": "array[reference[network]]",

		"networkLaunchConfig": "string",

		"networkMode": "managed",

		"pidMode": "enum",

		"ports": [

			"string1",

			"string2",

			"...stringN"

		],

		"primaryIpAddress": "string",

		"privileged": false,

		"publishAllPorts": false,

		"readOnly": false,

		"registryCredentialId": "reference[registryCredential]",

		"removed": "date",

		"requestedHostId": "reference[host]",

		"securityOpt": [

			"string1",

			"string2",

			"...stringN"

		],

		"startCount": 0,

		"startOnCreate": true,

		"state": "enum",

		"stdinOpen": false,

		"systemContainer": "enum",

		"transitioning": "enum",

		"transitioningMessage": "string",

		"transitioningProgress": 0,

		"tty": false,

		"user": "string",

		"uuid": "string",

		"version": "0",

		"volumeDriver": "string",

		"workingDir": "string"

	},

	"metadata": "map[json]",

	"name": "string",

	"selectorLink": "string"

} 
{% endhighlight %}
</div>
</span>













<span class="action">
<span class="header">
Update
<span class="headerright">PUT:  <code>${links.self}</code></span>
</span>
<div class="action-contents">
{% highlight json %} 
{

	"description": "string",

	"metadata": "map[json]",

	"name": "string"

} 
{% endhighlight %}
</div>
</span>







<span class="action">
<span class="header">
Delete
<span class="headerright">DELETE:  <code>${links.self}</code></span>
</span>
<div class="action-contents">
{% highlight json %} 
 
{% endhighlight %}
</div>
</span>






​
### Actions

<span class="action">
<span class="header">
activate
<span class="headerright">POST:  <code>${actions.activate}</code></span>
</span>
<div class="action-contents">
To activate the dnsService
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
addservicelink
<span class="headerright">POST:  <code>${actions.addservicelink}</code></span>
</span>
<div class="action-contents">
To addservicelink the dnsService
<br>

<span class="input">
<strong>Input:</strong>​​​ addRemoveServiceLinkInput


Field | Type | Required | Default | Notes
---|---|---|---|---
serviceLink | serviceLink | Yes | <no value> | 


<br>
{% highlight json %}{

	"serviceLink": {

		"name": "string",

		"serviceId": "reference[service]"

	}

}{% endhighlight %}

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
cancelrollback
<span class="headerright">POST:  <code>${actions.cancelrollback}</code></span>
</span>
<div class="action-contents">
To cancelrollback the dnsService
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
cancelupgrade
<span class="headerright">POST:  <code>${actions.cancelupgrade}</code></span>
</span>
<div class="action-contents">
To cancelupgrade the dnsService
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
deactivate
<span class="headerright">POST:  <code>${actions.deactivate}</code></span>
</span>
<div class="action-contents">
To deactivate the dnsService
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
finishupgrade
<span class="headerright">POST:  <code>${actions.finishupgrade}</code></span>
</span>
<div class="action-contents">
To finishupgrade the dnsService
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
remove
<span class="headerright">POST:  <code>${actions.remove}</code></span>
</span>
<div class="action-contents">
To remove the dnsService
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
removeservicelink
<span class="headerright">POST:  <code>${actions.removeservicelink}</code></span>
</span>
<div class="action-contents">
To removeservicelink the dnsService
<br>

<span class="input">
<strong>Input:</strong>​​​ addRemoveServiceLinkInput


Field | Type | Required | Default | Notes
---|---|---|---|---
serviceLink | serviceLink | Yes | <no value> | 


<br>
{% highlight json %}{

	"serviceLink": {

		"name": "string",

		"serviceId": "reference[service]"

	}

}{% endhighlight %}

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
rollback
<span class="headerright">POST:  <code>${actions.rollback}</code></span>
</span>
<div class="action-contents">
To rollback the dnsService
<br>

<span class="input">
<strong>Input:</strong>This action has no inputs
<br>

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
setservicelinks
<span class="headerright">POST:  <code>${actions.setservicelinks}</code></span>
</span>
<div class="action-contents">
To setservicelinks the dnsService
<br>

<span class="input">
<strong>Input:</strong>​​​ setServiceLinksInput


Field | Type | Required | Default | Notes
---|---|---|---|---
serviceLinks | array[serviceLink] | No | <no value> | The list of services linked


<br>
{% highlight json %}{

	"serviceLinks": "array[serviceLink]"

}{% endhighlight %}

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

<span class="action">
<span class="header">
upgrade
<span class="headerright">POST:  <code>${actions.upgrade}</code></span>
</span>
<div class="action-contents">
To upgrade the dnsService
<br>

<span class="input">
<strong>Input:</strong>​​​ serviceUpgrade


Field | Type | Required | Default | Notes
---|---|---|---|---
inServiceStrategy | inServiceUpgradeStrategy | No | <no value> | 
toServiceStrategy | toServiceUpgradeStrategy | No | <no value> | 


<br>
{% highlight json %}{

	"inServiceStrategy": {

		"batchSize": 1,

		"intervalMillis": 2000,

		"launchConfig": {

			"accountId": "reference[account]",

			"build": {

				"context": "string",

				"dockerfile": "string",

				"forcerm": true,

				"nocache": true,

				"remote": "string",

				"rm": true

			},

			"capAdd": "array[enum]",

			"capDrop": "array[enum]",

			"command": [

				"string1",

				"string2",

				"...stringN"

			],

			"count": 0,

			"cpuSet": "string",

			"cpuShares": 0,

			"createIndex": 0,

			"created": "date",

			"dataVolumeMounts": "map[reference[volume]]",

			"dataVolumes": [

				"string1",

				"string2",

				"...stringN"

			],

			"dataVolumesFrom": "array[reference[container]]",

			"dataVolumesFromLaunchConfigs": [

				"string1",

				"string2",

				"...stringN"

			],

			"deploymentUnitUuid": "string",

			"description": "string",

			"devices": [

				"string1",

				"string2",

				"...stringN"

			],

			"dns": [

				"string1",

				"string2",

				"...stringN"

			],

			"dnsSearch": [

				"string1",

				"string2",

				"...stringN"

			],

			"domainName": "string",

			"entryPoint": [

				"string1",

				"string2",

				"...stringN"

			],

			"environment": {

				"key1": "value1",

				"key2": "value2",

				"keyN": "valueN"

			},

			"expose": [

				"string1",

				"string2",

				"...stringN"

			],

			"externalId": "string",

			"extraHosts": [

				"string1",

				"string2",

				"...stringN"

			],

			"firstRunning": "date",

			"healthCheck": {

				"healthyThreshold": 0,

				"interval": 0,

				"name": "string",

				"port": 0,

				"requestLine": "string",

				"responseTimeout": 0,

				"unhealthyThreshold": 0

			},

			"healthState": "enum",

			"hostname": "string",

			"id": 0,

			"imageUuid": "string",

			"instanceLinks": "map[reference[instance]]",

			"kind": "string",

			"labels": {

				"key1": "value1",

				"key2": "value2",

				"keyN": "valueN"

			},

			"logConfig": {

				"config": {

					"key1": "value1",

					"key2": "value2",

					"keyN": "valueN"

				},

				"driver": "string"

			},

			"lxcConf": {

				"key1": "value1",

				"key2": "value2",

				"keyN": "valueN"

			},

			"memory": 0,

			"memorySwap": 0,

			"nativeContainer": true,

			"networkContainerId": "reference[container]",

			"networkIds": "array[reference[network]]",

			"networkLaunchConfig": "string",

			"networkMode": "managed",

			"pidMode": "enum",

			"ports": [

				"string1",

				"string2",

				"...stringN"

			],

			"primaryIpAddress": "string",

			"privileged": false,

			"publishAllPorts": false,

			"readOnly": false,

			"registryCredentialId": "reference[registryCredential]",

			"removed": "date",

			"requestedHostId": "reference[host]",

			"securityOpt": [

				"string1",

				"string2",

				"...stringN"

			],

			"startCount": 0,

			"startOnCreate": true,

			"state": "enum",

			"stdinOpen": false,

			"systemContainer": "enum",

			"transitioning": "enum",

			"transitioningMessage": "string",

			"transitioningProgress": 0,

			"tty": false,

			"user": "string",

			"uuid": "string",

			"version": "0",

			"volumeDriver": "string",

			"workingDir": "string"

		},

		"previousLaunchConfig": {

			"accountId": "reference[account]",

			"build": {

				"context": "string",

				"dockerfile": "string",

				"forcerm": true,

				"nocache": true,

				"remote": "string",

				"rm": true

			},

			"capAdd": "array[enum]",

			"capDrop": "array[enum]",

			"command": [

				"string1",

				"string2",

				"...stringN"

			],

			"count": 0,

			"cpuSet": "string",

			"cpuShares": 0,

			"createIndex": 0,

			"created": "date",

			"dataVolumeMounts": "map[reference[volume]]",

			"dataVolumes": [

				"string1",

				"string2",

				"...stringN"

			],

			"dataVolumesFrom": "array[reference[container]]",

			"dataVolumesFromLaunchConfigs": [

				"string1",

				"string2",

				"...stringN"

			],

			"deploymentUnitUuid": "string",

			"description": "string",

			"devices": [

				"string1",

				"string2",

				"...stringN"

			],

			"dns": [

				"string1",

				"string2",

				"...stringN"

			],

			"dnsSearch": [

				"string1",

				"string2",

				"...stringN"

			],

			"domainName": "string",

			"entryPoint": [

				"string1",

				"string2",

				"...stringN"

			],

			"environment": {

				"key1": "value1",

				"key2": "value2",

				"keyN": "valueN"

			},

			"expose": [

				"string1",

				"string2",

				"...stringN"

			],

			"externalId": "string",

			"extraHosts": [

				"string1",

				"string2",

				"...stringN"

			],

			"firstRunning": "date",

			"healthCheck": {

				"healthyThreshold": 0,

				"interval": 0,

				"name": "string",

				"port": 0,

				"requestLine": "string",

				"responseTimeout": 0,

				"unhealthyThreshold": 0

			},

			"healthState": "enum",

			"hostname": "string",

			"id": 0,

			"imageUuid": "string",

			"instanceLinks": "map[reference[instance]]",

			"kind": "string",

			"labels": {

				"key1": "value1",

				"key2": "value2",

				"keyN": "valueN"

			},

			"logConfig": {

				"config": {

					"key1": "value1",

					"key2": "value2",

					"keyN": "valueN"

				},

				"driver": "string"

			},

			"lxcConf": {

				"key1": "value1",

				"key2": "value2",

				"keyN": "valueN"

			},

			"memory": 0,

			"memorySwap": 0,

			"nativeContainer": true,

			"networkContainerId": "reference[container]",

			"networkIds": "array[reference[network]]",

			"networkLaunchConfig": "string",

			"networkMode": "managed",

			"pidMode": "enum",

			"ports": [

				"string1",

				"string2",

				"...stringN"

			],

			"primaryIpAddress": "string",

			"privileged": false,

			"publishAllPorts": false,

			"readOnly": false,

			"registryCredentialId": "reference[registryCredential]",

			"removed": "date",

			"requestedHostId": "reference[host]",

			"securityOpt": [

				"string1",

				"string2",

				"...stringN"

			],

			"startCount": 0,

			"startOnCreate": true,

			"state": "enum",

			"stdinOpen": false,

			"systemContainer": "enum",

			"transitioning": "enum",

			"transitioningMessage": "string",

			"transitioningProgress": 0,

			"tty": false,

			"user": "string",

			"uuid": "string",

			"version": "0",

			"volumeDriver": "string",

			"workingDir": "string"

		},

		"previousSecondaryLaunchConfigs": "array[secondaryLaunchConfig]",

		"secondaryLaunchConfigs": "array[secondaryLaunchConfig]",

		"startFirst": false

	},

	"toServiceStrategy": {

		"batchSize": 1,

		"finalScale": 1,

		"intervalMillis": 2000,

		"toServiceId": "reference[service]",

		"updateLinks": true

	}

}{% endhighlight %}

<br>
</span>

<span class="output"><strong>Output:</strong> An updated copy of the <a href="/rancher/api/api-resources/service/">service</a> resource
</span>
</div>
</span>
</span>
</span>

