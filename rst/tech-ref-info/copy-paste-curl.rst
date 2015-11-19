.. _copy-paste-curl:

Copying and pasting cURL request examples into a terminal window
==================================================================

To run the cURL request examples shown in this guide on Linux or Mac
systems, perform the following actions:

1. Copy and paste each example from the HTML version of this guide into
   an ASCII text editor (for example, vi or TextEdit). You can click on
   the small document icon to the right of each request example to
   select it.

2. Modify each example with your required account information and so on,
   as detailed in this guide.

3. After you are finished modifying the text for the cURL request
   example with your information (for example, your username and your
   API key), paste the command into your terminal window.

4. Press **Enter** to run the cURL command.

..  note:: 
Note
The carriage returns in the cURL request examples that are part of the
cURL syntax are escaped with a backslash (\\) to avoid prematurely
terminating the command. However, you should not escape carriage returns
inside the JSON message within the command.

Consider the following cURL authentication request: JSON example, which
is described in detail in `Chapter 4, *Generating an authentication
token using cURL* <CBD_Generating_Auth_Token.html>`__.

 
**Example 3.1. cURL authenticate request: JSON**

.. code::  

    curl -i -d \
    '{
        "auth":
        {
           "RAX-KSKEY:apiKeyCredentials":
           {
              "username": "yourUserName",
              "apiKey": "yourApiKey"}
        }
    }' \
    -H 'Content-Type: application/json' \
    'https://identity.api.rackspacecloud.com/v2.0/tokens'

| 

Notice that the lines that are part of the cURL command syntax have been
escaped with a backslash (\\) to indicate that the command continues on
the next line.

.. code::  

    curl -i -d \
      
       
    (... lines within the JSON portion of the message are not shown in this example)
    (... the example only shows lines that are part of cURL syntax)     
         

       
    -H 'Content-Type: application/json' \
    'https://identity.api.rackspacecloud.com/v2.0/tokens'

However, the lines within the JSON portion of the message are not
escaped with a backslash to avoid issues with the JSON processing.

.. code::  

    '{
        "auth":
        {
           "RAX-KSKEY:apiKeyCredentials":
           {
              "username": "yourUserName",
              "apiKey": "yourApiKey"}
        }
    }' \

The final line of the JSON message is escaped because the backslash lies
outside the JSON message and continues the cURL command to the next
line.

..  tip:: 
		If you have trouble copying and pasting the examples as described, try
		typing the entire example on one long line, removing all the backslash
		line continuation characters.
