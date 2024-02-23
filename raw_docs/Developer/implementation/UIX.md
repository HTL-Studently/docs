# UIX

This solution uses Sveltekit as a meta framework in combination with Svelte. For styling we stick to tailwind CSS and its plugin daisy-UI. We aim to create a responsive and inclusive webportal.

## Views

### Student
Sees their own dashboard with payment requests and available licenses. Can access subpages for completing payment requests and for license requests.

### Head of the class
Has the same functionality as the student view with the addition of being able to create payment requests. This role can be assigned by any teacher.

Student and Head of the class share a similar landing page as shown in this mock-up.

![Mockup](../../docs/assets/images/Mockup.png)

### Teacher

Does not have the same dashboard as students do, instead is greeted by a management page where they can select a class to view and has the option to create payment requests, view already submitted payments and request licenses for a class.

### Accounting

The accounting team also has their own view where the simplified page displays all incoming payments. This creates an easily sortable and searchable list view where they have the option to confirm the submitted payments. As displayed on the mock-up, there is also an Events tab which displays submitted payments grouped by their tagged purpose. 

![Finances](../../docs/assets/images/Mockup%20Finances.png)

## Routing

Sveltekit’s routing is a file-based routing system, where each file in the “src/routes” directory corresponds to a route in the application. SvelteKit automatically generates the necessary code to handle navigation between these routes, including client-side transitions. It also supports dynamic and nested routing. One of its features are slugs that enable one singe page to act as a template where URL and content are dynamically replaced. 

The Studently platform uses slugs when accessing individual payment requests.

![Routing](../../docs/assets/images/screeenshot_routing.png)

For the structure in this file-based routing system a folder represents the route where it’s “+page.svelte” page leads to. For example the “src/routes/(protected)/licenses/+page.svelte” file will have the URL of just /Licenses.

## Components

Svelte components that are required to be reusable find a home in the “src/lib” folder. From there they can be easily imported in any file using:

```
Import <alias> from $lib/<name_of_component>
```

If a variable from a certain Component needs to be called outside, it must be exported first then defined as a variable in the file the variable is needed and additionally assigned to its Parent Component. This is also the way links operate. 

For example, when a link is to be added to a navigation component it needs to address it as following:

```
<li><a href="{<onepage>}">One Page</a></li>
```

Then exported as script:

```
Export let <onepage>:string
```

When using it in another file, the parent component must be imported then the value defined:

```
import <alias> from $lib/<name_of_parent>
const <onepage>:string = <route>
```

When called it needs to be inside parent component:

```
<<name_of_parent> {<onepage>}/>
```

