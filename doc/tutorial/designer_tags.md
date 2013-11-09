[Up](../tutorial.md)

Tags
====
Designers will probably like to write some tags rather than write php.
These tag patterns will be automatically parsed into several values:


| Tag Pattern                                                                                                                                                                                                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{ user_id }}                                                                                                                                                                                                | Show user id or empty string if user not logged in                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| {{ user_name }}                                                                                                                                                                                              | Show user name or empty string if user not logged in                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| {{ user_real_name }}                                                                                                                                                                                         | Show user's real name or empty string if user not logged in                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| {{ user_email }}                                                                                                                                                                                             | Show user's email or empty string if user not logged in                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| {{ site_url }}                                                                                                                                                                                               | Show the site's url with trailing slash (e.g: http://localhost/No-CMS/index.php/)<br />Usually used if you want to make a link to a page<br />  &lt;a href=”{{ site_url }}main/index”&gt;Go to home&lt;/a&gt;                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| {{ base_url }}                                                                                                                                                                                               | Show the base url with trailing slash (e.g: http://localhost/No-CMS/)<br />Usually used if you want to include an image, javascript or <span style="line-height: 1.5em;">css</span><br /> &lt;img <span style="line-height: 1.5em;">src=”{{ base_url }}assets/nocms/img/some_image.jpg” /&gt;</span>                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| {{ module_path }}                                                                                                                                                                                            | Show the module path relative to the /modules directory<br />(e.g: main, blog etc)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| {{ module_site_url }}                                                                                                                                                                                        | Show the module site url (e.g: http://localhost/No-CMS/index.php/blog)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| {{ module_base_url }}                                                                                                                                                                                        | Show the module site url (e.g: http://localhost/No-CMS/blog)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| {{ widget_slug:slug }}                                                                                                                                                                                       | Show widgets with certain slug<br />(e.g: {{ widget_slug:advertisement }} will show all widget that has advertisement slug)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| {{ widget_name:name }}                                                                                                                                                                                       | Show widgets with certain name<br />(e.g: {{ widget_name:login }} will show a widget named login)<br />See [here](user_widget.md) to get the complete default widget                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| {{ language }}                                                                                                                                                                                               | Show current language used.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| {{ language:some_word }}                                                                                                                                                                                     | Show translation of word in current language. The language setting file is located in `/assets/nocms/languages` and `/modules/module_name/assets/languages`.<br />Just add a new entry and it will works.<br /> For more information about language setting, please click [here](programmer_translation.md)                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| {{ if_language:a_language }}<br />  content in a_language<br />{{ elif_language:another_language }}<br />  content in another_language<br />{{ else }}<br />  content if no language match<br />{{ end_if }} | This tag make No-CMS prevail in multi-language content. Let's take a look at this simple example:<br />{{ if_language:english }}<br />  Nice to meet you, {{ user_real_name }}<br />{{ elif_language:japanese }}<br />  始めまして, {{ user_real_name }} さん<br />{{ elif_language:indonesia }}<br />  Senang bertemu dengan anda, {{ user_real_name }}<br />{{ else }}<br />  Hi, {{ user_real_name }}<br />{{ end_if }}<br /><br />If your language setting is “english”, then there will be “Nice to meet you, Go Frendi Gunawan” shown. If your language setting is “japanese”, then there will be “始めまして, Go Frendi Gunawan さん” shown. Such a thing will also be applied if your language setting is “indonesia” or “other” language.  |
| {{ configuration_value }}                                                                                                                                                                                    | Show configuration value.<br />Example:<br />{{ site_name }}, {{ site_slogan }}, {{ site_favicon }}<br /><br />For complete configuration value, take a look at `CMS Management | Configuration Management`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| {{ navigation_path }}                                                                                                                                                                                        | Create navigation path (breadcrumb)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| {{ used_theme }}                                                                                                                                                                                             | Currently used theme                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

You can put these tags on both, static & dynamic page, theme's view, layout etc.
__PS:__ There is always a space between curly brace and the words.                                                                           