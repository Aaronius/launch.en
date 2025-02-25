---
title: Release notes
seo-title: Adobe Launch Release notes
description: Adobe Launch release notes
seo-description: Adobe Launch release notes
---

# Release notes

## October 08, 2019

## Updates

* Property Copy: You can now make a copy of a property and everything in it.  From the Properties list page, simply select a property and click Copy in the toolbar.
* Working Library Build button: For users who use the Working Library, there's now a build button.  When you have set the working library and make edits to a resource, the default action is now *Save and Add* instead of *Save and Build*.  This will allow users to make edits to multiple resources and then build when you are ready.
* Visual tweaks to code checks in code editor: We made some visual tweaks to soften the appearance of the Code Validation that we released back in August.

## Bug Fixes

* Dependencies are checked when building a library.  We've done some optimizations there to reduce the number of network requests that are made when performing these checks.

## September 24, 2019

## Updates

Multiple cache invalidations: If you are using the *Managed by Adobe* Host for your environments, Launch now makes multiple cache invalidations each time you publish.  Previously, one invalidation was performed for each build immediately after the build was uploaded.  However, there is a time delay between when the file is uploaded to one origin server and when it is available on all origin servers, so there was a race condition which sometimes caused the stale version of the library to be cached on the edge for up to 6 hours.  Each build is now purged on the following intervals:

* Immediately
* 5 minutes after build
* 60 minutes after build

You can read more about cache invalidations on the [Managed by Adobe Host](/help/launch-reference/publishing/hosts/managed-by-adobe-host.md) page.

## Bug Fixes

* Fixed an issue where, in certain edge cases where you had more than 100 libraries on the Publishing screen, there was a bug that caused Libraries in the Submitted column not to show up.  

## September 12, 2019

### Bug Fixes

* There was a bug that prevented you from being able to unassign an Environment from a Library (when you chose No environment, it wasn't saved correctly).  That works again.

## September 04, 2019

## Updates

* Tokens in pathnames: Newly created environments now use much shorter IDs for Company, Property, Extension, and Environment in the pathnames referenced in the embed codes.  Self-hosting users were bumping into path length limitations on Windows systems, so they've been shortened.  Existing environments are unaffected.  New environments have much shorter paths, including the embed codes referenced in the install instructions.

## Bug Fixes

* Updated the regex tester to be more explicit about the expected inputs and how the pattern you enter will be used at run-time.
* Fixed a bug that caused you to be unable to upgrade an extension when the installed version had no settings and the latest version did.
* Fixed a bug that, in rare cases, caused unavailable environments to show as available.


## August 14, 2019

### Updates

* Code Validation: The custom code editor now lints and minifies your code behind the scenes and informs you if there are problems. Some of these notifications are warnings, but some are errors that will cause your build to fail if this code is included in a library.
* Extension Enhancements for Compare View: Rule Components and Data Elements rely on extensions.  Extensions have their own settings and revisions that can potentially modify the behavior of your components, even if the the settings on the component itself is the same.  Compare view now warns you if the component is relying on a different extension revision than its historical counterpart, so you can decide if you'd also like to compare the extension settings.

## Bug Fixes

* Fixed a bug that defaulted some users to the first Org they had access to when opening a new tab. This only affected a few users.
* Fixed a bug that prevented you from being able re-expand custom code in compare view.

## June 18, 2019

### Updates

* Libraries that use the [!DNL Managed by Adobe] host and a non-archived environment now reference all sub files directly with `https://` instead of inheriting the underlying page protocol.  This enables you to use [!DNL Launch] in embedded HTML scenarios (mobile and set-top-box environment in particular) without self-hosting.
* You can now unset your Working Library.
* The Edit Library screen now has a button to [!UICONTROL Remove All Resources].
* The size of the click target has increased to remove individual resources from a library

### Bug Fixes

* Fixed a bug in [!DNL Safari] that caused the [!UICONTROL Add Resource] buttons on the Library Edit page to show in the wrong place.
* Fixed a bug with validating uppercase domains on the Property Edit screen.
* Fixed a bug that caused some buttons to be available when they should not be.

## June 15, 2019

### Updates

* Archive packages on SFTP Hosts are now delivered to the root patch specified by the Host instead of being delivered two subdirectories deep (which is how all other builds are delivered).  This was change because of permissions issues creating subdirectories on some SFTP servers.

## June 13, 2019

### Updates

* Error messages now provide much more detail about the error that occurred (for those who want to look).  They also provide an easy way to log tickets and some key identifiers that will help [!DNL Adobe] to troubleshoot any issues.  And they've moved to the bottom center of the page to comply with the latest [!DNL Adobe] styles.
* The [!UICONTROL Add Resource] buttons on the Library Edit page now float as you scroll up and down so they are always visible.
* The URLS for Resource Comparison are more informative (and useful for debugging purposes).

## Bug Fixes

* Fixed a bug in Edge on Windows 10 that wouldn't let you promote libraries in Edge on Windows 10.
* Fixed a bug in Edge on Windows 10 that prevented library resources from being displayed on the Library edit page.
* Fixed a bug that was showing scroll bars in unnecessary places.
* Fixed several broken links that were scattered about.
* Fixed several non-scrollable areas for iOS browsers.

## June 11, 2019

### Updates

* Archive packages now use relative symlinks instead of absolute ones.

### Bug Fixes

* You can no longer delete a Host that is being used by an environment
* Resources in revision selector will now appear alphabetically
* Fixed a bug that caused certain rules to fail to copy
* Got rid of a few unnecessary unsaved changes prompts
* Updated shell to match the rest of Experience Cloud
* Fixed the polling bug on library build, so we'll retry 5 times before starting the exponential backoff
* Got rid of a few warnings for deprecation in the developer console

## May 8, 2019

The [!DNL Reactor] API that powers [!DNL Launch] is officially reaching 1.0 status today.  This comes with a commitment to maintaining backwards compatibility within this major version (the 1.x series).  To get started working with the [!DNL Reactor] API, please visit [https://developer.adobelaunch.com/api/\#](https://developer.adobelaunch.com/api/#).

### Updates

* A number of API changes have been made for this 1.0 release.  API release notes will be posted with the API documentation at [https://developer.adobelaunch.com/api/release\_notes/2019-release-notes/](https://developer.adobelaunch.com/api/release_notes/2019-release-notes/).
* `Adapter` has been renamed to `Host`. Audit events will contain the following items related to this change.
  * For each adapter, you'll see a `Host.created` event.
  * For each environment, you'll see an `Environment.updated` event to remove the relationship with the adapter and add the relationship to the host.
  * For each adapter, you'll see an `Adapter.deleted` event.

### Bug Fixes

* Fixed some inconsistencies with the Regular Expression tester used by various extensions.

## April 8, 2019

### Bug Fixes

* Improved a few build error messages
* Better reporting for failed SFTP Hosts

### Other

* Updated the way that rule components and data elements relate to extensions.  When you delete an extension and reinstall an extension, you no longer have to manually update your resources to point to the newly installed extension.
* Rule components are now under Property instead of Rule.  This lays a foundation for future enhancements to rule components.

## March 20, 2019

### Updates

* Visual updates to the resource copy tool, including status indicators and a cancel button.

## March 5, 2019

### Bug Fixes

* Builds stored on Akamai will use a new folder structure.  Embed codes do not change. This will mediate many issues we've seen with builds to Akamai.

## February 20, 2019

### Updates

* Support for custom code has been added to Compare View.

### Bug fixes

* The cross-property workflow is now a bit smoother.

## February 12, 2019

### Features

* Cross-property Copy - You can now copy resources from one property to another.  After selecting a resource and clicking the **[!UICONTROL Copy]** button, you can select a target property to copy to.  This is available on extensions, data elements, and rules.  Read more about copying resources [here](../launch-reference/managing-resources/copying-resources.md).

## January 29, 2019

### Features

* Revision Compare - You can now compare one version of a resource with older versions.  This is available on extensions, data elements, and rules.  Read more about this new feature [here](../launch-reference/managing-resources/compare-resource-revisions.md).

## January 17, 2019

### Updates

* Builds should be running ~15% faster than before.  Large builds (hundreds of resources) will have more dramatic improvements.

## January 8, 2019

### Core Extension 1.4.2

* The `Enters Viewport` event is now configurable to trigger each time that the element enters the viewport instead of just the first time.
* Custom Events can now contain extra contextual data that can be used in conditions and actions.
* Link Delay on the Click event will now trigger on descendants of the anchor and not just the anchor itself.

### Updates

* Properties that are configured for Extension Development now have a small tag next to the Property Name.
* OrgID is now available on the \_satellite object.
* Use of the [!DNL Launch] UI is no longer supported in IE 11, you'll receive a warning if you login with IE 11.

### Bug fixes

* Better support for long library names in your Active Library and the Publishing view.
* In certain scenarios, when you saved a library, the dependency checker would prompt you to add a new revision of an extension that was already in your library. It doesn't do that anymore.
* Tooltips will now reliably show up in Safari.
* Searches in the search bar will now trigger a bit faster than before.
