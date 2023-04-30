## Hi there 👋

This is Team Q and our project is document extraction and management.

Github Link: [https://github.com/DocXtract](https://github.com/DocXtract)
The above link can be used to access all the repositories of our final implementation. It includes:
1. ```pdf-manager```: The backend for the creation and organization of forms, responses, and organization. Also defines conversion and extraction.
2. ```web-portal```: The online portal where an organization can view responses to their forms in digital pdf or excel format.
3. ```mobile-app```: The mobile application where a member can view their forms, choose to print them, and respond by direct entry or scanning.

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->


### Contributions
#### 1. Peter Buonaiuto
  - Created the backend image processing. This includes
  1. Cropping of images to include only the exact size of the PDF
  2. Uploaded PDF to array of fields (includes their type, coordinate location, value and properties)
  3. Extracted fields back to digital PDF
  4. Extracted fields to excel or csv format of all responses
  5. Original uploaded PDF to printable. This is a function that adds borders around all fields. 
      - The purpose of this is to designate where the user can write so that the extraction will see their response. 
      - There is also a border generated on the outside of the document. This helps my cropping algorithm find the area of interest.
  6. I created a driver which demonstrates all functionality. It allows you to:
      - Quickly test changes to the backend functions by mimicking frontend input through direct function calls
      - Create organizations
      - Create members
      - Send invites to organizations and to forms
      - Respond to fields of a given selected form
      - Submit form responses
      - Convert response objects to digital PDFs
      - Convert forms to excel sheets or printable documents, prepared for extraction
  7. Object oriented program with representations of forms, fields, organizations, responses, requests and members
  8. Created an api which communicates with Muskaan's web and mobile segments to recieve images for processing and return the resulting PDF's and excel.
      - The api also is called by web and mobile to find all available forms for a given user, as well as display all responses.
  
  9. Muskaan and I together worked on the algorithm to take my cropped photo and extract all data from it.
      - I send her a list of all fields found in the document. Because this includes their coordinate location, we can compare the location of all text extracted by text extraction, and organize which responses go to which fields by comparing the coordinate locations of each response we find. 
      - Based on the metadata I send to Muskaan, we can determine if a field is a checkbox, signature, or text. We only try to extract the text if of course it is text. If it is a checkbox, we pass it to an algorithm I wrote which uses the coordinates of the checkbox and determines whether or not it is checked.
      - Similarly, signature fields will be saved as an image and appended to the final digital output to maintain the handwriting.

#### 2. Muskaan Shaikh
##### Mobile App
  - Implemented the entire mobile app which includes developing the pages Dashboard, Form Fill Type (Scan or Manual), Form Fill Page
  - Integrated camera module to allow images to be clicked from the app itself. Added flash feature within camera module
  - Used javascript to dynamically identify the type of input fields received from the server and display it on the mobile UI as html form input fields
  - Worked on the logic of segregating manual type forms with the forms which are scanned
  - Added a check of eliminating signature field for forms that are scanned and submitted
  - Pair programmed with Peter to integrate mobile app with the api servers built by him
  - Pair programmed with Moemen to add print functionality in the mobile app
  
##### Web App
  - Implemented the entire web app which includes developing the pages Dashboard which has list of forms and another page to display list of responses as well as the excel file
  - Implemented the feature of downloading a response from AWS S3 and integrated it with the viewing response as digital PDF built by Moemen
  - Pair programmed with Peter to integrate web app with the api servers built by him
  - Pair programmed with Moemen to add print functionality in the web app
  - Integrated the display excel module built by Moemen

##### Pdf Manager
  - Worked on the text extraction feature by integrating a third party API
  - Pair programmed with Peter to design an algorithm that maps rectangular coordinates from the extraction mentioned above with the rectangular coordinates from Peter's pdf extraction module class and decide which field key maps to what extracted value
  - Pair programmed with Peter in integrating all the apis with the mobile and web modules
 
#### 3. Moemen Elmegahed
  - Worked on viewing a pdf file in the browser
  - Worked on displaying an excel sheet in the form of table in the web app
  - Implemented the feature of downloading the table excel as an excel sheet
  - Pair programmed with Muskaan to work on the print functionality on the mobile and web app
  - Designed Figma Screens for the web app. (Couldn't be used because the web app eliminated the feature of adding members and users. Link for reference: [https://www.figma.com/file/nNxxip4qYl4KtLU8vThshZ/digiForm-AI-Screens?type=design&node-id=0%3A1&t=YZYw0P7L1b0VWgbf-1](https://www.figma.com/file/nNxxip4qYl4KtLU8vThshZ/digiForm-AI-Screens?type=design&node-id=0%3A1&t=YZYw0P7L1b0VWgbf-1))
  
#### 4. Devin O'Brien
 - Setup general infrastructure (Couldn't be used as lack of time and communication to migrate the apis on the infrastructure)
 - Initialized a DB and integrated CRUD operations (Couldn't be used as lack of time and communication to migrate the apis on the infrastructure)
 - Implemented web UI with features of adding members, adding users, creating profile, updating profile, viewing members, updating members (Couldn't be used because the web app eliminated the feature of adding members and users) 
 
#### 5. Dan Yee
 - Worked on api for CRUD operations on the database (Requested by Devin and then wasn't utilised as Devin worked on that whole part individually)
 - Implemented a drap and drop component in React (Requested by Muskaan and then not utilised as pdf upload feature was eliminated from final implementation. Component is useful and would be utilized while extending the project to allow organisations to upload a template form)
 
#### 6. Prudhvi Raj Bhashampally
 - Researched and worked on the original text extraction method. (Couldn't be used because it wasn't accurate)
 - Researched the original mobile printing method. (Couldn't be used because it was not tested and integrated, and didn't work with s3)
 
