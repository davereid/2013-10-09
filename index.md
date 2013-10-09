# Twig
Dave Reid // [@davereid](https://twitter.com/davereid) // [dave.reid@lullabot.com](mailto:dave.reid@lullabot.com)

===============================================================================
# TWIG!
## Sensio Labs

(same people as Symfony)

[http://twig.sensiolabs.org/](http://twig.sensiolabs.org/)

===============================================================================
## Disclaimer!

Presenting on my first week of a new job! And without a computer!

===============================================================================
## Birds Eye View

- Best template engine for PHP
- Fast
- Secure
- Flexible
- Easy to learn, to read and to write

---------------------------------------
## Test

===============================================================================
# Twig in Drupal

---------------------------------------
## Getting Rid of PHPTemplate

PHPTemplate requires:

- A lot of PHP knowledge, making it difficult to teach.
- Many custom template files, often with very minor changes, making it difficult to maintain.
- PHP to run, making all themes inherently insecure.
- Tight integration with Drupal's theme system, making it difficult to swap out template engines.

Source: https://drupal.org/node/1499460

---------------------------------------
## A new template engine: Twig

- Twig renders variables into a single format, making it easier to learn.
- Twig allows templates to drill into data sources, reducing the number of templates required.
- Twig is secure, because it does not allow PHP to run.
- The Twig initiative has reduced the complexity of the theme system, making it easier to swap out template engines in the
  future.

---------------------------------------
## Twig Removes Drupalisms and PHPisms From Themes

We have removed the following:

- theme function (only templates from now on!)
- guessing if a variable is an object or array or string
- processing (but not preprocess)

---------------------------------------
## Sample Code

From core/themes/bartik/templates/node.html.twig

<pre><code data-trim>
&lt;header&gt;
    {{ title_prefix }}
    {% if not page %}
      &lt;h2{{ title_attributes }}&gt;
        &lt;a href=&quot;{{ node_url }}&quot;&gt;{{ label }}&lt;/a&gt;
      &lt;/h2&gt;
    {% endif %}
    {{ title_suffix }}

    {% if display_submitted %}
      &lt;div class=&quot;meta submitted&quot;&gt;
        {{ user_picture }}
        {{ submitted }}
      &lt;/div&gt;
    {% endif %}
  &lt;/header&gt;

  &lt;div class="content clearfix"{{ content_attributes }}&gt;
    {# We hide links now so that we can render them later. #}
    {% hide(content.links) %}
    {{ content }}
  &lt;/div&gt;

  {% if content.links %}
    &lt;footer class="link-wrapper"&gt;
      {{ content.links }}
    &lt;/footer&gt;
  {% endif %}
</code></pre>

---------------------------------------
## Resources for Twig

- Twig: http://twig.sensiolabs.org/
- Twig in Drupal: https://drupal.org/node/2008464
- Overview of the Twig Project:
  http://www.jenlampton.com/presentations/twig-and-new-theme-layer-drupal-8
- Introduction to Twig (without Drupal) http://www.youtube.com/watch?v=18sxjsLTesE
