# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
  The main tasks of an Ember Application Router are to set the paths of the
  routes and sub-routes you will use for each route view-state or template.  In an Ember
  Route, the main tasks are to set the data that you would like to return
  from your model and to pass any appropriate parameters that allow you to
  pull specific data from the model.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
  ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    If we are linking from campuses to the boston campus, you would use the link-to
      {{#link-to 'campus.boston'}}Click here to go to Boston{{/link-to}}
    in the Campus template.
    This would create a link that would bring you to the Boston campus view state.
    You could create a link back to the main campus view by putting
      {{#link-to 'campus'}}Click here to go to Campus{{/link-to}}
    in the Boston template.
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    1) For the second example, there is no route simply called '/products', whereas
    in the first example, there is.

    2) The first route is also nested, with 'product' being nested inside of
    'products' route.  The second example is not nested and stands alone.  We
    do not know if there is a standalone '/products' route based upon the second
    example.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
  We can reference the value '123' inside a Route by passing that number as params
  into the model function. Then, if the object were an array, we would want
  to take 1 less than the value of the ID to access the data at that index, which
  would (theoretically, depending on your ID-assigning convention) target the
  appropriate data.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
  Inside a template, we reference data by {{model.<key name>}}.  You can set the
  model to either plain old 'model' or to the name of the object(or any other name
  for that matter) that you would like to iterate over.  To accomplish the
  latter, an example would be seen with engineers:
  {{#each model as |engineer|}}
    {{engineer.name}}
    {{engineer.team}}
    {{engineer.years}}
  {{/each}}
    ```
