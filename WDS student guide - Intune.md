# Intune Whiteboard Design Session

**Contents**

<!-- TOC -->

- [Intune Whiteboard Design Session](#intune-whiteboard-design-session)
- [Hybrid identity whiteboard design session student guide](#hybrid-identity-whiteboard-design-session-student-guide)
  - [Abstract and learning objectives](#abstract-and-learning-objectives)
  - [Step 1: Review the customer case study](#step-1-review-the-customer-case-study)
    - [Customer situation](#customer-situation)
    - [Customer needs](#customer-needs)
    - [Key design considerations](#key-design-considerations)
  - [Step 2: Design a proof of concept solution](#step-2-design-a-proof-of-concept-solution)
  - [Step 3: Present the solution](#step-3-present-the-solution)
  - [Wrap-up](#wrap-up)
  - [Additional references](#additional-references)

<!-- /TOC -->

#  Hybrid identity whiteboard design session student guide

## Abstract and learning objectives 

In this whiteboard design session, you will learn how to implement different components of Microsoft Intune to manage and monitor endpoint devices.  This will include determining how to architect for automatic enrollment, Azure AD Conditional Access policies with Intune, setting up and monitoring updates, and troubleshooting compliance issues.

## Step 1: Review the customer case study 

**Outcome**

Analyze your customer's needs.

Timeframe: 15 minutes

Directions:  With all participants in the session, the facilitator/SME presents an overview of the customer case study along with technical tips.

1.  Meet your table participants and trainer.

2.  Read all of the directions for steps 1-3 in the student guide.

3.  As a table team, review the following customer case study.

### Customer situation

Contoso is a medium size financial services company with its headquarters in New York and a branch office in San Francisco. It is currently operating in Microsoft 365, with majority of its devices running on the Windows platform with some personal Apple and Android devices. 

Contoso is facing challenges related to increased mobility of its workforce. In particular, in order to drive down its office space costs, Contoso management is considering implementing a flexible work arrangement policy which would allow its employees to work on designated days from home, using either corporate- and employee-owned devices. However, the Contoso's Information Security team expressed concerns about insufficient controls that would prevent access from unauthorized or non-compliant systems. In addition, there are concerns regarding maintaining proper security updates and patches on their Windows devices, and having users access certain applications with devices that may be compromised. 
 
**Existing Contoso environment**

Contoso has an Azure Active Directory infrastructure with a custom domain of contoso.com. Contoso has all of their Windows devices upgraded to Windows 10.  Users are also permitted to access their company email from their personal smart devices, though they have not implemented any MDM or MAM solution to avoid potential data leakage.

**Customer objectives**

Contoso is exploring the option of transitioning its operations into a more internet-open model which would facilitate support for mobile workforce and integration with business partners, while, at the same time, support current security and manageability controls. Given its current environment, Contoso intends to evaluate Azure Active Directory and Microsoft Intune as potential identity and management components of the target design.

The identity component of the target design should facilitate step-up authentication and per-application permissions based not only on the properties of users' accounts but also on the state of these users' devices. To maximize security, Contoso wants to minimize the effort required to monitor and manage updates on devices that have access to company resources.  They would like to have controls in place that if a device is not joined to the Azure Active Directory domain and is not compliance from an update perspective, that device is not allowed to access resources. For obvious reasons, such devices need to be closely monitored and audited.
 
Besides enhancing self-service user capabilities, Contoso wants to optimize end-user experience, especially in environments where users might be using several different devices. The user-defined settings, such as accessibility or app customization should be consistent across all devices.
 
In order to facilitate compliance of devices, the experience to users should be as seamless and transparent as possible, while still maintaining company policy.  Access to applications from compliant devices should not impede user efficiency.  

From a support perspective, IT support staff should be able to monitor device compliance and report back to management when users and devices within their department are not compliant to the policies.

Contoso has multiple departments with different requirements. These requirements are:

- IT Department - all devices are enrolled into MDM and MAM but no policies should block their access to applications.
  
- C-level Executives - all devices are enrolled and monitored for compliance.  If a device is non-compliant, they need to be notified and IT support will assist in getting these devices compliant.  They should never be blocked access to any applications.
  
- Departmental managers and directors - all devices are enrolled and monitored for compliance.  Non-compliant devices will be allowed to access applications when they are accessing from trusted office locations, which includes any of the company offices or their home office.  Otherwise, non-compliant devices will be blocked access to company applications and data.
  
- Sales/Marketing - all devices are enrolled and monitored for compliance.  Non-compliant devices will be allowed to access applications when they are accessing from trusted office locations, which includes any of the company offices or their home office.  Otherwise, non-compliant devices will be blocked access to company applications and data.
  
- HR/Legal - all devices are enrolled and monitored for compliance.  Non-compliant devices will be not be allowed to access applications.  Only compliant devices can access company applications and data.

### Customer needs 

1.  All users must be able to sign into their devices using their Azure Active Directory credentials.  User devices must be enrolled in some form of MDM or MAM for access to company applications. 

1.  Windows 10 devices need to be fully managed by the company. 

1.  Smart devices will required different management requirements depending on whether they are company-owned or personal. 

1.  Users should not be required additional authentication verification nor should they be blocked from accessing resources when in a company office.

1.  The IT department requires the ability to manage the update level and features on Windows 10 devices.  They also need to maintain a minimum and maximum version on company-owned smart devices.

1. The IT department should be able to monitor and report on compliant and non-compliant devices, and provide details as to why devices are non-compliant to department managers.


### Key design considerations

1.  The choice of the endpoint management authority for Windows 10, Apple, and Android devices.

1.  The choice of how to handle company-owned versus personal devices.

1. The choice for handling access to company resources when devices are non-compliant.

1.  The choice of handling version control of devices.

1. The requirements for reporting to non-compliant user devices to management.


## Step 2: Design a proof of concept solution

**Outcome**

Design a solution and prepare to present the solution to the target customer audience in a 15-minute chalk-talk format.

Timeframe: 90-120 minutes

**Business needs**

Directions: With all participants at your table, answer the following questions and list the answers on a flip chart:

1.  Who should you present this solution to? Who is your target customer audience? Who are the decision makers?

2.  What customer business needs do you need to address with your solution?

**Design**

Directions: With all participants at your table, respond to the following questions on a flip chart:

*Architecting an endpoint management solution*

1.  Using the features of Intune and the requirements from the customer, how would you design an endpoint management solution?

2.  How does your design accounts for customer objectives and needs?

*Architecting an endpoint management solution*

1.  How does your solution address all the customer requirements in regard to authentication?

*Implementing an endpoint management solution*

1.  What are the steps to implement an endpoint management solution that will allow you to meet all the customer requirements?

1. How will you address company-owned and personal devices?

1. How will you address different operating systems?



**Prepare**

Directions: With all participants at your table:

1.  Identify any customer needs that are not addressed with the proposed solution.

2.  Identify the benefits of your solution.

3.  Determine how you will respond to the customer's objections.

Prepare a 15-minute chalk-talk style presentation to the customer.

## Step 3: Present the solution

**Outcome**

Present a solution to the target customer audience in a 15-minute chalk-talk format.

Timeframe: 30 minutes

**Presentation**

Directions:

1.  Pair with another table.

2.  One table is the Microsoft team and the other table is the customer.

3.  The Microsoft team presents their proposed solution to the customer.

4.  The customer makes one of the objections from the list of objections.

5.  The Microsoft team responds to the objection.

6.  The customer team gives feedback to the Microsoft team.

7.  Tables switch roles and repeat Steps 2-6.

##  Wrap-up 

Timeframe: 15 minutes

Directions: Tables reconvene with the larger group to hear the facilitator/SME share the preferred solution for the case study.

##  Additional references

|    |            |
|----------|:-------------:|
| **Description** | **Links** |
| What is hybrid identity with Azure Active Directory? | <https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity>  |
| Choose the right authentication method for your Azure Active Directory hybrid identity solution | <https://docs.microsoft.com/en-us/azure/security/fundamentals/choose-ad-authn>  |
| Azure AD Connect sync: Understand and customize synchronization |  <https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis> |
| Buy a custom domain name for Azure App Service | <https://docs.microsoft.com/en-us/azure/app-service/manage-custom-dns-buy-domain>  |
| What is Conditional Access? | <https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview>  |
| Azure Active Directory B2B documentation | <https://docs.microsoft.com/en-us/azure/active-directory/b2b/>  |
| Azure Active Directory B2C documentation | <https://docs.microsoft.com/en-us/azure/active-directory-b2c/>  |
| Microsoft Enterprise Mobility + Security options | <https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing>
