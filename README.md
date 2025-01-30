The template allows collecting user data from forms and utilizing it for marketing and analytics tools.

It is primarily intended for marketers and analysts who want to work with users' personal data—such as emails, phone numbers, and more—in advertising or analytics systems but do not have access to a developer to obtain this data. Additionally, the template monitors whether consent for the use of personal data (ad_user_data) is enabled on the website, ensuring compliance with user consent according to current legal requirements.

> [!WARNING]  
> Please note that when the website restricts Content Security Policy, the functionality can be blocked. You can allow domain `taste.cz*` in that case.

# Implementation
In the GTM Templates menu, create a new template (Tag type), select Import, upload the .tpl file, and save it.

Then, create a new Tag and select the tag type User data form extraction.

## Setup
To collect user data, you need to configure several settings in the template.

### User parameters – settings
#### Form restriction
If your page contains multiple forms, you can restrict data collection to a specific form using CSS selectors.

For example, to limit data collection to a form with the ID `form-contact`, enter `#form-contact` in the selector field. Similarly, if you want to target a class attribute, use `.form-contact`.

If you don’t want to restrict forms, leave the field empty.

#### User parameters
Here you can ad desired user parameters that should be extracted from the form fields. 

Let's say you want to extract an email and the form in HTML looks like this:

![Form HTML](https://taste.cz/images/gtm-template-example.png)

In this case you would add new row to the template, choose `E-mail` as a _User parameter_ and `id="email"` or `name="email"` as a _Value_.

### Settings
Choose the desired location to save the user data. You can choose localStorage, sessionStorage, cookie and dataLayer.

#### Replace values
You can also choose how to behave if there are some user data already saved. 
1. **If a new value is to be stored, the whole object is replaced.**
2. **Replace only the new values, keep the others unchanged.**
3. **If the object already exists, do not save anything new.**

## Trigger
Create a new trigger that would fire in the moment of clicking to a submit button of the form and set it as a trigger for the tag.

## Next steps
After the deployment of the template you can easily check if the user data is collected successfuly in the location you chose earlier (localStorage, cookie, ...).

You can easily access this data with Custom Javascript variable and use it e.g. for Google Enhanced Conversions.
