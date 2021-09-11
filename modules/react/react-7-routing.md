# Routing

## Materilas
[React-Router](https://www.freecodecamp.org/news/learn-react-router/) video tutorial

[Run the React Router v4 Examples](https://egghead.io/lessons/react-run-the-react-router-v4-examples-with-create-react-app)

[Туториал по использованию React Router v4](http://falbar.ru/article/tutorial-po-ispolzovaniyu-react-router-v4)

## Task 7
1. Create routing for your application (via [React Router](https://www.npmjs.com/package/react-router) - there are more tutorials about `v4`, but you can use `v5` as well, the difference between these versions is not significant).
2. Add [404](https://projects.invisionapp.com/share/F9VXQ7IMZGY/#/screens/406802243) (error page) and [No movies found](https://projects.invisionapp.com/share/F9VXQ7IMZGY/#/screens/406802248) page.
3. Link app states between each other with `React Router`.
4. By default, user lands on a new page with empty results state.
5. When user clicks on a film item, redirect them to: `localhost/film/id`.
6. Handle invalid URLs, display a `404 page`, where user will be redirected in case of invalid URL.
7. On switching search type or sorting type you shouldn't switch any routes.
8. When user performs a new search, you should redirect them to `localhost/search/Search%20Query`. When a new user lands on the page with such URL, you should perform search and display results.


## Control questions
1. What is `React Router`?
2. What are the `<Router>` components?
3. What is the purpose of `push()` and `replace()` methods of history?
4. How do you programmatically navigate using `React Router`?
5. How to get query parameters in `React Router`?
6. How to implement `default` or `NotFound` page?
7. How to get history on `React Router`?
