# Microsoft GraphAPI

## Why we need it

With the Microsoft GraphAPI, Microsoft Users can be authenticated, authorized. It is also used to fill the user database. Using the structure of its roles students, teachers and heads of classes can be distinguished without further identifiers. The Sandbox Tool Graph Explorer all API calls can be tested.

## Graph Explorer

Find the Graph Explorer [here](https://developer.microsoft.com/en-us/graph/graph-explorer)

The Graph Explorer can be used anonymously or with an account. Using a students account of the customer HTL-Villach all calls can be tested before having to implement them in code. 

## Authenticating a user

No page of this website is meant to be accessible to an unauthenticated user. SvelteKit automatically reroutes users to a Microsoft Login page that returns an authentication code. This code is then used in every single API call. 