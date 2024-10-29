=== Paid Memberships Pro - Roles Add On ===
Contributors: strangerstudios, joshlevinson
Tags: pmpro, paid memberships pro, membership, roles
Requires at least: 5.2
Tested up to: 6.6
Stable tag: 1.5

Adds a WordPress Role for each Membership Level.

== Description ==

Adds a new WordPress Role for each Membership Level. A member's role will be set to the role for their membership level after checkout.

Custom roles will set the `display_name` as the membership level's name and the `role` as `pmpro_role_x`, where `x` is the membership level's ID. 

Custom role capabilities are equivalent to WordPress `subscriber` role capabilities. You can adjust the role's capabilities using the `pmpro_roles_default_caps` filter in a custom function. For a list of all WordPress core capabilities, visit (https://wordpress.org/support/article/roles-and-capabilities/](https://wordpress.org/support/article/roles-and-capabilities/).

Alternately, you can use a plugin like [User Role Editor](https://wordpress.org/plugins/user-role-editor/) to add or remove custom capabilities via a settings page in the WordPress dashboard.

The plugin will immediately create a new role for every existing or newly added membership level. 

* New members will have their role set after completing checkout. 
* Existing members will keep their previous role. You will need to perform a custom database query to bulk update the roles for existing members, if desired.

If you no longer want to use this plugin, click the "Delete and Deactivate" link in the plugin's action links on the Plugins page in the WordPress dashboard. This will update all users with a custom membership role and set their "role" back to the WordPress "subscriber" default.

This plugin currently requires Paid Memberships Pro. 

Based on the original PMPro Roles plugin by Josh Levinson (josh@joshlevinson.me) in 2013.

== Installation ==

1. Upload the `pmpro-roles` directory to the `/wp-content/plugins/` directory of your site.
1. Activate the plugin through the 'Plugins' menu in WordPress.
1. That's it. No settings.

== Frequently Asked Questions ==

= I found a bug in the plugin. =

Please post it in the issues section of GitHub and we'll fix it as soon as we can. Thanks for helping. https://github.com/strangerstudios/pmpro-roles/issues

= I need help installing, configuring, or customizing the plugin. =

Please visit our premium support site at https://www.paidmembershipspro.com for more documentation and our support forums.

== Changelog ==
= 1.5 - 2024-10-29 =
* SECURITY: Improved security and escaping of strings.
* ENHANCEMENT: Improved capability for Paid Memberships Pro V3.0+ logic.
* ENHANCEMENT: Defaulting to the "New User Default Role" setting when no role is selected within the membership level settings. This will dynamically change based on the default WordPress setting.
* ENHANCEMENT: Allows creation of custom level roles for each membership level at any time if the role does not exist.
* ENHANCEMENT: Deletes the `pmpro_draft_role` role when the plugin is deleted or delete roles and deactivate option is selected from the plugins page.
* REFACTOR: Refactored some code to use built-in methods available from Paid Memberships Pro and older versions to support backwards compatibility.

= 1.4.2 - 2022-12-12 =
* ENHANCEMENT: Improved UI for role selection in the edit level settings.
* BUG FIX: Fixed issue where fatal error was being caused when Paid Memberships Pro was deactivated. 

= 1.4.1 - 2021-08-30 =
* BUG FIX/ENHANCEMENT: Checkbox list scrollbars are now more noticeable on MacOS.
* BUG FIX: Fixed issue where level role settings weren't being honored sometimes if the default level role was selected.

= 1.4 - 2021-08-18 =
* BUG FIX/ENHANCEMENT: Reworked function that assigns user roles for Paid Memberships Pro V2.5.8+. Fixes an issue with Multiple Memberships Per User and WooCommerce.
* ENHANCEMENT: New filter added 'pmpro_roles_after_role_change'. This allows developers to hook in during the role assignment process and run other code.

= 1.3.2 - 2020-11-24 =
* ENHANCEMENT: Improved logic around changing level and assigning roles.

= 1.3.1 - 2020-10-28 =
* BUG FIX: Fixed issue where accidentaly removed administrator role from edit user profile page while plugin is active.

= 1.3 - 2020-10-26 =
* ENHANCEMENT: Added options to level settings area to choose which roles members should receive when purchasing a level.
* ENHANCEMENT: Supports members having multiple roles, and integration for Multiple Memberships Per User Add On.
* ENHANCEMENT: Added localization (translations) and escaped all front-end strings.
* ENHANCEMENT: Improved coding standards and docblocks for all functions.
* ENHANCEMENT: New filter added for when member cancels, allows developers to set a unique user role when a member cancels. Filter: 'pmpro_roles_downgraded_role'
* ENHANCEMENT: New filter added to allow developers to add/remove roles to the membership level settings checkboxes. By default this excludes the admin role. Filter: 'pmpro_roles_downgraded_role'.
* REFACTOR: Reworked the delete_level function. Logic is still the same.

= 1.2 - 2020-05-21 =
* BUG FIX/ENHANCEMENT: Adding the "read" capability to all custom level roles by default. You can filter custom role capabilities using the `pmpro_roles_default_caps` filter.
* BUG FIX: Repaired issue where the "Delete Roles and Deactivate" link would show when the plugin was inactive.

= 1.1 = 
* Added a "Delete Roles and Deactivate" link to the plugins page to deactivate with a bit more cleanup. Users are given the "Subscriber" role if they had a membership level based role before.

= 1.0 =
* FEATURE: This is the initial version of the plugin.
