+++
draft = false
title = '01 Building our First CRUD App in Go!'
series = ['Our First CRUD App']
tags = ['projects']
+++

## Getting CRUDy

### Create

### Read

### Update

### Delete

## Why CRUD?

## To-Do Lists: The Hello World of Applications

## Our Tools

## A Demo

## Setup

### File Structure

Go ahead and create the following file structure:

```
.
|_main.go
|_/handlers
|_/models
|_/router
|_/storage
|_/utils
|_/view
|_LICENSE
|_README.md
```



**/handlers**: This handles our HTTP Requests and tells our code what to do when it gets a specific HTTP Request

**/models**: Models are where our data structures sit, like our structures. Usually we have some validation that also sits here to check our data matches what is in our database

**/router**: This is our middleware and acts as a "restaurant server" for our connection between what our user will see and where our data is.

**/storage**: This is where our storage will be. We'll use something called sqlite for local storage

**/utils**: Utils isn't always neccessary, but we are going to be building an id generator for our little application, so things like that and other helper functions sit in this folder.

**/view**: Our view is the front end that the user will see. Things like our static files, our homepage, etc. will all come from here


