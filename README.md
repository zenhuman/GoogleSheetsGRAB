# GoogleAppsScriptGRAB
Google Apps Script "Grab" is a backend script OR custom function that lets users "grab" any data in the HTML by designating the TEXT immediately before &amp; after the target data.  Regex. Multi-tool for data extraction.  Built for difficult extraction cases or where XML is unavailable.

CODE:

// **********************************************************************
//                            FUNCTION: GRAB
// **********************************************************************

// Grabs whatever text exists between two other texts using regex.
// Grab(url, foretext, aftertext)

function grab(url, foretext, aftertext) 
{
    var page = UrlFetchApp.fetch(url);
    var html = page.getContentText();
    var regex = foretext+"([^<>]+)"+aftertext
    var output = html.match(regex);
          if(output == null) {var output = null} else {output = output[1]};  
  return output;
}

