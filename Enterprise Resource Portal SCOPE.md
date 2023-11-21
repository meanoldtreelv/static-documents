
# Enterprise Resource Portal Usability Scope

## Overview
Z-Telco has chosen the Odoo platform to serve as its Enterprise Resource Portal and Source Of Truth. The Odoo platform will serve as a basis for all company business process and be extended as needed by 3rd party applications. 

The following functions have been identified as a core need for Odoo and will be detailed in the sections below:

### CRM
The Company needs to keep detailed information about prospective, current, and past customers. The CRM should be the central data source for the "Customer Object" and all related Data. The Customer Object should exist in a one to many relationship with objects created in the Sales Pipeline, Projects Pipeline, and After Sales module. 

### Sales Pipeline
The Sales Pipeline should be handled entirely within a single module, supporting the transition of a contact from a Lead to a Customer, along with supporting Sales Order Data. This includes the creation of Opportunities during prospecting; the preparation, submission, and confirmation of formal quotations; the creation, submission, and confirmation of binding sales orders; the creation, submission, and confirmation of binding contract documentation. 

### After Sales
The After Sales module should provide for the servicing of the customers account once they have completed the Sales Pipeline. This includes the handling of support tickets created via phone, email, or 3rd party integration. 

### Invoicing
As The Company has spent significant resources on the development of its Zoura platform, it is not ideal at this time to use the Invoicing module to interact directly with customers. It is however needed to form a link between the Sales Pipeline and Zoura, as well as to make data generated from within Zoura accessable to Platform Users

### Projects Pipeline
On completion of the Sales Pipeline, dependent on product sold, A project and associated tasks must be created to allow our Implementation teams the ability to move the customer forward from a signed contract to receiving service.  The Projects Pipeline offers us a large opportunity for the automation of our existing business processes as with additional LOBs coming online we will be seeing customers completing their onboarding via Self Service. The Projects Pipeline is to serve as a record of all operations performed for a customer between the completion of the Sales Pipeline until the activation of the customers service. 

### Inventory
The company maintains physical inventory in a self-managed warehouse, as well as has the ability to handle physical inventory via 3PL partners. All saleable items purchased by The Company should be tracked in this Inventory System. 

### HR
The company wishes to gain more control over its HR documentation, timesheets, and training. To facilitate this The Company will be utilizing the TimeSheets, Employee, Expense, Time-Off, and E-Learning modules to form the basis of a new Employee Management System. 

## Technical Overview

### Planned Deployment:
The ERP and associated tools should be deployed as an interconnected collection of docker images (a "stack") on the multi-datacenter Internal Services Docker Swarm Cluster.  The Odoo interface is to be decoupled from its database and be independently scalable. The Odoo installation should operate in a **stateless** manner as multiple replicas of the interface may be accessing the database at any given time. 

In addition to Odoo and its corresponding database a standalone version of our API Automation Platform (N8N) is to be deployed alongside to facilitate chronological applications and serve as the connector between Odoo and other services. 

Additional 3rd Party tools which extend the functionality of Odoo will be included in this stack as well such as AppSmith, ToolJet, Grafana, Grist, etc. 

### Current Deployment:

Currently the Odoo Platform is deployed to production as a single VM. This **IS NOT** sustainable for production use and should be rectified at the earliest point. However we understand that there are chronological based events currently built into the Odoo system which prevent scaling to a multi-node cluster. These items will need to be addressed and migrated to the API Automation Platform individually before Containerization and Scaling can occur. 


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIzNTQ4MzI3NV19
-->