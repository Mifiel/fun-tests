# Advance Mifiel Widget\* Integration

Mifiel allows its customers to integrate an electronic signing flow completely within their websites. The signatures are made by using the e.firma, a pair of flies (one being very sensitive) that people get from SAT.
One of the files of the e.firma must never leave the signer’s device which essentially means that the signature must be handled in the front end (browser) in order to guarantee that the e.firma’s sensitive file never touches the customer’s server nor Mifiel’s server.
To achieve this, Mifiel offers its customers a javascript widget or snippet that securely handles the e.firma files on the signer’s browser. The widget has two main functionalities. First, it presents the document to be signed for its review. Second, allows the signer to securely sign the document.

There are two ways to integrate Mifiel’s widget:

Simple Widget: The customer sends Mifiel, via our API, a file to be signed and the information of the signers. For each signer, Mifiel returns a unique widget id which needs to be passed to Mifiel’s signing widget so the correct document is passed to the widget and displayed to the appropriate signer. For example, if you create a document with two signers, Mifiel returns two unique widget ids, one for each signer.

**Advance Widget\***: Same way as "Simple Widget" but instead of sending the file to Mifiel, the customer sends the hash (sha256) and the name of the document. This is done to avoid sharing the document with Mifiel which could contain sensitive information. Since the document is not shared with Mifiel, when the widget is presented to the signer, the file to be signed has to be also passed to the widget so the signer can review the document before signing.

## Test

Build a small web app that creates a simple PDF, sends the hash (sha256) and the name of the document to Mifiel and allows the user to sign using the widget in the web app.

## Expected Flow

- Create PDF. It can be as simple as having the user press a button that says "Crear PDF". Make sure to create the PDF in the backend.
- Send SHA256 `hash` and `name` of the file as well as a `callback_url` (to receive events regarding the status of the document) to Mifiel.
- Use the widget_id (from response in point 2) and the Base64 formatted content of the PDF and pass it to the snippet described in https://docs.mifiel.com/#tag/Embeber-widget-de-firma
- Present the widget with the document to the user so he can sign it.
- Sign the document using your e.firma or a test e.firma (you can issue one at https://pki-sandbox.mifiel.com).
- When you sign, Mifiel will make a POST to your web app. The web app should catch this request and:
  - Fetch the signatures page from the server
  - Fetch the XML
  - Merge the signature page with the original file
  - Merge the PDF in the XML

## Notes

- The full description on how to make calls to the API is in https://docs.mifiel.com/#section/Introduccion, use the sandbox environment!. When you are ready to begin, ask us to give you some free docs so you can test without _Payment Required_ errors.
- There is no time limit to deliver the solution but the speed will be taken into account.
- We encourage you to communicate as much as you can, so please don’t be afraid of asking questions. Remember, there is no such thing as a dumb question!

**Good luck!!**
