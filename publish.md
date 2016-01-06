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

To upload your app, you need to create a ZIP file that contains at least one file: your app's manifest.

Manifest files are .json files that contain important information about your app. They contain the following:

* App name - Displayed in the Chrome Web Store and in the Chrome launcher
* Version - The version of the metadata, incremented

It should also contain a few images and any other files that the app requires. The contents of the ZIP file and manifest depend on the type of app you're writing and its capabilities. For details, see the documentation for the type of app you're writing:

<table>
  <tr>
    <td><strong>Required item</strong></td>
    <td><strong>Hosted apps</strong></td>
    <td><strong>Apps</strong></td>
    <td><strong>Themes</strong></td>
    <td><strong>Extensions</strong></td>
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

* Set the initial [version number](https://developer.chrome.com/extensions/manifest.html#version) in the manifest to a low value, such as 0.0.0.1. That way, you have room to increase the version number when you upload new versions of your app.
* If your packaged app or extension uses [Native Client](https://developers.google.com/native-client/), you can structure your application directory hierarchy and ZIP file in a way that reduces the size of the user download package. For details, see [Reducing the size of the user download package](https://developer.chrome.com/native-client/devguide/distributing#reducing-the-size-of-the-user-download-package).

Before you upload your app, you’ll be asked to pick a developer account to both own your apps and receive payments. Instead of your personal account, we suggest using a dedicated account.

## Create a developer account

We suggest using a new account just for your app instead of your personal account.

If you want to publish a hosted app, you'll need to prove that your developer account owns the URLs that comprise the app. Visit the Google Webmaster Tools Help Center for information on [proving site ownership](http://www.google.com/support/webmasters/bin/answer.py?hl=en&answer=34592).

If you already host your app in Google Play and you want your Chrome Web Store app listing to show an "Available for Android" link, your app must have the same name as your Google Play listing, and both apps must be owned by the same developer account.
To transfer your Chrome Web Store app to a different developer, submit this [form](https://support.google.com/chrome_webstore/contact/dev_account_transfer).

## Upload your app

To upload your app, use the Chrome Developer Dashboard.

If you need the app ID or an OAuth access token to complete your app's code, then you need to upload the app while you're still writing its code. Otherwise, you can wait until the app is finished. You can upload your app many times before publishing it.

When your app, its Chrome Web Store listing, and all the sites it relies on are ready, you can publish your app. You can publish up to 20 applications on Chrome Web Store.

Here's how to upload your app:

1. Go to the [Chrome Developer Dashboard](https://chrome.google.com/webstore/developer/dashboard).

2. Sign into the developer account you chose in Step 1.

3. Click the **Add new item** button. 

4. If you've never uploaded an item before, you need to accept the developer agreement before going to the next step.

5. Click **Choose file** > your zip file > **Upload**. If your app's manifest and ZIP file are valid, you can edit your app on the next page.

## Pick a payment system

If you aren't going to use Chrome Web Store Payments, you can delay or (for free apps) omit this step.

If you want to charge for your app, set its price and payment system through the dashboard's edit page for your app.

To use Chrome Web Store Payments, you also need to signup your developer account as a Google Checkout merchant, and you need to associate your merchant account with the store. For details, see [Register for a Google Checkout Merchant account](https://developer.chrome.com/webstore/money).

## Provide store content

Add the store listing information for your app that isn't in the ZIP file, such as a long description, screenshots, videos, and links to related sites. You’ll need the following to finish your app’s store listing:

* A **detailed description** of your application. Write your description to entice users to download your app.
* A 128x128 **icon** to display in the store. You may re-use your app icon here.
* At least one 1280x800 or 640x400 **screenshot** or YouTube **video** to show off what your app does.
* A 440x280 **small tile icon** that will be displayed on the Chrome Web Store wall.
* The **primary category** where your app should be listed.
* Your app's **language** to help users find it.

See [Supplying Images](https://developer.chrome.com/webstore/images.html) for help on designing the images for your app, and [Branding Guidelines](https://developer.chrome.com/webstore/branding.html) for information on how you can use Google brands.

## Pay the developer signup fee

Before you publish your first app, you must pay a one-time $5 developer signup fee. A reminder in the dashboard will appear until you pay the fee.

For more information, including troubleshooting tips, see the [Registration article](http://www.google.com/support/chrome_webstore/bin/answer.py?answer=187591).

## Get app constraints and finish your app’s code

When you publish your app, you’ll get an app ID. If you make requests to Google APIs, you’ll need this information. For example, if you need the [licensing API](https://developer.chrome.com/webstore/get_started), you’ll need the app ID.

To get the app ID or OAuth token for your app’s code, follow the steps below:

### Get the app ID

The app ID appears in the URL of any dashboard or store page for your app. You’ll need the app ID if you want to use the Licensing API.

For example, the URL "https://chrome.google.com/extensions/detail/aaaaaaaaaabbbbbbbbbbcccccccccc?hl=en" has the app ID “aaaaaaaaaabbbbbbbbbbcccccccccc.”

### Get the OAuth token

If you want to use Chrome Web Store Payments, you’ll need an [OAuth access token and access token secret](https://developer.chrome.com/webstore/check_for_payment.html#token).

### Finish the app

Now you can add any code that refers to the app ID or OAuth access token to complete your app.

You can update your app as many times as you want, just remember to increase the version number each time.

Before you publish your app, verify that everything is working properly:

1. On the edit page, click **Preview changes** and check that the listing looks great and has all the info that it should.
2. Check that the app and any websites and supporting pages all work.
3. Publish any new websites and supporting pages that your app needs to work.
4. Publish your app. You can choose the audience for your app using the information below:

## Publishing to test accounts

When you publish to test accounts, your app’s store listing only appears to you and any users who are logged into these test accounts that you specify. Your app won’t appear in search results, so you’ll need to give testers a direct link to your app’s listing. Testing also gives you a chance to see how the license server integrates with your app if you plan to charge your it using Chrome Web Store Payments.

To edit your list of accounts, click **Edit your tester accounts**. You can enter single accounts, or create a Google Group so that this set of users can test your app. See the section below to learn how to set up Group Publishing.

Once you’re ready to publish, click **Publish to test accounts**.

You’ll need to unpublish the app if you want to publish to the world later.

## Set up Group Publishing

You can share ownership of your items in Google Chrome Web Store with other developers by setting up group publishing. With group publishing, you can add developers to a Google Group, who can then act on your behalf. They'll have access to all the items you own and can make any changes to them that you can make.

### Before you set up group publishing

Keep these important notes in mind:

* Creating a Group Publisher is not reversible: a new Group Publisher account is created and the Google Group you select is permanently linked to that account.
* You cannot change which group is linked to the Group Publisher account.
* You still retain your personal publishing account and can publish from either your group or personal account.

### Set up group publishing

To set up group publishing, follow these steps:

1. Sign in to your [Chrome Web Store dashboard page](https://chrome.google.com/webstore/developer/dashboard).
2. If you don't see a drop-down at the top of dashboard page, go to step 3.
3. If you do see a drop-down, you've already been added to group publishing by another developer. From the drop-down, select your own account instead of the group publisher account.
4. At the bottom of the dashboard page, you'll see one of two links:
    * **Google Group publishing: Choose existing group or create new group** This link shows up if you're the owner of one or more Google Groups, and those groups haven't already been linked to a publisher account.
    * **Google Group publishing: Create new group** You'll see this link if you aren't an owner of any Google Groups, or if all the groups that you are an owner of have already been linked to other publisher accounts.
5. You can do one of the following:
    * Create a new Google group and link to this new group: 1. Click **Create new group**. You'll see the Google Groups page in a new tab. 2. Create your new group. 3. Reload the Chrome Web Store dashboard page in your browser, then follow the steps below under "Link to an existing Google Group."
    * Link to an existing Google group: 1. Click **Choose existing group**. 2. Select a group from the drop-down. (We recommend linking to a group that you're using only for group publishing of your items.) 3. Click **OK** in the confirmation box. 4. Click **Save Changes** at the bottom of dashboard page.

After you complete the steps above, a new Group Publisher account is created. The Google Group you selected or created is linked to this new publisher account, and the group email is the new publisher account's email.

### After you set up group publishing

Your dashboard page will show the new Group Publisher account and the linked Google Group. You can [add or remove developers](https://groups.google.com/). **All members of the linked group can act on behalf of the new publisher account**. For example, they can edit items, publish items, edit the publisher's display name, etc.

### Things to note

* Each member of the group must pay the developer fee.
* You can only set up group publishing once and create one group publisher account.
* You must be the owner or administrator of a Google Group to link the group. The drop-down list on the dashboard page only shows groups that you're a direct member of (for example, if you are a member of Group A and Group A is a member of Group B, you are not a direct member of Group B, and Group B is not shown on the drop-down list).
* Once you finish the group publishing setup, it can take up to 30 minutes for developers in your group to see the changes.
* Your domain is the default domain of the new group publisher account. A group publisher can publish items either to the public or to its default domain. A publisher cannot publish to other domains.
* A developer can act on behalf of multiple publishers if the developer is a member of multiple Google Groups linked to publishers.
* If a merchant account is needed or is already set up, any member of the group can choose to re-link their own merchant accounts to the publisher on the dashboard page.
* When you want to create new store items, you will have the opportunity to choose whether to make them part of your personal publisher account or the group publisher account before you upload the item.

### Move existing items to a Group Publisher account

Once you set up a Group Publisher account (or once you're added as a member of a Google Group linked to a Group Publisher account), you can transfer your own items to the Group Publisher.

Remember that once you move items to a Group Publisher account, you won't be able to move them back to your personal publishing account.

To transfer items to a Group Publisher account:

1. Sign into your [Chrome Web Store dashboard page](https://chrome.google.com/webstore/developer/dashboard).
2. From the publisher selection drop-down at the top of the dashboard, select the Group Publisher you want to transfer your items to. It will load the dashboard page for the selected Group Publisher.
3. Select **Transfer existing item(s)**, next to the **Add new item** button. You'll see a page with a list of items you own personally.
4. Select the item(s) you want to transfer, and click the **Transfer** link to the right of the item.
5. Click **Transfer** in the confirmation box.

After your items are moved, you'll see the item transfer page again. Any items you transferred will no longer be on the page. At the top of the page, you'll see a yellow bar with the status of the last item transfer.

### Group publishing troubleshooting

* If either your personal publishing account or the Group Publisher account is suspended, you won't be able to transfer items.
* If the Group Publisher account has reached its published item limit, you won't be able to transfer your published items to this Group Publisher.
* You can't transfer a paid item to a Group Publisher account that doesn't have a Google Wallet merchant account set up and linked.

## Publishing to the world

When you publish to the world, it’ll be immediately visible to the world, and it’ll be visible in the store’s search results.

You can select the regions that you want to support, [pick your app’s price in each region](https://developer.chrome.com/webstore/pricing#matrix) (if you use Chrome Web Store Payments), and [internationalize your app](https://developer.chrome.com/webstore/i18n).

To publish to the world, click **Publish** next to your app. You can also visit the dashboard’s edit page and click **Publish changes**.

## Publishing on Google Play for Education

If you build an app for K-12 education, you can opt in to Google Play for Education.

Google Play for Education is a separate store that lets educators find, buy, and deploy apps to their students with just a few clicks. Learn more about publishing in [Google Play for Education](http://developer.android.com/distribute/googleplay/edu/start.html).

## Control how fast your app reaches users

You can control how fast a new version of your app reaches existing users with Controlled Rollout. By using the “max deploy percentage” control, you can limit the percentage of existing users that are updated to the latest version of the app through the Chrome auto-update mechanism.

Example:

If your app has 20,000 users and the current version of the app is 1.0, you may want to test how the new version 2.0 of your app works for a small portion of users before you deploy it to all of them. You can set the “max deploy percentage” control for the new package to say, 10%, then publish the package. This way, a maximum of 2,000 users will be updated to version 2.0 of the app. If you’re happy with the test, you can gradually increase the max deploy percentage and republish the app, eventually turning off the max deploy percentage control to roll out to all users.

Notes:

* The max deploy percentage control only applies to auto-update for existing users. New users always get the latest version of your app.
* If you don’t see the max deploy percentage control, it may be because of the following:
    * You have less than 10,000 users. Currently the “controlled rollout” feature is only available for items with at least 10,000 users.
    * You need to upload a newer (higher) version of a package to use the “controlled rollout” feature. We can’t apply a controlled rollout to an already published package, because it may have already reached 100% of users.

{{/partials.standard_store_article}}
