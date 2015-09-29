{{+bindTo:partials.standard_store_article}}
# Publish in the Chrome Web Store

To publish your app to the Chrome Web Store, follow these steps:

1. Create your app’s zip file

2. Create a developer account

3. Upload your app

4. Pick a payments system

5. Get app constraints and finish your app’s code

6. Get the app ID

7. Get the OAuth token

8. Finish the app

9. Provide store content

10. Pay the developer signup fee

11. Publish your app

We’ll go into detail about each step below.

## Create your app’s zip file

To upload your app,
you need to create a ZIP file that contains at least one file:
your app's manifest.

Manifest files are .json files that contain important information
about your app. They contain the following:

* App name - Displayed in the Chrome Web Store and in the Chrome launcher
* Version - The version of the metadata, incremented

It should also contain a few images and any other files that the app requires.
The contents of the ZIP file and manifest
depend on the type of app you're writing and its capabilities.
For details, see the documentation for the type of app you're writing:

<table>
  <tr>
    <td>Required item</td>
    <td>Hosted apps</td>
    <td>Apps</td>
    <td>Themes</td>
    <td>Extensions</td>
  </tr>
  <tr>
    <td>Manifest file</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Background script</td>
    <td>Yes</td>
    <td>Yes</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Window page</td>
    <td></td>
    <td>Yes</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Icons</td>
    <td>Yes</td>
    <td>Yes</td>
    <td></td>
    <td></td>
  </tr>
</table>

**Tips:**

* Set the initial
[version number](https://developer.chrome.com/extensions/manifest.html#version)
in the manifest to a low value, such as 0.0.0.1.
That way, you have room to increase the version number
when you upload new versions of your app.
* If your packaged app or extension uses
[Native Client](https://developers.google.com/native-client/),
you can structure your application directory hierarchy and ZIP file
in a way that reduces the size of the user download package.
For details, see
[Reducing the size of the user download package](https://developer.chrome.com/native-client/devguide/distributing#reducing-the-size-of-the-user-download-package).

Before you upload your app,
you’ll be asked to pick a developer account
to both own your apps and receive payments.
Instead of your personal account, we suggest using a dedicated account.

## Create a developer account

We suggest using a new account just for your app
instead of your personal account.

If you want to publish a hosted app,
you'll need to prove that your developer account owns the URLs
that comprise the app.
Visit the Google Webmaster Tools Help Center for information on
[proving site ownership](http://www.google.com/support/webmasters/bin/answer.py?hl=en&answer=34592).

If you already host your app in Google Play and you want
your Chrome Web Store app listing to show an "Available for Android" link,
your app must have the same name as your Google Play listing,
and both apps must be owned by the same developer account.
To transfer your Chrome Web Store app to a different developer,
submit this
[form](https://support.google.com/chrome_webstore/contact/dev_account_transfer).

## Upload your app

To upload your app, use the Chrome Developer Dashboard.

If you need the app ID or an OAuth access token to complete your app's code,
then you need to upload the app while you're still writing its code.
Otherwise, you can wait until the app is finished.
You can upload your app many times before publishing it.

When your app, its Chrome Web Store listing,
and all the sites it relies on are ready, you can publish your app.
You can publish up to 20 applications on Chrome Web Store.

Here's how you upload your app:

1. Go to the
[Chrome Developer Dashboard](https://chrome.google.com/webstore/developer/dashboard).

2. Sign into the developer account you chose in Step 1.

3. Click the **Add new item** button. 

4. If you've never uploaded an item before,
you need to accept the developer agreement before going to the next step.

5. Click **Choose file** > your zip file > **Upload**.
If your app's manifest and ZIP file are valid,
you can edit your app on the next page.

## Pick a payment system

If you aren't going to use Chrome Web Store Payments,
you can delay or (for free apps) omit this step.

If you want to charge for your app,
set its price and payment system
through the dashboard's edit page for your app.

To use Chrome Web Store Payments,
you also need to signup your developer account as a Google Checkout merchant,
and you need to associate your merchant account with the store.
For details, see
[Register for a Google Checkout Merchant account](https://developer.chrome.com/webstore/money).

## Provide store content

Add the store listing information for your app that isn't in the ZIP file,
such as a long description, screenshots, videos, and links to related sites.
You’ll need the following to finish your app’s store listing:

* A **detailed description** of your application.
Write your description to entice users to download your app.
* A 128x128 **icon** to display in the store.
You may re-use your app icon here.
* At least one 1280x800 or 640x400 **screenshot** or YouTube **video**
to show off what your app does.
* A 440x280 **small tile icon** that will be displayed
on the Chrome Web Store wall.
* The **primary category** where your app should be listed.
* Your app's **language** to help users find it.

See
[Supplying Images](https://developer.chrome.com/webstore/images.html)
for help on designing the images for your app, and
[Branding Guidelines](https://developer.chrome.com/webstore/branding.html)
for information on how you can use Google brands.

## Pay the developer signup fee

Before you publish your first app,
you must pay a one-time $5 developer signup fee.
A reminder in the dashboard will appear until you pay the fee.

For more information, including troubleshooting tips, see the
[Registration article](http://www.google.com/support/chrome_webstore/bin/answer.py?answer=187591).

## Get app constraints and finish your app’s code

When you publish your app, you’ll get an app ID.
If you make requests to Google APIs, you’ll need this information.
For example, if you need the
[licensing API](https://developer.chrome.com/webstore/get_started),
you’ll need the app ID.

To get the app ID or OAuth token for your app’s code, follow the steps below:

### Get the app ID

The app ID appears in the URL of any dashboard or store page for your app.
You’ll need the app ID if you want to use the Licensing API.

For example, the URL
"https://chrome.google.com/extensions/detail/aaaaaaaaaabbbbbbbbbbcccccccccc?hl=en" has the app ID “aaaaaaaaaabbbbbbbbbbcccccccccc.”

### Get the OAuth token

If you want to use Chrome Web Store Payments, you’ll need an
[OAuth access token and access token secret](https://developer.chrome.com/webstore/check_for_payment.html#token).

### Finish the app

Now you can add any code that refers to the app ID or OAuth access token
to complete your app.

You can update your app as many times as you want,
just remember to increase the version number each time.

Before you publish your app, verify that everything is working properly:

1. On the edit page, click **Preview changes** and
check that the listing looks great and has all the info that it should.

2. Check that the app and any websites and supporting pages all work.

3. Publish any new websites and supporting pages that your app needs to work.

4. Publish your app.
You can choose the audience for your app using the information below:

## Publishing to test accounts

When you publish to test accounts,
your app’s store listing only appears to you and any users
who are logged into these test accounts that you specify.
Your app won’t appear in search results,
so you’ll need to give testers a direct link to your app’s listing.
Testing also gives you a chance to see how the license server integrates
with your app if you plan to charge your it using Chrome Web Store Payments.

To edit your list of accounts, click **Edit your tester accounts**.
You can enter single accounts, or
create a Google Group so that this set of users can test your app.

Once you’re ready to publish,
click **Publish to test accounts**.

You’ll need to unpublish the app if you want to publish to the world later.

## Publishing to the world

When you publish to the world,
it’ll be immediately visible to the world,
and it’ll be visible in the store’s search results.

You can select the regions that you want to support,
[pick your app’s price in each region](https://developer.chrome.com/webstore/pricing#matrix)
(if you use Chrome Web Store Payments), and
[internationalize your app](https://developer.chrome.com/webstore/i18n).

To publish to the world, click **Publish** next to your app.
You can also visit the dashboard’s edit page and click **Publish changes**.

## Publishing on Google Play for Education

If you build an app for K-12 education,
you can opt in to Google Play for Education.

Google Play for Education is a separate store
that lets educators find, buy, and deploy apps to their students with just a few clicks.
Learn more about publishing in
[Google Play for Education](http://developer.android.com/distribute/googleplay/edu/start.html).
{{/partials.standard_store_article}}
