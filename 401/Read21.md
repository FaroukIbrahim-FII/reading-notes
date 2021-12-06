# Django CRUD and Forms

## Overview

An HTML Form is a group of one or more fields/widgets on a web page, which can be used to collect information from users for submission to a server. Forms are a flexible mechanism for collecting user input because there are suitable widgets for entering many different types of data, including text boxes, checkboxes, radio buttons, date pickers and so on. Forms are also a relatively secure way of sharing data with the server, as they allow us to send data in POST requests with cross-site request forgery protection.

## HTML Forms

First a brief overview of HTML Forms. Consider a simple HTML form, with a single text field for entering the name of some "team", and its associated label:

![HTMLform](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms/form_example_name_field.png)

## Django form handling process

Django's form handling uses all of the same techniques that we learned about in previous tutorials (for displaying information about our models): the view gets a request, performs any actions required including reading data from the models, then generates and returns an HTML page (from a template, into which we pass a context containing the data to be displayed).

![DjangoForm](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms/form_handling_-_standard.png)

Based on the diagram above, the main things that Django's form handling does are:

* Display the default form the first time it is requested by the user.

    * The form may contain blank fields (e.g. if you're creating a new record), or it may be pre-populated with initial values (e.g. if you are changing a record, or have useful default initial values).
    * The form is referred to as unbound at this point, because it isn't associated with any user-entered data (though it may have initial values).
* Receive data from a submit request and bind it to the form.
    * Binding data to the form means that the user-entered data and any errors are available when we need to redisplay the form.
* Clean and validate the data.
    * Cleaning the data performs sanitization of the input (e.g. removing invalid characters that might be used to send malicious content to the server) and converts them into consistent Python types.
    * Validation checks that the values are appropriate for the field (e.g. are in the right date range, aren't too short or too long, etc.)
* If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.
* If all data is valid, perform required actions (e.g. save the data, send an email, return the result of a search, upload a file, etc.)
* Once all actions are complete, redirect the user to another page.

## Renew-book form using a Form and function view

Next, we're going to add a page to allow librarians to renew borrowed books. To do this we'll create a form that allows users to enter a date value.

### Form

The Form class is the heart of Django's form handling system. It specifies the fields in the form, their layout, display widgets, labels, initial values, valid values, and (once validated) the error messages associated with invalid fields.

### Declaring a Form

The declaration syntax for a Form is very similar to that for declaring a Model, and shares the same field types (and some similar parameters).

### Validation

Django provides numerous places where you can validate your data. The easiest way to validate a single field is to override the method clean_`<fieldname>()` for the field you want to check.

### View

As discussed in the Django form handling process above, the view has to render the default form when it is first called and then either re-render it with error messages if the data is invalid, or process the data and redirect to a new page if the data is valid.

## ModelForms

Creating a Form class using the approach described above is very flexible, allowing you to create whatever sort of form page you like and associate it with any model or models.

However, if you just need a form to map the fields of a single model then your model will already define most of the information that you need in your form: fields, labels, help text and so on.

## Generic editing views

The form handling algorithm we used in our function view example above represents an extremely common pattern in form editing views. Django abstracts much of this "boilerplate" for you, by creating generic editing views for creating, editing, and deleting views based on models.

![form](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms/forms_example_create_book.png)