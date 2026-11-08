# AWS Monitoring, Management & Cost

## BLA6 AWS Cloud

## Topics: Amazon CloudWatch, AWS CloudTrail, AWS Billing and Cost Management, AWS Pricing, and AWS Support.

### 1. Overview

AWS monitoring, management, and cost services help organisations observe
their cloud environments, investigate account activity, understand
expenditure, estimate future costs, and obtain technical assistance.

  -----------------------------------------------------------------------
  Service / Concept                   Main purpose
  ----------------------------------- -----------------------------------
  Amazon CloudWatch                   Monitors AWS resources and
                                      applications using metrics, logs,
                                      dashboards, and alarms

  AWS CloudTrail                      Records AWS account activity and
                                      API events for auditing and
                                      investigation

  AWS Billing and Cost Management     Provides access to billing
                                      information, charges, invoices, and
                                      cost-management tools

  AWS Cost Explorer                   Analyses historical AWS costs and
                                      usage and can forecast future costs

  AWS Budgets                         Sets cost, usage, and other budget
                                      thresholds and can send alerts

  AWS Pricing Calculator              Estimates the cost of planned AWS
                                      workloads

  AWS Support                         Provides support resources and
                                      technical assistance according to
                                      the selected support plan

  AWS Trusted Advisor                 Provides checks and recommendations
                                      to help optimise AWS environments
  -----------------------------------------------------------------------

### 2. Amazon CloudWatch

Amazon CloudWatch is a monitoring and observability service for AWS
resources, applications, and services.

#### Key capabilities

-   **Metrics:** Numerical measurements such as EC2 CPU utilisation,
    network activity, and other resource or application measurements.
-   **Logs:** Collects and stores log data that can help investigate
    application and system behaviour.
-   **Alarms:** Watches metrics and can take configured actions or send
    notifications when thresholds or conditions are met.
-   **Dashboards:** Displays selected metrics and monitoring information
    in one place.
-   **Events and automation:** CloudWatch integrates with other AWS
    services to support event-driven responses and operational
    workflows.

#### Example

-   A team wants to know when an EC2 instance has sustained CPU
    utilisation above 80%.
-   It can create a CloudWatch alarm based on the relevant CPU metric.
-   The alarm can send a notification through Amazon SNS or trigger a
    configured response, such as an Auto Scaling action.

#### When to use CloudWatch

-   Monitor application and infrastructure performance.
-   Collect and review application logs.
-   Create dashboards for operational visibility.
-   Alert teams when metrics meet specified conditions.
-   Trigger supported automated responses.

**Exam hint:** Performance metrics, logs, dashboards, and alarms point
to Amazon CloudWatch.

### 3. AWS CloudTrail

AWS CloudTrail records activity in an AWS account, including actions
performed through the AWS Management Console, AWS CLI, SDKs, and APIs.

It helps answer questions such as:

-   Who performed an action?
-   What action was performed?
-   When did it happen?
-   Which identity or account was involved?
-   What request details are available for investigation?

#### Key concepts

-   **Management events:** Record management operations performed on
    resources, such as creating, modifying, or deleting resources.
-   **Event history:** Provides a searchable record of the past 90 days
    of management events in a Region.
-   **Trails:** Can deliver event records to destinations such as Amazon
    S3 for longer-term retention and analysis.
-   **CloudTrail Lake:** Supports querying and analysing event data
    using SQL.
-   CloudTrail can be integrated with CloudWatch Logs and other services
    for monitoring and alerting workflows.

#### Example

-   An EC2 instance is unexpectedly terminated.
-   An administrator reviews CloudTrail events to identify the API
    activity and the identity associated with the action.
-   A trail can retain event records in Amazon S3 for longer-term
    auditing.

**Exam hint:** Questions asking who performed an AWS action, what
changed, or when an API operation occurred point to AWS CloudTrail.

### 4. AWS Billing and Cost Management

AWS Billing and Cost Management provides tools and information to
understand, organise, and manage AWS charges.

#### Billing Dashboard

-   Displays billing information and an overview of AWS charges.
-   Provides access to invoices, payments, and billing preferences.
-   Helps account owners review their current billing position.

#### AWS Cost Explorer

-   Analyses historical cost and usage data.
-   Groups and filters costs by dimensions such as service, linked
    account, Region, and usage type.
-   Helps identify spending trends and major cost drivers.
-   Can provide forecasts based on historical patterns.

#### AWS Budgets

-   Creates cost, usage, and other supported budgets.
-   Tracks actual or forecasted values against configured thresholds.
-   Can send notifications when a threshold is reached or forecast to be
    reached.
-   Budget alerts do not automatically stop all AWS spending. Any
    automated action must be separately configured and supported.

#### Example

-   A team has a monthly AWS cost target of \$500.
-   It creates an AWS cost budget and configures notifications at
    selected thresholds, such as 80% and 100%.
-   The team uses Cost Explorer to investigate which services are
    driving expenditure.

**Remember:** \* Billing Dashboard = View billing information and
invoices. \* Cost Explorer = Analyse historical costs and usage. \* AWS
Budgets = Set thresholds and receive alerts.

### 5. AWS Pricing

AWS offers different pricing approaches depending on the service and
workload.

#### On-Demand

-   Pay for eligible resources as they are used, without a long-term
    capacity commitment.
-   Useful for variable, short-term, or unpredictable workloads.
-   Exact billing units and rates depend on the service.

#### Reserved Instances

-   Provide discounted pricing for eligible usage when the customer
    makes a reservation commitment, generally for a one-year or
    three-year term.
-   Availability and payment options depend on the service and offering.
-   For Amazon EC2, Reserved Instances are a billing discount construct
    and do not always represent a physical instance reservation.

#### Savings Plans

-   Offer lower prices in exchange for a commitment to a consistent
    amount of eligible compute usage, measured in dollars per hour, for
    a one-year or three-year term.
-   The applicable Savings Plan type determines which usage is covered.

#### Spot Instances

-   Allow customers to use spare Amazon EC2 capacity at a discount
    compared with On-Demand prices.
-   AWS can interrupt Spot Instances when it needs the capacity back.
-   Suitable for flexible, interruption-tolerant workloads.

#### AWS Pricing Calculator

-   Estimates the cost of planned AWS workloads.
-   Helps compare service configurations and estimate expected charges
    before deployment.
-   Estimates are not a guarantee of the final bill; actual costs depend
    on usage, configuration, Region, and applicable pricing.

**Exam hint:** \* Flexible usage without a long-term commitment =
On-Demand. \* Commitment-based discounts = Reserved Instances or Savings
Plans, depending on the requirement. \* Discounted spare EC2 capacity
that can be interrupted = Spot Instances. \* Estimate planned workload
costs = AWS Pricing Calculator.

### 6. AWS Support

AWS Support provides resources and support options to help customers
operate AWS workloads.

#### Basic Support

-   Included for all AWS customers.
-   Provides access to documentation, AWS re:Post, service health
    information, and account and billing support resources.
-   Does not include the same technical support capabilities as paid
    support plans.

#### Paid support plans

-   Paid plans provide additional technical support capabilities.
-   Features, response targets, access to support engineers, and other
    benefits vary by plan.
-   Customers should compare the current AWS Support plan descriptions
    to select an option that meets their operational needs.

#### Other support resources

-   **AWS Knowledge Center:** Answers to common AWS questions.
-   **AWS re:Post:** Community-based technical questions and answers.
-   **AWS Support Center:** A place to manage support cases and view
    support information.
-   **AWS Trusted Advisor:** Checks and recommendations across areas
    such as cost optimisation, security, performance, fault tolerance,
    and service limits. Available checks and features depend on the
    account and support entitlements.

**Exam hint:** Technical assistance and support cases point to AWS
Support. Recommendations to improve an AWS environment point to AWS
Trusted Advisor.

### 7. How the services work together

Example: monitoring and controlling costs for an online application.

-   CloudWatch monitors application and infrastructure metrics and logs.
-   CloudWatch alarms can notify an operations team when defined
    performance conditions occur.
-   CloudTrail records account activity and API events for auditing and
    investigation.
-   The Billing Dashboard provides access to billing information and
    invoices.
-   Cost Explorer helps the team understand historical spending and
    identify cost drivers.
-   AWS Budgets sends alerts when actual or forecasted spending reaches
    configured thresholds.
-   AWS Pricing Calculator helps estimate costs before adding or
    changing workloads.
-   AWS Support provides assistance when the organisation needs help
    with AWS services.
-   Trusted Advisor can provide recommendations to improve cost
    efficiency and other aspects of the environment.

Not every workload needs every tool. Select services based on the
organisation's monitoring, audit, financial, and support requirements.

### 8. Practical configuration and review checklist

#### 1. Monitoring with CloudWatch

-   [ ] Identify the resources and application metrics that need
    monitoring.
-   [ ] Review available metrics and configure any required custom
    metrics.
-   [ ] Configure log collection where appropriate.
-   [ ] Create dashboards for important operational information.
-   [ ] Create alarms with meaningful thresholds and evaluation periods.
-   [ ] Configure notification or automated actions where required.

#### 2. Account activity with CloudTrail

-   [ ] Review CloudTrail Event history when investigating recent
    management activity.
-   [ ] Configure a trail when ongoing event delivery and retention are
    required.
-   [ ] Select appropriate event types and Regions for the audit
    requirement.
-   [ ] Protect and manage access to the S3 destination.
-   [ ] Consider retention, encryption, and monitoring requirements.

#### 3. Billing and cost management

-   [ ] Review the Billing Dashboard and invoices.
-   [ ] Use Cost Explorer to identify spending trends and cost drivers.
-   [ ] Create AWS Budgets for important cost or usage thresholds.
-   [ ] Configure budget notifications and review who receives them.
-   [ ] Investigate unexpected increases in spending.
-   [ ] Remove or right-size resources that are no longer required,
    after checking dependencies.

#### 4. Pricing and support

-   [ ] Estimate planned workloads with AWS Pricing Calculator.
-   [ ] Compare On-Demand, commitment-based, and Spot options where
    appropriate.
-   [ ] Check interruption tolerance before using Spot Instances.
-   [ ] Review current AWS Support plan features and requirements.
-   [ ] Use Trusted Advisor recommendations where available.

### 9. Quick comparison for exam revision

  -----------------------------------------------------------------------
  If the question asks about...       Think of...
  ----------------------------------- -----------------------------------
  CPU utilisation, metrics, logs, or  Amazon CloudWatch
  alarms                              

  Who made a change or performed an   AWS CloudTrail
  API action                          

  Viewing invoices or billing         Billing Dashboard
  information                         

  Analysing historical spending       AWS Cost Explorer

  Setting spending thresholds and     AWS Budgets
  alerts                              

  Estimating costs before deployment  AWS Pricing Calculator

  Discounted spare EC2 capacity that  Spot Instances
  can be interrupted                  

  Technical assistance from AWS       AWS Support                 
  -----------------------------------------------------------------------
