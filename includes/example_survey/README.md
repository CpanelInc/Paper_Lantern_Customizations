# How to create a survey to use in cPanel Paper Lantern

Below are the steps that a reseller can take to add a survey for cPanel accounts using the Paper Lantern theme.

## Steps
1. Create a Survey using a Survey Provider and Get the Survey Embed Code

    There are several companies that offer surveys (SurveyMonkey, Polldaddy, etc.). Creating a survey will largely depend on what company you use. I would suggest following the instructions the survey company provides for creating surveys. One thing to consider when choosing a survey provider are the options they provide for embedding a survey into a site.

    After you have created your survey, you will need to decide on how you want to embed the survey on your site. When you have decided on the embedding method, copy the embedding code provided by your survey provider.

    In our demo UI Include, we will be using [Polldaddy](https://polldaddy.com) as our survey provider and their "Slider Popup" implementation for embedding the survey.

2. Create the UI Include on Your Server

    We are going to inject the survey into the home page for accounts using the Paper Lantern theme of cPanel.
    
    Log in to your server.

    - If you are a reseller and want to show this survey to your users
    
        Create a file called `home_page_footer.html.tt` in `/home/username/var/cpanel/reseller/includes/` where username is your username on the server.

    - If you are an administrator and want to show this survey to all users
    
        Create a file called `home_page_footer.html.tt` in `/var/cpanel/customizations/includes/`.

    Open the file in an editor.

    Paste the survey embed code into the editor.

    NOTE:
    To avoid any issues with jQuery not being loaded, we recommend wrapping any code that injects a script tag into the DOM be wrapped in a `setTimeout`. For example:
    
```
// Add a setTimout here around the JSONP request to avoid race conditions with jQuery
window.setTimeout(function() {
    // original embedding code from polldaddy
(function(d,c,j){if(!document.getElementById(j)){var pd=d.createElement(c),s;pd.id=j;pd.src=('https:'==document.location.protocol)?'https://polldaddy.com/survey.js':'http://i0.poll.fm/survey.js';s=document.getElementsByTagName(c)[0];s.parentNode.insertBefore(pd,s);}}(document,'script','pd-embed'));
    // end of original embedding code from polldaddy
}, 1000); // we are setting this timeout to occur after 1 second
```

## Notes

Now you should be able to log in a cPanel account you own on the server where you added your survey and see the survey popup.

For more information about UI Includes, see our [documentation](https://documentation.cpanel.net/display/SDK/Guide+to+cPanel+Interface+Customization+-+UI+Includes).

