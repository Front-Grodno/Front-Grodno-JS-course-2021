# Routing

## Task 7
1. Create routing for your application (via [React Router](https://www.npmjs.com/package/react-router)).
2. Add [404](https://projects.invisionapp.com/share/F9VXQ7IMZGY/#/screens/406802243) (error page) and [No movies found](https://projects.invisionapp.com/share/F9VXQ7IMZGY/#/screens/406802248) page.
3. Link app states between each other with `React Router`.
4. By default, user lands on a new page with empty results state.
5. When user clicks on a film item, redirect them to: `localhost/film/id`.
6. Handle invalid URLs, display a `404 page`, where user will be redirected in case of invalid URL.
7. On switching search type or sorting type you shouldn't switch any routes.
8. When user performs a new search, you should redirect them to `localhost/search/Search%20Query`. When a new user lands on the page with such URL, you should perform search and display results.
