# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    When user interacts with application, our application moves to different states. Those states are determined by the URL that is currently loaded. Ember Applcation Router holds all routes that are provided by the app. Router redirect to a new URL.

    Ember route is router handler that loads tempalte and model. Router changes the template on the screen once data is rendered.


    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus' boston}}Link{{/link-to}}
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
    Product route expects path in the browser that matches the product id. Like so: movies/1


    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    We pass params into our Route object so it matches the movies_id in the browser.

    export default Ember.Route.extend({
      model (params) {
      return this.get('store').findRecord('movie', params.movie_id);
  }
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    We are referencing them through components if we have one. We use {{each}} helper to loop throuhg the data.

    Example with component:
    {{movies-list list=list}}

    Data will be referenced in the component template.

    Example without component:
    {{#each model  as |movie|}}
          <h3>Movie id is: {{movie.id}}
    {{/each}}

    ```
