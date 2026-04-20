---
id: id-ra0030
slug: /ref-arch/ra0030
sidebar_position: 30
title: Boxes on SAP BTP
description: Reference architecture for containerized workloads and sandbox environments on SAP Business Technology Platform.
keywords:
  - sap
  - boxes
  - containers
  - sandbox
  - btp
  - isolation
sidebar_label: Boxes on SAP BTP
image: img/ac-soc-med.png
tags:
  - ref-arch
  - appdev
hide_table_of_contents: false
hide_title: false
toc_min_heading_level: 2
toc_max_heading_level: 4
draft: true
unlisted: false
contributors:
last_update:
  author: Julian Schambeck
  date: 2026-04-20
---

Boxes represent isolated, self-contained environments used to run workloads, experiments, or services without interference from other systems. On SAP Business Technology Platform (SAP BTP), this pattern is commonly applied to achieve clean separation of concerns, resource governance, and safe experimentation at scale.

This reference architecture describes how to design and operate box-based environments on SAP BTP, covering the key services and patterns that enable workload isolation, lifecycle management, and controlled resource sharing across teams and projects.

## Architecture

The following diagram illustrates the high-level architecture of box-based workload isolation on SAP BTP.

![drawio](drawio/solution-diagram.drawio)

Each box represents a bounded context — a runtime environment with defined inbound and outbound interfaces, dedicated resource quotas, and scoped identity and access management. Boxes can be provisioned dynamically and are designed to be short-lived or persistent depending on the use case.

## Services and Components

The following SAP BTP services are central to implementing this architecture:

- **SAP BTP, Cloud Foundry Runtime**: Provides the containerized runtime environment for deploying applications in isolated spaces with resource quotas and role-based access control.

- **SAP BTP, Kyma Runtime**: Offers Kubernetes-based workload isolation, enabling fine-grained control over compute, networking, and storage boundaries.

- **SAP Authorization and Trust Management Service**: Manages scoped access tokens and role assignments per environment, ensuring each box operates under least-privilege principles.

- **SAP BTP Cockpit**: Central control plane for provisioning, monitoring, and governing box environments across subaccounts.
