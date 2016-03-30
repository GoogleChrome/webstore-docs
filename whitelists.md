# Whitelists (final name TBD)

## Introduction
Whitelists are a Chrome Web Store (CWS) item type, similar to Chrome Apps and Chrome Extensions. They are collections of "safe" content in the context of Chrome Supervised Users, enabling custodians to allow their supervised users access to a trusted list of websites.

Whitelists are lists of URL patterns and/or hashed hostnames provided by third parties. A whitelist contains, at a minimum, an *icon*, a *name*, and a *landing page URL*. The name and icon are used to visually represent the whitelist in the CWS or in Chrome. The landing page URL is used as a starting point into the whitelisted content.

## Requirements
A Whitelist is uploaded to CWS as a `ZIP` file containing a manifest file and a list of URLs to be whitelisted, both in JSON format. 

### Manifest
A sample manifest file is shown below.
```javascript
{
  "manifest_version": 2,
  // The name of the whitelist that can be displayed to users.
  "name": "Test whitelist",
  // The whitelist version. Publishing a new version of a whitelist requires incrementing the version.
  "version": "0.0.0.1",
  "whitelisted_content": {
    // Required.
    "sites": "site_list.json"
  },
  "icons": {
    // Required.
    "128": "128icon.png"
  }
}
```
The manifest identifies the whitelist version, name, and icon, and points to the sitelist file that contains the URLs to be whitelisted. The presence of the key `whitelisted_content` uniquely identifies a whitelist.

### Sitelist
A sample sitelist file is shown below.
```javascript
{
  // Version of the whitelist format.
 "sitelist_version": 1,
  // This URL will be featured on the supervised user’s new tab page. 
  // This URL too has to be manually whitelisted in order to be accessible.
  // Optional.
 "entry_point_url": "http://example.com",
  // The list of URL patterns that define which URLs are whitelisted.
 "whitelist": [
       "youtube.com",
       "ytimg.com",
       "https://googleusercontent.com",
       "gstatic.com"
     ],
  // The list of hostname SHA1-hashes that are whitelisted. 
  "hostname_hashes": [
       "0caaf24ab1a0c33440c06afe99df986365b0781f"
     ]

}
```
URLs may be defined either in plain text or as [SHA-1](https://en.wikipedia.org/wiki/SHA-1) (Secure Hash Algorithm 1) hashed host names, which allows membership tests without exposing host names in plain text. For example, the hash value above represents the string "example.com". 

>**Tip:** You can generate SHA-1 hash values in several ways, including command line utilities, JavaScript functions, and at web sites such as [sha1-hash-online](http://sha1-hash-online.waraxe.us/), [md5-hash-generator](http://www.md5hashgenerator.com/md5-hash-generator/sha1-generator.php), and [passwordsgenerator](http://passwordsgenerator.net/sha1-hash-generator/).

Note that the landing page specified by the `entry_point_url` key is not automatically whitelisted. It is your responsibility as the developer to ensure that the entry point is properly scoped to avoid over-whitelisting content.

## Publish
Whitelists are uploaded and maintained in much the same way as other CWS items using the publishing UI in the [Developer Dashboard](https://chrome.google.com/webstore/developer/dashboard). Adding or removing whitelisted content is done by uploading a new `ZIP` (with an item's version number incremented) containing an edited sitelist file. 

For more information see the [Publish in the Chrome Web Store](https://developer.chrome.com/webstore/publish) documentation.

