# Microsoft GraphAPI

## Why we need it

With the Microsoft GraphAPI, Microsoft Users can be authenticated, authorized. It is also used to fill the user database. Using the structure of its roles students, teachers and heads of classes can be distinguished without further identifiers. The Sandbox Tool Graph Explorer all API calls can be tested.

## Graph Explorer

Find the Graph Explorer [here](https://developer.microsoft.com/en-us/graph/graph-explorer)

The Graph Explorer can be used anonymously or with an account. Using a students account of the customer HTL-Villach all calls can be tested before having to implement them in code. 

## Authenticating a user

No page of this website is meant to be accessible to an unauthenticated user. SvelteKit automatically reroutes users to a Microsoft Login page that returns an authentication code. This code is then used in every single API call. 

## Getting Adobe Licenses

The second usage of the Microsoft GraphAPI is gathering intofmation about user licenses. The Adobe Developer API is not usable without admin rights, so using it to gather information about the license status is not viable. The alternative that is being used is gathering said information from the [Adobe Identity Management Application](https://portal.azure.com/#view/Microsoft_AAD_IAM/ManagedAppMenuBlade/~/Overview/objectId/680033ff-1040-43a8-a8db-18d8d6e81f9a/appId/f68114c4-a128-4172-8232-65ca425cc112/preferredSingleSignOnMode~/null/servicePrincipalType/Application/fromNav/) using its ObjectID and the API endpoint at .../servicePrincipals/<OjbectID>/appRoleAssignedTo. The function is also build to support more then just the Adobe Identity Management Application staticly. The list of default licenses and their sources, can be extended by further license objects together with theire sources, either group or application (for example the ObjectID Adobe Identity Management). The licenses are automatically attached when the students collection is build. 

