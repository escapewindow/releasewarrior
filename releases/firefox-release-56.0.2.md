# Release: Firefox 56.0.2

### Started: 2017-10-24

## Build 1

### Release Graph
[task group](https://tools.taskcluster.net/push-inspector/#/bL_MbidsTwCm0xJGOUuL2w)

#### Status
- [x] [submit to Shipit](https://wiki.mozilla.org/Release:Release_Automation_on_Mercurial:Starting_a_Release#Submit_to_Ship_It)
- [x] [Setup whatsnew page](https://wiki.mozilla.org/Release:Release_Automation_on_Mercurial:Updates_through_Shipping#Set-up_whatsnew_page)
- [x] [pushed to mirrors/releases](../how-tos/relpro.md#2-push-to-releases-dir-mirrors)
- [x] [published release tasks](../how-tos/relpro.md#4-publish-release)
- [x] [signoff in Balrog](../how-tos/relpro.md#3-signoffs)

### Issues
- rail: The updates builder failed because we had to partials for version less than 56.0, so the bz2 blob top-level submission failed. Fixed in https://bugzilla.mozilla.org/show_bug.cgi?id=1395697#c48 and has been rerun.
- jlund: REQUIREMENT: determine need and action - [Bug 1411428](https://bugzil.la/1411428) - Create partial updates to migrate eligible 56.0 win32 users to 56.0.2 win64
- jlund: REQUIREMENT: update balrog rules to reflect requirements defined in this [doc](https://docs.google.com/document/d/1_b3SuHiMZn141jM_MHw9sclm8nkn_COrlbHF44NIWKY/edit\#heading\=h.g14w5uu682r0)
- jlund: REQUIREMENT: re: balrog rules - all users should watershed off 56.0. https://aus4-admin.mozilla.org/rules/624  stays the same
- jlund: REQUIREMENT: re: balrog rules - no users receive 56.0.1. If we need migration partials from [Bug 1411428](https://bugzil.la/1411428), we should update https://aus4-admin.mozilla.org/rules/659 to point to 56.0.2 with WNP for mobile promotion. Same WNP as 56.0.1
- jlund: REQUIREMENT: re: balrog rules - all platforms + non eligible win32 migration 56.0 users should go to 56.0.2 with WNP for mobile promotion. Same WNP as 56.0.1
- jlund: REQUIREMENT: re: balrog rules - all 56.0.1 users should receive 56.0.2 but *not* receive any WNP as they already saw WNP for mobile promotion
- jlorenzo: [Bug 1411981](https://bugzil.la/1411981) - Can't schedule publishing in balrog: balrog-release-shipper.py: error: unrecognized arguments: --suffix
- jlorenzo: I worked around [Bug 1411981](https://bugzil.la/1411981) by manually submitting J5nLeOoORmu1Hm9pYg0Hdw (with "publish_bz2_blob" set to false in the payload). Then I forced the original task to be resolved.
