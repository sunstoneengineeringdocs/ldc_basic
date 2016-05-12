# Getting Started

To create a new set of documentation from the [template](github.com/sunstoneengineeringdocs/docs-template): 

1. Download the [zip of the template](https://github.com/sunstoneengineeringdocs/docs-template/archive/master.zip)
2. Create a new repository in the organization "sunstoneengineeringdocs" on github. The repository name will be the url path for the documentation: a repository named **welder-doc** will be accessable at **docs.sunstoneengineering.com/welder-docs**
3. Commit to the repository
4. Create a branch called gh-pages
5. Push to Github

# Adding a Chapter

1. Add 
  ``` 
  - title: rename-me  
    docs: 
  ```
  to _data/docs.yml changing "rename-me" to a descriptive name
  
2. Add a line under ```category-names:``` in _docs/en/doc-main.md with the form (space, space)[ descriptive name ]: "The name visible on the website"

***Note:*** A category-name has to be added for each language that is active. If there is a problem with the name, then an empty space will show up instead of the display name that you picked under ```category-names```

# Adding a Section

1. add a new file in _docs/en/. The file name must have the form ``` filename.md ``` where ```filename``` is any descriptive name without spaces and the extention is ```.md```. Care has to be taken because sometimes programs will autmatically use the extention ```.markdown``` instead of the required ```.md```
2. After adding the new file, add the ```filename``` (without the .md extention) to _data/docs.yml under one of the ```docs:``` sections. Be sure that you add it in the form of (space, space)- [filename]
3. Be sure to start the file with 
```
---
title: "Section Title"
---
```

# Controlling the Order of Chapters and Sections

The order that Chapter and sections appear in _data/docs.yml is the order that they will appear on the website. Changing this order will change the display order for all languages.

# Adding a new language

1. Copy one of the existing language folders (eg _docs/en/ ) to a new language folder (like _docs/de/ )
2. Do not change any of the file names. All viewable text is editable from inside the file (like the title of a section)
3. Open ```doc-main.md``` in the new language folder
4. Change the settings in the folder:
    * ```layout: dochome``` - Do not change this line
    * ```title: "Documentation Title" ``` - This is the name that displays in the browser tab
    * ```permalink: /en/``` - Change this to the new language folder you created (if new language folder is _docs/de/ then change /en/ to /de/
    * ```languages-translation: "Languages"``` - This is the direct translation of the word "languages" in the target language. It is the word displayed on the language dropdown. It will be displayed exactly how it is here.
    * ```language-translation: "English"``` - This is the name of the language for itself. For german it would be Deutsche. Italian would be italiano. Russian would be русский.
    * ```category-names:``` - These are the translations for each of the Chapters
5. Add the folder name (without slashes) to _data/languages.yml in the form -(space)folder name (ex. - de)

***Note:*** Any section added for one language must be added for each of the others. The contents of the sections do not have to match at all, but each of the section files must exist for each language.


