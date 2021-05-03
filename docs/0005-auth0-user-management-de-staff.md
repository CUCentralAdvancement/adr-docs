# Use Auth0 For Authentication Within Apps Exclusive To DE Staff

Traditional user management usually involves stroing user credntials within the 
application's local database. Storing user information in that manner allows for more
attack vectors than when offloading user management to a third-party service or group.

For the University of Colorado as a whole, SSO via Ping SAML has been the default for
any application catering to university staff users who may work in any of the university's
four main organizational units. However, when you get into applications that Digital
Engagement only touch, there are examples of shared user accounts outside of Ping SSO.
Granted, some applications have no other way to share user management functionality,
but that's not always the case.

## Sponsors

- Alex Finnarn - DE Front-end Developer - alexander.finnarn@cu.edu

## Status

- **Proposed** - This ADR is a fleshed out idea including documentation but has not been
formally accepted by the whole Digital Engagement team. 

## Prior Art

I've known about Auth0 for quite a while and heard good things. Moving to Heroku and seeing
it listed in the Heroku addon marketplace made it a no-brainer to try out. Experience
with password storage, the password reset process, and other fun, generic user management
development task has left most developers searching for an easier DX, which Auth0 provides.

## Current Context

Setting up authentication per app is a tedious process and leaves room for exposing security
attack vectors with custom code. Auth0 provides a way to manage this via common "social login"
functionality that many libraries and frameworks support.

SSO via Ping SAML is a want but not a need for all applications. With a small set of trusted
users, a service like Auth0 is fine for some DE internal applications.

## Decision

On any application hosted via Heroku, Auth0 can be used to authenticate users while
the application will still be responsible for authorization management. Email addresses
will be used as the primary key linking the Auth0 account to the local user account
within each application. If the user audience expands outside of Digital Engagement,
then the authentication strategies will need to be reviewed.

## Consequences

It is easier to launch an application with this process; however, it can be harder to 
integrate with the Ping SAML solution. As a mitigation step, it would be best to use
the CU email addresses that match Ping SSO accounts. Switching to SAML simply becomes 
replacing the POST to Auth0 with a POST to Ping when a user clicks "Log In".

## Detailed Explanation

For more information, you should read the user management docs at: 


