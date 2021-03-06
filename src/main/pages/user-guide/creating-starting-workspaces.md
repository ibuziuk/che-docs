---
title: "Workspace Management"
keywords: workspace, runtime, recipe, docker, yaml, Dockerfile, docker, kubernetes, container, pod
tags: [workspace, runtime, docker, kubernetes]
sidebar: user_sidebar
permalink: creating-starting-workspaces.html
folder: user-guide
---

{% include links.html %}


## Creating Workspaces

The easiest way to create a workspace is to use ready to go [stacks][stacks] in User Dashboard. Images and configuration in these stacks is certified both for Docker and OpenShift, and these are the stacks that are used in daily functional testing. There are multiple options though, namely:

**Ready-to-go Stacks**
{% include image.html file="workspaces/ready_to_go_stacks.gif" %}

**Duplicate an existing stack**

In this scenario, you need to create a stack first, and then use the resulting stack to create a workspace.

{% include image.html file="workspaces/duplicate_stack.gif" %}

**Create Custom stack from a custom [recipe][recipes]**

In this scenario, you need to author a custom [recipe][recipes], then a stack, and finally use the resulting stack to create a workspace.

{% include image.html file="workspaces/custom_recipe_stack.gif" %}

## Starting Workspaces

A workspace can be started in one of the following ways:

1. Auto-start when workspace is created in UD
2. Run or Open buttons in workspace details view in User Dashboard
3. By clicking on a workspace name in the left Dashboard sidebar (recent workspaces)
4. Using REST API. See [REST API][TODO: REST API page]

It can take some time for a workspace environment to start. It depends on several factors like network conditions, Docker image availability, configured installers that may attempt to install additional tools and software in runtime etc. When a workspace is starting, you can track progress in a workspace start tab. There are also individual tabs for each machine in workspace environment that stream logs from installers (terminal, exec agent, ws agent, language servers if any).

## Workspace Management

Once a workspace is created or started, you can modify it by adding [projects][projects], [installers][installers], [env variables][env-variables], [volumes][volumes]. You can also edit raw workspace config, but beware that you may break your workspace this way, so always have a backup of a working config. If you change configuration of a running workspace and save it, a workspace will be restarted. Follow the links above to learn more about workspace configuration.

{% include image.html file="workspaces/ws_details.gif" %}
