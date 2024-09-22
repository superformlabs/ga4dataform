So, I’ve installed ga4dataform.. now what?
Browse to the files
On the repository page, select the created repository you just created, and browse to the Development workspace


Browse to includes/custom_config.js and adjust the parameters to your needs

Add some customisations
Now, you can configure custom parameters you want in your events dataset. Let’s look at GA4 and just use those:

We see 7 custom dimensions, of which 6 are needed
clean_path is already in the model (as page.path)
6 are going to be configured
5 as string
1 as number (int)
I will rename the event param shop to become the column name shop_name
const CUSTOM_PARAMS_ARRAY = [
  // outside the core ones
  { name: "details", type: "string" },
  { name: "is_logged_in", type: "string" },
  { name: "items_in_cart", type: "int" },
  { name: "message", type: "string" },
  { name: "product_name", type: "string" },
  { name: "shop", type: "string", renameTo: "shop_name" },
];

This website uses q as search term url parameter, and some other URL parameters to indicate filters. Let’s add those:

Save your changes
When making changes, you have to test them (which we’re not going to do now, haha) and when it’s all working: push them into production.
First commit, then push
Commit
