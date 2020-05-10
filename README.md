# Author
Vala Khosravi
# Introduction
This document will help you develop and design scalable Angular projects.
# Project environment
...

# Directory Structure
Acourding to [Mathis Garberg - How to define a highly scalable folder structure for your Angular project](https://itnext.io/choosing-a-highly-scalable-folder-structure-in-angular-d987de65ec7) scalable Angular projects directory should be like this:
## General view
*Note! The [+] indicates that the folder has additional files.*
```
|-- app
     |-- modules
       |-- home
           |-- [+] components
           |-- [+] pages
           |-- home-routing.module.ts
           |-- home.module.ts
     |-- core
       |-- [+] authentication
       |-- [+] footer
       |-- [+] guards
       |-- [+] http
       |-- [+] interceptors
       |-- [+] mocks
       |-- [+] services
       |-- [+] header
       |-- core.module.ts
       |-- ensureModuleLoadedOnceGuard.ts
       |-- logger.service.ts
     |
     |-- shared
          |-- [+] components
          |-- [+] directives
          |-- [+] pipes
          |-- [+] models
     |
     |-- [+] configs
|-- assets
     |-- scss
          |-- [+] partials
          |-- _base.scss
          |-- styles.scss
```
## Modules
```
|-- modules
       |-- home
           |-- components
           |-- pages
           |    |-- home
           |         |-- home.component.ts|html|scss|spec
           |
           |-- home-routing.module.ts
           |-- home.module.ts
```
## Core Module
```
|-- core
       |-- authentication
           |-- authentication.service.ts|spec.ts
       |-- header
           |-- header.component.ts|html|scss|spec.ts
       |-- footer
           |-- footer.component.ts|html|scss|spec.ts
       |-- guards
           |-- auth.guard.ts
           |-- no-auth-guard.ts
           |-- admin-guard.ts 
       |-- http
           |-- user
              |-- user.service.ts|spec.ts
           |-- api.service.ts|spec.ts
       |-- interceptors
           |-- api-prefix.interceptor.ts
           |-- error-handler.interceptor.ts
           |-- http.token.interceptor.ts
       |-- mocks
           |-- user.mock.ts
       |-- services
           |-- srv1.service.ts|spec.ts
           |-- srv2.service.ts|spec.ts
       |-- core.module.ts
       |-- ensureModuleLoadedOnceGuard.ts
       |-- logger.service.ts
```
## Shared Module
```
|-- shared
    |-- components
         |-- loader
              |-- loader.component.ts|html|scss|spec.ts
         |-- buttons
              |-- favorite-button
                   |-- favorite-button.component.ts|html|scss|spec.ts
              |-- collapse-button
                   |-- collapse-button.component.ts|html|scss|spec.ts
    |-- directives
         |-- auth.directive.ts|spec.ts
    |-- pipes
         |-- capitalize.pipe.ts
         |-- safe.pipe.ts
    |-- models
         |-- user.model.ts
         |-- server-response.ts
```
## Config
```
|-- configs
     |-- app-settings.config.ts
     |-- dt-norwegian.config.ts
```
## Styling
```
|-- scss
     |-- partials
          |-- _layout.vars.scss
          |-- _responsive.partial.scss
     |-- _base.scss
|-- styles.scss
```

# Coding system
This section is about code writing rules.
## Variables
### General rules
- All variables must be camelCase
- All field variables must be defined with type
- All variable names must introduce its usage
### Boolean
- Must start with "is"
- The default value must be true and its name should be defined by its default value 
- Never pass opposite value of boolean variable to it self. ~isActive = !isActive~
### Array 
- All array variables must end with "List" instead of "s"
- On iterating on array element name is array name without "List"
## Functions
### General rules
- Function type and type of input parameters should be determined
- All functions that used in template must be public 
- Private function should be used in public functions
### Template functions
Naming pattern: "on" + (button Label, input name, ...) + (event type)

Example: onSubmitClick, onUserNameKeyEnter, ...
### Service functions
Naming pattern: (request type) + (requested model or models) + ("List" or "ById")

Example: getRetailerListWithProductList, postProductById, ...
# Angular CLI commands
```
ng g module --flat --routing=true "module name"
ng g component --module="module name" "component name"
```
