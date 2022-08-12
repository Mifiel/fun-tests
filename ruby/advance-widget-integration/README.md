# Advance Mifiel Widget* Integration

Mifiel customers have 3 different options to allow their users to sign a document:
1. Automatic: Customer sends us the file that needs to be signed and the emails of the required signers. Mifiel sends an email to the signers on the customer’s behalf and the signers sign in mifiel.com.
2. Simple Widget*: Customer send Mifiel a file to be signed and the information of the signers. They receive a widget_id which can be used in a javascript snippet to present the document and let the user sign within the site of the client.
3. Advance Widget*: Same way as "Simple Widget" but instead of sending the file, the customer sends only the *hash* and the name of the document. They have to send the file content to the snippet to be presented to the user. This offers maximum privacy to the customer and his users!

*The Widget refers to the front-end signing flow/views that clients can integrate into their own websites to create a white-labeled signing experience.
The customer is the business that uses Mifiel but the signers and the users are our customers´ clients

## Test

Build a small web app that creates a simple PDF, sends the hash and the name of the document to Mifiel and allow the user to sign using the widget  in the web app.

## Expected Flow

- Create PDF. It can be a simple as having user press a button that says “Crear PDF”. Make sure to create the PDF in the backend. 
- Send *SHA256 *hash** and *name* of the file and a *callback_url* (to receive events when all signers have signed) to mifiel.com
- Use the widget_id (from response in point 2) and the Base64 formatted content of the PDF and pass it to the snippet described in https://docs.mifiel.com/#tag/Embeber-widget-de-firma
- Present the widget with the document to the user so he can sign it.
- Mifiel will POST the document object when all the signers signed the document. The web app should catch this request and:
  * Fetch the signatures page from the server
  * Fetch the XML
  * Merge the signature page with the original file
  * Merge the PDF in the XML

## Notes

- The full description on how to make calls to the API is in https://docs.mifiel.com/#section/Introduccion, use the sandbox environment!. When you are ready to begin, ask us to give you some free docs so you can test without *Payment Required* errors.
- There is no time limit to deliver the solution but the speed will be taken into account.
- We encourage you to communicate as much as you can, so please don’t be afraid of asking questions. Remember, there is no such thing as a dumb question!

**Good luck!!**
