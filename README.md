<h2 id="top">Top of page!</h2>
<a href="#actionBar">Action Bar Def</a>


#Page Info Configuration Document:

The “PageInfo” specification is part of the “page” specification defined in the facility/settings for each facility. PageInfo specification is made up of Title, Toolbar, BreadCrumb, Site Search and Action Bar.

> *Site Search in pageInfo is disabled in the code due to the reason that in the latest iteration of the Labshare design it has been moved to the header. Therefore, changes to the site search settings would not have any effect.*

Below is the placement of PageInfo inside the page specification:

      "page": {
          "Login": {…},
          "Header": {…},
          "Footer": {…},
          "Theme": {…},
          "PageInfo": {
              "disabled": Boolean,
              "Height": "Text",
              "Theme": "Text",
              "pageTitle": […],
              "BreadCrumb": […],
              "siteSearch": […],
              "toolbar": {…},
              "actionBar": {…}
      },   

###Properties:
1.  <a href="#disabled">disabled</a> : Boolean
2.  <a href="#Height">Height</a> : text
3.  <a href="#Theme">Theme</a> : text
4.  <a href="#pageTitle">pageTitle</a> : array of objects.  
    1. <a href="#showPageTitle">showPageTitle</a> : Boolean
    2. <a href="#title">title</a> : text
    3. <a href="#position">position</a> : text
    4. <a href="#fontStyle">fontStyle</a> : Choice
        1. choices : array
    6. <a href="#fontSize">fontSize</a> : Choice
        1. choices : array
    8. <a href="#fontColor">fontColor</a> : color
    9. <a href="#customImage">customImage</a> : File
5.  <a href="#BreadCrumb">BreadCrumb</a> : array of objects.
    1. <a href="#Enable">Enable</a> : Boolean
    2. <a href="#showBreadcrumbInhomePage">showBreadcrumbInhomePage</a> : Boolean
        1. <a href="#fontSize">fontSize</a> : Choice
            1. choices : array
    3. <a href="#pageInfoBottom">pageInfoBottom</a> : Boolean
6.  <a href="#siteSearch">siteSearch</a> : array of objects.
    1. <a href="#PlaceHolder">PlaceHolder</a> : text
    2. <a href="#Enable">Enable</a> : Boolean
    3. <a href="#Height">Height</a> : Number
    4. <a href="#Width">Width</a> : Number
7.  <a href="#toolbar">toolbar</a>
    1. <a href="#Enable">Enable</a> : Boolean
    2. <a href="#ToolbarList">ToolbarList</a> : array of objects.
        1. “Cancel”: Take user back to the previous UI state.
        2. “Save”: Broadcasts event ‘submit’.
        3. “Save as Draft”: Broadcasts event ‘draft’.
        4. “Delete”: Broadcasts event ‘delete’.
        5. “Edit”: Broadcasts event ‘edit’.
        6. “Share”: Broadcasts event ‘share’.
        7. “Favorite”: Broadcasts event ‘favorite’.
        8. “Copy”: Broadcasts event ‘copy’.
        9. “New”: Broadcasts event ‘new’.
        10. “Print”: Broadcasts event ‘print’.
        11. “Member”: Opens up the Project Member form.
        12. “Assign”: Opens up the assign to form.
        13. “Approve”: Broadcasts event ‘approve’.
        14. “Reject” : Broadcasts event ‘reject’.
8.  <a href="#actionBar">actionBar</a>
    1. <a href="#Enable">Enable</a> : Boolean
    2. <a href="#actionList">actionList</a> : array of objects.
        1. button 1 : configurable button with configurable action.
        2. button 2 : configurable button with configurable action.
        3. button 3 : configurable button with configurable action.
        4. button 4 : configurable button with configurable action.


<a href="#top">Go to top</a>

##Dictonary of Terms

<dl id="actionBar">
  <dt>actionBar</dt>
  <dd>Type: "object" </br>
      Description: Is used for NCATLYST mobile app only. Activates the action bar icon, back button icon & action bar menu.</dd>
</dl>

<dl id="actionList">
  <dt>actionList</dt>
  <dd>Type: "array of objects" </br>
      Description: An array of objects. Each object represents an action icon button in the action menu. Each object has properties Name, Icon, styles and Trigger. The only configurable properties are Icon & styles. You can specify a font awesome icon class in the Icon property or you can specify an background image path in the styles property.
      <table>
          <tr>
              <th>label</th>
              <th>value</th>
              <th>Type</th>
              <th>Required</th>
          </tr>
          <tr>
              <td>style</td>
              <td>This object has the property “background-image” which would take a URL path for the image file.</td>
              <td>Object</td>
              <td>Yes</td>
          </tr>
          <tr>
              <td>Icon</td>
              <td>Icon that would appear on the button. Should be a font awesome icon class.</td>
              <td>Text</td>
              <td>No</td>
          </tr>
      </table>
      </dd>
</dl>

<dl id="BreadCrumb">
  <dt>BreadCrumb</dt>
  <dd>Type: "array of objects" </br>
      Description: Each objects has the properties <b>required</b> label and value.
      <table>
          <tr>
              <th>label</th>
              <th>value</th>
              <th>Type</th>
              <th>Required</th>
          </tr>
          <tr>
              <td>Enable</td>
              <td>True or false – for controlling breadcrumb</td>
              <td>Boolean</td>
              <td>Yes</td>
          </tr>
          <tr>
              <td>fontSize</td>
              <td>Any value applicable to font-size CSS property e.g “16px”</td>
              <td>Text</td>
              <td>No</td>
          </tr>
          <tr>
              <td>pageInfoBottom</td>
              <td>True/false – used for controlling breadcrumb to show on pageInfo bottom panel</td>
              <td>Boolean</td>
              <td>No</td>
          </tr>
          <tr>
              <td>pageInfoTop</td>
              <td>True/false – used for controlling breadcrumb to show on pageInfo top panel</td>
              <td>Boolean</td>
              <td>No</td>
          </tr>
      </table>
      </dd>
</dl>

<dl id="customImage">
  <dt>customImage</dt>
  <dd>Type: "File" </br>
      Description: Image URL Text No</dd>
</dl>

<dl id="disabled">
  <dt>disabled</dt>
  <dd>Type: "boolean" </br>
      Description: Used to disable / Enable PageInfo</dd>
</dl>

<dl id="fontColor">
  <dt>fontColor</dt>
  <dd>Type: "Choice" </br>
      Description: Any value applicable to color CSS property e.g “white”. Should be left blank if Theme is being used. Text No</dd>
</dl>

<dl id="fontSize">
  <dt>fontSize</dt>
  <dd>Type: "Choice" </br>
      Description: Any value applicable to font-size CSS property e.g “16px” Text No</dd>
</dl>

<dl id="fontStyle">
  <dt>fontStyle</dt>
  <dd>Type: "Choice" </br>
      Description: Any value applicable to font-style CSS property e.g “italics” Text No</dd>
</dl>

<dl id="Height">
  <dt>Height</dt>
  <dd>Type: “string”
      </br>
      Description: This property is only effective if pageTitle or Toolbar are enabled. Used to set the height of PageInfo panel. Options available are “short” or “tall”. Leaving this field empty would resolve the height to “short”. Below table shows the pixel value to which the height is resolved for setting each option.
      <ul>
        <li>"short" = 100px</li>
        <li>"tall" = 120px</li>
      </ul>
      </dd>
</dl>

<dl id="pageTitle">
  <dt>pageTitle</dt>
  <dd>Type: “array”
      </br>
      Description: This is an array of objects. Each objects has the <b>required</b> properties "label" and "value".
      <table>
          <tr>
              <th>label</th>
              <th>value</th>
              <th>Type</th>
              <th>Required</th>
          </tr>
          <tr>
              <td>showPageTitle</td>
              <td>True/false – for controlling pageTitle</td>
              <td>Boolean</td>
              <td>Yes</td>
          </tr>
          <tr>
              <td>title</td>
              <td>Title of the page</td>
              <td>Text</td>
              <td>No</td>
          </tr>
          <tr>
              <td>position</td>
              <td>Could be one of the following: “start center”, “center center” or “end center”</td>
              <td>Text</td>
              <td>Yes</td>
          </tr>
          <tr>
              <td>fontStyle</td>
              <td>Any value applicable to font-style CSS property e.g “italics”</td>
              <td>Text</td>
              <td>No</td>
          </tr>
          <tr>
              <td>fontSize</td>
              <td>Any value applicable to font-size CSS property e.g “16px”</td>
              <td>Text</td>
              <td>No</td>
          </tr>
          <tr>
              <td>fontColor</td>
              <td>Any value applicable to color CSS property e.g “white”. Should be left blank if Theme is being used.</td>
              <td>Text</td>
              <td>No</td>
          </tr>
          <tr>
              <td>customImage</td>
              <td>Image URL</td>
              <td>Text</td>
              <td>No</td>
          </tr>
      </table>
      </dd>
</dl>

<dl id="pageInfoBottom">
  <dt>pageInfoBottom</dt>
  <dd>Type: “boolean”
      </br>
      Description: This is used for controlling breadcrumb to show on pageInfo bottom panel</dd>
</dl>

<dl id="pageInfoTop">
  <dt>pageInfoTop</dt>
  <dd>Type: “boolean”
      </br>
      Description: This is used for controlling breadcrumb to show on pageInfo top panel</dd>
</dl>

<dl id="position">
  <dt>position</dt>
  <dd>Type: “string”
      </br>
      Description: This could be one of the below: Text Yes
      <ul>
        <li>“start center”</li>
        <li>“center center”</li>
        <li>“end center”</li>
      </ul>
      </dd>
</dl>

<dl id="showPageTitle">
  <dt>showPageTitle</dt>
  <dd>Type: “boolean”
      </br>
     Description: For controlling pageTitle Boolean Yes</dd>
</dl>

<dl id="title">
  <dt>title</dt>
  <dd>Type: “string”
      </br>
     Description: Title of the page Text No/dd>
</dl>

<dl id="ToolbarList">
  <dt>ToolbarList</dt>
  <dd>Type: “array of objects”
      </br>
     Description: Each object represents a toolbar button. Each objects has the properties name, icon, enable, trigger & role. The only configurable properties are name, icon, enable & role.
     <table>
         <tr>
             <th>label</th>
             <th>value</th>
             <th>Type</th>
             <th>Required</th>
         </tr>
         <tr>
             <td>Name</td>
             <td>The name which would appear on the button</td>
             <td>Text</td>
             <td>Yes</td>
         </tr>
         <tr>
             <td>Icon</td>
             <td>Icon that would appear on the button. Should be a font awesome icon class.</td>
             <td>Text</td>
             <td>No</td>
         </tr>
         <tr>
             <td>Enable</td>
             <td>True or false – for controlling button</td>
             <td>Boolean</td>
             <td>Yes</td>
         </tr>
         <tr>
             <td>Role</td>
             <td>Array list of roles that are allowed to view the button</td>
             <td>Array</td>
             <td>Yes</td>
         </tr>
     </table>
     </dd>
</dl>

<dl id="Theme">
  <dt>Theme</dt>
  <dd>Type: “string”
      </br>
      Description: This property chooses a theme for the PageInfo panel by affecting the color and style. Choose either “default” or the specific theme.</dd>
</dl>


