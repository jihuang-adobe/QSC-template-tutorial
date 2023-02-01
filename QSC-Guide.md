# QSC Template Creation

![QSC Template](images/qsc-template-creation.png)

This is a guide on how to create a new QSC Template, using the Standard Template as the base.

## Prerequisites

Review the required tooling and instructions for setting up a [local development environment](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/overview.html?lang=en#local-dev-environment). Ensure that you have a fresh instance of Adobe Experience Manager available locally and that no additional sample/demo packages have been installed (other than required Service Packs).

## Download the Basic Site Template

A Site Template provides a starting point for a new site. A Site Template includes some basic theming, page templates, configurations and sample content. Exactly what is included in the Site Template is up to the developer. Adobe provides a **Basic Site Template** to accelerate new implementations.

1. Open a new browser tab and navigate to the Basic Site [Template project on GitHub](https://github.com/adobe/aem-site-template-standard). The project is open-sourced and licensed to be used by anyone.

2. Click Releases and navigate to the [latest release](https://github.com/adobe/aem-site-template-standard/releases/latest).

3. Expand the Assets dropdown and download the Source Code file:

## Source Code Structure Explained
```
aem-site-template-standard-aem-site-template-standard-x.x.x
│   ...
│
└───files
│       wireframe.xd
│
└───preview
│       StandardSiteTemplate.png
│
└───site
│   │   pom.xml
│   │   ...
│   │
│   └───src
│   │       ...
│   │
│   └───target
│           ...
│
└───theme
    |   env_template
    |   ...
    |   
    └───src
            ...
```

`files` Folder with the UI wireframes and other files supporting current design

`preview` Folder with screenshots of the site template

`site` Base site structure, content and template policies that are copied and used on each site creation from template

`theme` Global template theme responsible for how the site looks (CSS, JS, etc)

## Compile Theme

Go to theme

run `npm install`

run `npm run build`

## Make Local Theme Externally Accessible

Go to `theme/dist`

run `http-server`

## Deploy Site Structure, Content and Template Policies

Go to site and run `mvn clean install`

Install `target/xxx.zip` via Package Manager

## Configure Site to Use Local Theme

Use crx/de to go to /conf/aem-site-template-standard/sling:configs/com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig/jcr:content

make backup of prefixPath

change prefixPath to http://localhost:8080