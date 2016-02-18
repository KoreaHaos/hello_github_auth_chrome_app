# hello_github_auth_chrome_app

#### First,

Get the bits we need from Google's App [Samples](https://github.com/GoogleChrome/chrome-app-samples).

You can copy and run the script below;

```bash
mkdir github_auth_temp
cd github_auth_temp
git init
git remote add -f origin https://github.com/GoogleChrome/chrome-app-samples.git
git config core.sparseCheckout true
echo "samples/github-auth" >> .git/info/sparse-checkout
git pull origin master
cd ..
mkdir github_auth_app
cp -r github_auth_temp/samples/github-auth/* github_auth_app/
zip -r github_auth_app github_auth_app
rm -rf github_auth_temp
```

or even easier, `bash` the sensibly titled `get_googles_github_auth_sample_app.bash` file.

The script does a sparseCheckout of the files needed and since they are buried several folders down, it copies what's needed to a more convient directoy, removes the temporary duplicate, and as an added bonus, zips up the files so they are ready to be loaded up as an extension.

* Download those files to wherever you are going to try out the extension.
* Fire up Chrome.
* In Chrome, click the settings button. It looks like this : ![](img/chrome_settings_button.png), and is most likely in the upper right corner of the chrome browser. 
* Scroll down a bit in the settings menu and hover over the `More tools` selector.
* In the pop-up menu that appears, click extensions.
* On the extensions page, click the developer mode check-box.
* NOTE - If you don't see the developer mode check-box, enable it by opening a new tab and browsing to : [chrome://flags](chrome://flags) and enabling "Experimental Extension APIs".
* Once that's all done, click the ![load extension button](img/load_extension_button.jpg), select the unziped folder you downloaded a bit ago, and hit run.
* That's it!

You've just created, from source, a chrome extension that uses one of the more complicated authetication schemes and does so in a way they does not require a server or an app id.

Pretty nice, right?
