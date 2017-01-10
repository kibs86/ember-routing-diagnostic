# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The Ember Application Router is what parses the URL.  The Ember Route is what loads the data from the model and displays it's corresponding template.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember generate route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}}Boston{{/link-to}}
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
    I'm not completely sure on this one, but below is my best attempt.
    1. The first route definition would be used for nested templates while the second one would be a better use case for what the above is actually accomplishing (doing a deeper view on a single item.  Basically a show instead of an index.).
    2. The first one is setting up products/product and then mapping product to :product_id (effectively setting the path to products/:product_id).  The second route definition is doing that much more directly and just mapping product directly to /products/:product_id.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    params.movie_id
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    You'd put the data you want to display within handlebars.  If the data is coming directly from a Route then it will be called model.  So something like:  {{model.title}}.
    ```
