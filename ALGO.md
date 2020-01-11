## how this works

### Folder structure

```
My Awesome Site
|
|________ config.json
|________ pages
|         |______.
|                |---- index.md
|                |---- contact.md
|                |---- about.md
|         
|________ plugins
|         |______.
|                |---- admin
|                |---- emailer
|________ posts
|         |______.
|                |---- 2018
|                |      |_____.
|                |            |____ how_to_create_a_static_site_using_asha.md
|                |            |____ 10_awesome_productivity_hacks.md
|                |---- 2019
|                |      |_____.
|                |            |____ how_to_create_a_static_site_using_asha.md
|                |            |____ 10_awesome_productivity_hacks.md
|                |---- 2020
|                       |_____.
|                             |____ how_to_create_a_static_site_using_asha.md
|                             |____ 10_awesome_productivity_hacks.md
|         
|________ themes
|         |______.
|                |---- theme_1
|                |      |_____.
|                |            |____ config.json
|                |            |____ header.jinja
|                |            |____ footer.jinja
|                |            |____ page.jinja
|                |            |____ posts.jinja
|                |            |____ post.jinja
|                |            |________ pages
|                |            |         |______.
|                |            |                |---- index.json
|                |            |                |---- contact.json
|                |            |                |---- about.json
|                |            |____ posts
|                |                  |______.
|                |                         |---- 2018
|                |                         |      |_____.
|                |                         |            |____ how_to_create_a_static_site_using_asha.json
|                |                         |            |____ 10_awesome_productivity_hacks.json
|                |                         |---- 2019
|                |                         |      |_____.
|                |                         |            |____ ...
|                |                         |---- 2020
|                |                                |_____.
|                |                                      |____ ...
|                |---- theme_2
|                |      |_____.
|                |            |____ ...
|                |---- theme_3
|                       |_____.
|                             |____ ...
|         
|________ _sites
```
### command line tool:
 - `asha init` - clones folder structure with default theme   
 - `asha intall plugin/theme URL` - clones theme/plugin to theme/plugin folder and run tests.
 - `asha build` - builds static pages and posts from markdown files for specified theme.
 - `asha serve` - serves the static website, use this only for dev environments for production consider something like nginx.

### Algo:

`asha build`

- check global config exists.
- check index.md exists in pages.
- check theme is set in global config. (let's say theme set is T)
- check theme exits and other neccessary items in it.
- compile posts and pages using global and theme configs.
- stop if error - report

