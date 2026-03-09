# AI-Driven-Autonomous-Access-Provisioning-Engine

**Overview**

This project implements an AI-driven autonomous access provisioning solution for Oracle E-Business Suite (EBS) integrated with ServiceNow.
It leverages UiPath Agentic AI and RPA automation to interpret unstructured ServiceNow access requests, determine the appropriate provisioning scenario, and automatically execute controlled access provisioning.

The solution reduces manual effort for L2 support teams by automating user creation, responsibility assignment, cloning, and approval workflows.


**Problem Statement :**

L2 Access Management teams manually interpret ServiceNow tickets to provision access in Oracle EBS.

**Challenges include:**

Access requests are written in unstructured free-text

Multiple provisioning scenarios increase complexity

Manual validation of users and responsibilities

Approval follow-ups delay request completion

Risk of duplicate users or incorrect access assignment

High dependency on SME knowledge for role mapping

This results in higher turnaround time, operational overhead, and governance risks.


**Solution:**

The Autonomous Access Provisioning Engine uses AI agents + UiPath automation to:

Interpret ServiceNow ticket descriptions

Identify provisioning scenarios

Extract key entities (user, responsibilities, dates)

Recommend role assignments when not provided

Trigger multi-level approvals

Execute provisioning actions in Oracle EBS

Maintain compliance and audit traceability

Key Features
AI-Driven Ticket Interpretation

AI agents analyze ServiceNow ticket descriptions to determine the request type.

Dynamic Role Recommendation

If responsibilities are not provided in the ticket, the system recommends access using predefined role mappings.

Automated Approval Workflow

Supports automated routing for:

Manager Approval

BPO Approval

Oracle EBS Access Provisioning

Automates provisioning tasks including:

User creation

Responsibility cloning

Responsibility assignment

Temporary access with end date

Compliance & Audit

All actions are logged to ensure governance and traceability.

Supported Provisioning Scenarios
Scenario	Description
User Creation	Create a new Oracle EBS user
User Creation with Clone	Create user and clone responsibilities from another user
Add Responsibility	Assign additional responsibility to existing user
Clone Responsibility	Copy responsibilities from one user to another
Temporary Access	Assign responsibility with defined end date
Architecture Overview

Workflow summary:

ServiceNow Ticket
       │
       ▼
AI Agent (Description Analysis)
       │
       ▼
Entity Extraction Agent
       │
       ▼
Validation Layer (Oracle EBS)
       │
       ▼
Approval Workflow
  ├ Manager Approval
  └ BPO Approval
       │
       ▼
UiPath RPA Execution
       │
       ▼
Oracle EBS Provisioning
       │
       ▼
ServiceNow Ticket Update
Project Components
AI Agents
Agent	Purpose
DescriptionAnalysis	Detect provisioning purpose from ticket description
Servicenow_DescriptionAnaAgentLattice	ServiceNow request interpretation
ResponsNameExtractor	Extract responsibility names from ticket
Username_Uppercase_lattice	Standardize username format
LatticeUserExtAgent	Extract user information
UserExtAgentNew	Handle responsibility assignment with end dates
ManagerEmailForgeAgent	Generate manager approval emails
BPO_Email_Forge_Agent	Generate BPO approval emails
FinalEmailForgeAgent	Generate final completion notification
BPOApproverExtLattice	Extract BPO approval information
RPA Processes
Process	Description
Lattice Servicenow User creation Responsibility POC	Main orchestration workflow
Lattice_BPOApproval	Handles BPO approval workflow
User_Responsibility Assign_Lattice	Executes Oracle EBS provisioning
Technology Stack

UiPath Studio

UiPath Agentic AI

Oracle E-Business Suite

ServiceNow APIs

SQL Validation Layer

Excel Role Mapping Repository

SMTP / Email Integration

Role Recommendation Engine

If responsibilities are not provided in the request, the system recommends access based on predefined role mappings.

Example:

Department	Role	Responsibilities
Finance	Analyst	AP Invoice Processing, GL Inquiry
Finance	Manager	AP Approval, GL Reporting
HR	Executive	Employee Records Access
HR	Manager	Payroll Approval
IT	Support	User Provisioning, System Monitoring
Benefits

50-70% reduction in manual provisioning effort

Faster ticket resolution

Reduced SLA breaches

Improved access accuracy

Reduced duplication risk

Better compliance and audit traceability

Scalable architecture for future systems

Impact Areas

IT Operations

Identity & Access Management

Oracle EBS Administration

ServiceNow Ticketing

Governance & Compliance

Future Enhancements

Integration with enterprise IAM platforms

Machine learning-based role recommendation

Automated risk scoring for access requests

Cross-application provisioning support

License

This project is developed for internal innovation and ideation purposes
