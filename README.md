Leave Management System – ServiceNow Application
Project Overview

The Leave Management System is a custom ServiceNow application developed to manage employee leave requests efficiently. It enables employees to apply for leave, managers to approve or reject requests, and automatically maintains leave balances based on predefined leave policies.

Features

Employee leave request submission

Manager approval and rejection

Automatic leave balance calculation

Leave bucket management

Validation to avoid excess leave requests

Role-based access control

Application Tables
Leave Request Table (u_leave_request)

This table stores all leave requests submitted by employees.

Fields:

Employee (Reference: User)

Leave Type

Start Date

End Date

Number of Days

Status (Requested, Approved, Rejected)

Manager (Reference: User)

Reason

Purpose:

Capture employee leave requests

Trigger approval workflow

Update leave balances after approval

Leave Bucket Table (u_leave_bucket)

This table stores leave balance information for each employee.

Fields:

Employee (Reference: User)

Leave Type

Total Leaves

Used Leaves

Remaining Leaves

Purpose:

Track available and used leaves

Prevent over-utilization of leave

Leave Logic Table (u_leave_logic)

This table defines leave policies and rules.

Fields:

Leave Type

Maximum Leaves Per Year

Carry Forward Allowed

Maximum Carry Forward Days

Approval Required

Purpose:

Centralized configuration for leave policies

Used in business rules and validations

Business Logic

Calculates number of leave days based on start and end date

Validates available leave balance before request submission

Updates leave bucket upon approval

Prevents submission when remaining leave is insufficient

Workflow / Flow Designer

Leave request submission triggers approval flow

Manager receives approval request

Status updates automatically based on action

Security and Roles

Employee: Can create and view own leave requests

Manager: Can approve or reject assigned requests

Admin: Full access to application configuration

Technologies Used

ServiceNow Platform

Application Studio

Business Rules

Flow Designer / Workflow

UI Policies

Client Scripts

Installation

Create a new scoped application in ServiceNow

Create the three tables

Configure forms and fields

Implement business rules and flows

Assign roles and test the application

Future Enhancements

Email notifications

Leave calendar integration

Reporting and dashboards

Multi-level approval workflow
