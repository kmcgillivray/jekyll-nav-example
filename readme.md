# Jekyll Nested Nav Example

This is an example of a site with a nested page navigation generated automatically by Jekyll. The goal is to:

1. Automatically generate a nested navigation.
2. Keep the site content organized and manageable.

## How it works

1. All pages that should be included in the nested navigation are written in the `/sections` directory. They're separated from the rest of the site in their own directory to avoid looping through _all_ site pages, and for general organization.
2. In `_includes/header.html`, we include `navigation.html` like so:

  ```html
  <header>
    <a href="/">Home</a>
    {% include navigation.html context="/sections/" %}
  </header>
  ```

  This creates a loop through all pages starting with the given `context` path. You can rename the `/sections` directory to a name that makes more sense for your content, but it will need to be updated here. You can also start the loop at the root instead of the `/sections` subdirectory by changing this property to `context="/"`.
3. In `_includes/navigation.html`, there is a loop that handles the logic for finding the pages and nesting them. This has been highly simplified, so you'll need to edit this to add links and styling to the nav if necessary.
