# Fusion Development

This repository contains a demo project for showing what can be built using fusion development. The project is called "Idea Management" and is meant to streamline the product ideation process by providing an easy to use interface and an ai-assisted approach to ideation. More specifically, it features:
- A Fluent-UI based user interface that is built by using PCF components.
- A structured way to have an ideation process.
- AI-assisted idea generation by using openAI. It allows for generating an idea description and image using AI.
- AI-assisted idea selection by using Power Platform AI Builder. The models are used to extract sentiment and key words from reviews.

> Note that this project is purely meant as a demo.

## How to deploy the project


### Prerequisites
- A Power Platform environment which allows PCF components to be used. You can turn on this setting in the admin center of the Power Platform as follows: 
  - Go to the target environment in the Power Platform admin center.
  - Select settings -> product -> features.
  - Enable "Allow publishing of canvas apps with code components".
- A (trial) license for AI Builder.
- An openAI API key. You can get one via [https://openai.com/api/](https://openai.com/api/).
- An application user in the environment with admin access, for a tutorial on how to create one, see [https://learn.microsoft.com/en-us/power-platform/admin/manage-application-users](https://learn.microsoft.com/en-us/power-platform/admin/manage-application-users).

### Deploying the solution
To deploy the solution, you should fork the repo and create an environment by going to settings -> environments. This environment will be used in the workflow to deploy the solution. In this environment, create the following 4 variables:

```html
CLIENT_ID = {The client id of your application user}
CLIENT_SECRET = {The client secret of your application user}
ENVIRONMENT_URL = {The URL of the target environment, you can get this from the Power Platform admin center}
TENANT_ID = {Tenant ID of your tenant}
```

After you set-up the environment and the variables, you can run the workflow "Deploy idea management" by going to actions, selecting the flow and specifying your environment. If your environment does not have the Creator Kit installed, check the box to install this as well, as the project has a dependency on this solution. Now, the project should install as a managed solution.

### Setting up the connection to openAI
After installing the solution, you should alter the connection reference for the openAI connector by going to the Idea Management solution and changing the "OpenAI CR" to point to your own openAI connection. When creating this connection, the API Key should be as follows: `Bearer {your API key}`.

Now, you can share the idea management app with other users and start using the app.
