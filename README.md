#gdcat
=========

Use one or more properties of a category to easily find other properties and make them available in templates independent of the native exp:channel:category tag pair.

##Single Tags

```
{exp:gdcat:group_id [parameters]} 
{exp:gdcat:url_title [parameters]}
{exp:gdcat:name [parameters]} 
{exp:gdcat:id [parameters]}
{exp:gdcat:description [parameters]} 
{exp:gdcat:image [parameters]}
{exp:gdcat:order [parameters]}
```

##Single Tag Parameters
All are optional, but query will return
the first result it finds meeting the criteria set in the parameters, 
so whenever possible using the group_id and either the cat_id or 
cat_url_title is recommended.

```
group_id
cat_id
cat_name
cat_url_title
```


##Tag Pairs:
----------------------------------------------------------------------------

### exp:gdcat:category

Display category

```
{exp:gdcat:line group_id="1" cat_url_title="category-url-title"}
 {cat_id}
 {site_id
 {group_id}
 {parent_id}
 {cat_name}
 {cat_url_title}
 {cat_description}
 {cat_image}
 {cat_order}
{/exp:gdcat:line}
```

### exp:gdcat:line

Display category as parent-child heirarchy

```
{exp:gdcat:line group_id="1" cat_url_title="category-url-title"}
 {cat_id}
 {site_id
 {group_id}
 {parent_id}
 {cat_name}
 {cat_url_title}
 {cat_description}
 {cat_image}
 {cat_order}
{/exp:gdcat:line}
```


###Change Log

1.2.0
 - Added {exp:gdcat:category} variable pair for displaying parsed category info.
 - Added br_desc parameter for applying nl2br to cat_description

1.1.1 - Bug fix - cat() function in :line tag was being called recursively and throwing error. 
Now using private category() method instead.

1.1.0 - Added {exp:gdcat:line} variable pair for showing parent categories 
for a category based on its group_id and category_url_title
