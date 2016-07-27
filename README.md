#Stroll Health API Documentation


##To find an endpoint:

If the microservice that contains the endpoint is known, simply select it on the left side menu. From the expanded list of endpoints belonging to that microservice, select the description that best fits the description of the endpoint in question. 

##To run an endpoint in shell:

Make sure to begin by getting a session token. You can do so by following steps in the "Authentication" section. Once a token is retrieved, use the curl command in the right section by replacing "meowmeowmeow" in the authorization header with your own token.

##To add/modify documentation:

1. Clone this repository to your own computer. 
2. Navigate to source folder.
3. Find a *.html.md file, where * is the name of the microservice for which you want to add/modify documentation.
4. Follow the template to add a new endpoint. Add a working curl command and wrap it in a shell formatted code box with github markdown language ('''shell). Add the corresponding response and wrap it in a json formatted code box ('''json). 
5. Add the name of the new request, as well as its description and HTTP format. For URL parameters, create a new table and specify the type of each parameter along with a short description. For POST request, include an additional table for the request body's parameters.

