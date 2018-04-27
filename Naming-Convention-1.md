# Naming Convention 1

Here's a way to name pipes and systems that a lot of projects use. If you follow a naming convention you make it easier to switch between projects.

## General rules
- lower case
- dash `-` as delimiter

## Systems
- name after the name of the service you integrate with, not the technology used (e.g. `salesforce` instead of `mysql`)
- if multiple systems are required to talk to a system postfix them with a qualifier (e.g. `salesforce-out`)

## Pipes
- name input pipes with system they read from and postfix with the type of content (e.g. `salesforce-sale`) 
- do not use plural names (e.g. `salesforce-sale` not `salesforce-sales`)
- prefix merge pipes with `merged-` (e.g. `merged-sale`)
- prefix global pipes with `global-` (e.g. `global-sale`)
- name intermediate output pipe with the type of the content and the name of the system to send to (`e.g. `sale-bigquery`
- name outgoing pipe by postfixing the intermediate output with `-endpoint` (`e.g. `sale-bigquery-endpoint`)

## Datasets
- name them the same as the pipe that produced it (the default)