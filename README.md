# Author
Vala Khosravi
# Introduction
This document will help you develop and design scalable Angular projects.
# Project environment
...

# Directory Structure
...

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
