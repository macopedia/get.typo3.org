Release Notes for TYPO3 CMS 6.2.13
==================================

This document contains information about TYPO3 CMS 6.2.13 which was
released on June 10th, 2015.

News
----

This release is a bug fix release.

PHP 5.6 support
---------------

Although the TYPO3 CMS Team aims at eventually supporting PHP 5.6 with
TYPO3 6.2 LTS, we are aware of in-depth issues with the reinstantiation
of objects in Extbase. As such, we highly recommend to keep PHP 5.3 -
5.5 when running TYPO3 6.2 LTS for the time being.

Important information regarding image handling
----------------------------------------------

The base data used for the checksum calculation of processed files have
been changed. The checksum is used to identify changes, which require
regeneration of processed files.

Formerly the `GFX` section of the `TYPO3_CONF_VARS` was included in this
base data, which caused weird problems in some cases.

With TYPO3 CMS 6.2.13 this has been changed. In case you are adjusting
`GFX` settings and you want processed files to be regenerated, you need
to manually clean the existing processed files by using the Clean up
utility in the Install Tool.

Since the base data are different now, the Core would not recognize the
existing processed files as valid files and would delete those and build
a new version.

In case you are having a large installation, you might want to avoid
this costly operation. The Install Tool provides a dedicated Upgrade
Wizard for you, which avoids the expensive regeneration of processed
files by updating the checksum of all existing processed files.

Download
--------

<https://typo3.org/download/>

MD5 checksums
-------------

    9c04385b58e65b9087540ca6ae59f7cc  typo3_src-6.2.13.tar.gz
    5db5d737ddd7ab546f872ec147b75fa8  typo3_src-6.2.13.zip

Upgrading
---------

The [usual upgrading
procedure](https://docs.typo3.org/typo3cms/InstallationGuide/) applies.
No database updates are necessary.

Changes
-------

Here is a list of what was fixed since
[6.2.12](TYPO3_CMS_6.2.12 "wikilink"):

    2015-06-10  5d5d0e1                  [RELEASE] Release of TYPO3 6.2.13 (TYPO3 Release Team)
    2015-06-10  a432175  #67272          Revert "[BUGFIX] Fix serializable object creation with PHP 5.6" (Helmut Hummel)
    2015-06-10  66ab2d6  #66614          [BUGFIX] Avoid unnecessary generation of processed files (Alexander Opitz)
    2015-06-10  6d44ed9  #67385          [BUGFIX] SQL parser does not support string as join condition (Xavier Perseguers)
    2015-06-06  cb76152  #67330          [TASK] Reduce diff size on PackageStates changes (Markus Klein)
    2015-06-06  9679766  #67286          [BUGFIX] InstallTool: connect to DBMS before retrieving current schema (Morton Jonuschat)
    2015-06-06  02d4907  #66572          [BUGFIX] Respect _FILE/_STRING in versioning (Alexander Opitz)
    2015-06-06  79e0941  #66523          [BUGFIX] Correct dependency handling in workspaces module (Dominique Kreemers)
    2015-06-06  6240e12  #67309          [BUGFIX] Show backend user in record info popup (Markus Klein)
    2015-06-05  2271eb8  #67239          [BUGFIX] Open element browser in sys_action (Nicole Cordes)
    2015-06-05  99ed805  #67285          [BUGFIX] Illegal string offset ´showitem´ in ExtensionManagementUtility (Wouter Wolters)
    2015-06-05  c1655c6  #67312          [TASK] Update to phpunit 4.7 (Christian Kuhn)
    2015-06-05  6cb01bb  #67189          [TASK] Adjust Log tests for changed exception format in PHP7 (Alexander Opitz)
    2015-06-05  813ab68  #65319          [BUGFIX] Fix FileList ordering for upper/lowercase (Alexander Opitz)
    2015-06-05  3e7c1bf  #67267          [BUGFIX] Do not try to resolve a path to t3lib (Markus Klein)
    2015-06-05  a729ddd  #67044          [BUGFIX] PropertyMapper now normalizes simple types (Wouter Wolters)
    2015-06-05  982f619  #67084          [BUGFIX] Delete FAL records + relations in ResourceStorage::deleteFolder() (Frans Saris)
    2015-06-04  bef83c8  #67066          [BUGFIX] Initialize database connection in ClearCacheService (Morton Jonuschat)
    2015-06-03  027acbc  #47322          [BUGFIX] Import Selection with TYPO3 Element Browser (Frank Nägler)
    2015-06-03  b13e7df  #67275          [BUGFIX] Clear cache_treelist table in Install Tool (Wouter Wolters)
    2015-06-03  fddd4c6  #67259          [BUGFIX] addToAllTCAtypes() must replace fields correctly (Markus Klein)
    2015-06-02  f6fba02  #64239,#62616   [BUGFIX] Type checking at PageRepository::getFileReferences() call (Alina Fleser)
    2015-06-01  02d5469  #67224          [FOLLOWUP][BUGFIX] dont set fePreview=2 with ADMCMD_noBeUser (Andreas Fernandez)
    2015-06-01  57860a2  #30643          [BUGFIX] dont set fePreview=2 with ADMCMD_noBeUser (Peter Niederlag)
    2015-05-31  e881769  #67148          [FOLLOWUP][BUGFIX] Show full folder path in file list title (Frans Saris)
    2015-05-31  4d8d215  #67094          [BUGFIX] Only persist processedFile if processing was successful (Frans Saris)
    2015-05-29  b391f1d  #67071          [FEATURE] Add "processed files" cleanup tool to Install Tool (Markus Klein)
    2015-05-29  a73adf2  #65320          [TASK] PHP7 is_numeric change (Alexander Opitz)
    2015-05-26  44c5857  #67139          [TASK] Print controller->action if required argument is not set (Andreas Fernandez)
    2015-05-26  aed83b7  #67138          [BUGFIX] Add missing int-cast for checking uid zero (Markus Klein)
    2015-05-25  d148131  #51069          [BUGFIX] Adhere "suggestions" when resolving ext loading order (Markus Klein)
    2015-05-25  0ef3c40  #65346          [TASK] Streamline TS registration for sysexts (Benjamin Mack)
    2015-05-24  8d3bc4c  #67116          [BUGFIX] Don't add TypoScript twice to defaultContentRendering (Markus Klein)
    2015-05-21  4a8580a  #66679          [BUGFIX] Generate thumbnails for files without width/height (Markus Klösges)
    2015-05-21  f084990  #67079          [BUGFIX] Check page access only if integer in ModuleRunner (Nicole Cordes)
    2015-05-20  347473b  #64759          [BUGFIX] Show full folder path in file list title (Christian Weiske)
    2015-05-20  b065bdf  #66870          [BUGFIX] Readonly fields must not render links to allowed tables (Georg Ringer)
    2015-05-20  1b23e73  #63920          [BUGFIX] Ensure new deep dirs don't contain double slashes (Thomas Deuling)
    2015-05-19  f7004ec  #22542          [BUGFIX] Uncheck prefix domain for new domain records (Simon Schaufelberger)
    2015-05-19  2bea93a  #66851          [BUGFIX] Add missing comma in ViewHelper example (Georg Ringer)
    2015-05-19  fa5fdb4  #66920          [BUGFIX] Prevent wrong record copies (Andreas Fernandez)
    2015-05-18  f5dc7d5  #65484          [BUGFIX] Resolve dependencies on extension update (Nicole Cordes)
    2015-05-18  2153bac  #25955          [BUGFIX] remove wrong code suggestion from GMENU (Frederic Gaus)
    2015-05-18  5aa67db  #67013          [BUGFIX] felogin: Use correct regex in redirect evaluation (Markus Klein)
    2015-05-18  f99636e  #67007          [BUGFIX] Correctly insert session data after deleting them (Markus Klein)
    2015-05-17  e98532b  #40280          [BUGFIX] Indexed_search Make results per page work (Extbase plugin) (Tymoteusz Motylewski)
    2015-05-15  5cd1d6c  #66913          [BUGFIX] Valid Content-Type header for jpg thumbnails (Andreas Fernandez)
    2015-05-15  c5b7a0d  #65842,#63519,  [BUGFIX] Temporary filename collision in imageMagickConvert() (Morton Jonuschat)
    2015-05-14  2362c1b  #66955          [FOLLOWUP][BUGFIX] Add extension precedence (Helmut Hummel)
    2015-05-14  1f523cf  #62129          [BUGFIX] Allow protocol in TCEMAIN.previewDomain (Wouter Wolters)
    2015-05-12  0d72276  #66911          [TASK] Travis: Verify no git submodule exists (Christian Kuhn)
    2015-05-12  44dd149  #66740          [TASK] use include for checking update scripts (Jigal van Hemert)
    2015-05-11  736abab  #65244          [FOLLOWUP][BUGFIX] Allow closures in filters methods for directory items (Nicole Cordes)
    2015-05-11  3e8f5c4  #66473,#66885   [BUGFIX] Fix serializable object creation with PHP 5.6 (Helmut Hummel)
    2015-05-11  68e80aa  #65244          [BUGFIX] Allow closures in filters methods for directory items (Christoph Dörfel)
    2015-05-11  b52b9ae  #66437          [TASK] Simplify PHP lint execution (Mathias Brodala)
    2015-05-11  654e990  #64884          [TASK] Display info about registered Extractors in Task "Metadata Extract" (Andreas Fernandez)
    2015-05-10  1a877f2  #66768,#58874   [BUGFIX] Activate runtimeActivatedPackages without cache clearing (Nicole Cordes)
    2015-05-09  c576bfe                  Revert "[BUGFIX] Fix serializable object creation with PHP 5.6" (Michael Stucki)
    2015-05-09  302cddd  #66854          [BUGFIX] Fix broken link to anchor (Andreas Fernandez)
    2015-05-09  b7e70fc  #46448          [BUGFIX] Show sectionIndex from referenced page (Nico de Haen)
    2015-05-09  169a6b2  #66473          [BUGFIX] Fix serializable object creation with PHP 5.6 (Mathias Brodala)
    2015-05-09  7977ac6  #65989,#52277   [BUGFIX] Indexed_search extbase plugin support for mysql fulltext search (Tymoteusz Motylewski)
    2015-05-08  cebf4fa  #66337          [BUGFIX] Respect file create mask for PackageStates file (Mathias Brodala)
    2015-05-07  0f31f45  #66843          [BUGFIX] DBAL: Permission error when saving a new record (Xavier Perseguers)
    2015-05-07  4f3baa9  #66830,#63070   [BUGFIX] ADOdb: mssqlnative driver is not properly initialized (Xavier Perseguers)
    2015-05-07  c3a5d65  #66825          [FOLLOWUP][BUGFIX] File list breaks with DBAL (Andreas Fernandez)
    2015-05-07  69bfc1b  #66825          [BUGFIX] File list breaks with DBAL (Xavier Perseguers)
    2015-05-06  62cbb20                  [TASK] Travis: composer install without --dev (Christian Kuhn)
    2015-05-06  47a498a  #66816          [TASK] Upgrade to phpunit 4.6 (Christian Kuhn)
    2015-05-05  645b1c8  #66798          [BUGFIX] Streamline queue objects on dependency check (Nicole Cordes)
    2015-05-05  ff99469  #52051,#65332,  [BUGFIX] Improve dependency check in extension manager (Nicole Cordes)
    2015-05-05  bc179ed  #66687          [BUGFIX] Prevent root folder listing for users (Andreas Fernandez)
    2015-05-03  f0a98e8  #66695          [BUGFIX] Prevent infinite loop in FAL access check (Nicole Cordes)
    2015-05-02  a2fe59f  #66696          [BUGFIX] Reload classAliasMap after extension installation (Nicole Cordes)
    2015-05-02  c70f3d8  #59147          [TASK] Add extension precedence (Nicole Cordes)
    2015-05-02  c0c563c  #62305          [BUGFIX] Resolve dependencies on extension upload (Nicole Cordes)
    2015-05-02  1dffada  #66742          [BUGFIX] Force hardware acceleration on scrollable elements (Benjamin Kott)
    2015-05-02  4c36b25  #66730          [TASK] Improve retrieving distribution list (Nicole Cordes)
    2015-05-02  afe03cf  #66681          [FEATURE] Add translation params for category (Markus Sommer)
    2015-05-01  30d04f4  #66425          [BUGFIX] Persistent classes with more than five name parts in extbase (Artus Kolanowski)
    2015-05-01  76e2a14  #66699          [BUGFIX] Prevent sorting incomplete loaded packages (Nicole Cordes)
    2015-04-30  5c2d9c3  #66686          [BUGFIX] Cannot use equal operator on data type text (Xavier Perseguers)
    2015-04-30  70356c2  #66680          [TASK] Do not use sequence table when uid field is auto-incremented (Xavier Perseguers)
    2015-04-30  f15a11e  #66678          [BUGFIX] ADOdb: mssqlnative driver fails to create sequences (Xavier Perseguers)
    2015-04-30  70a8dd2  #66496          [BUGFIX] Adhere absRefPrefix for storages (Markus Klein)
    2015-04-30  0c9284e  #66676          [BUGFIX] Invalid check for NULL with ISNULL (Xavier Perseguers)
    2015-04-30  1014635  #66675          [BUGFIX] exec_SELECTcountRows where clause must not be empty (Xavier Perseguers)
    2015-04-30  4887e80  #66674          [BUGFIX] MSSQL native driver for ADOdb returns erroneous message (Xavier Perseguers)
    2015-04-29  a38825c  #66412          [BUGFIX] Make sure excludedTablesAndFields are empty in DataHandler (Benjamin Serfhos)
    2015-04-27  2a43233  #65688          [BUGFIX] Simplify composer class alias loader usage (Helmut Hummel)
    2015-04-27  ea84f12  #63557          [BUGFIX] getProcessedValue ignores foreign_table_field (Andreas Allacher)
    2015-04-27  53c5791  #66499          [BUGFIX] Store page title information in cache (Markus Klein)
    2015-04-27  da231d7  #66573          [TASK] Protect configuration of extensions (Jan Kiesewetter)
    2015-04-26  0f0b807  #64090          [CLEANUP] Use $this-> instead of parent:: in TS Conditions (Markus Klein)
    2015-04-23  460623f  #64057          [BUGFIX] Properly set checked attribute for objects (Andreas Fernandez)
    2015-04-23  b55c22a  #66487          [BUGFIX] Remove unnecessary and failing code (Helmut Hummel)
    2015-04-23  8405d6a  #66537          [BUGFIX] Keep scheduler functional after task interruption (Xavier Perseguers)
    2015-04-21  6215bdb  #63047          [BUGFIX] AbstractTreeView correct permission handling with non pages (Andreas Allacher)
    2015-04-21  f3d846b  #66508          [BUGFIX] Check if validationrules are set before foreach statement (Ruud)
    2015-04-20  bb24c55  #66486          [BUGFIX] Make fields in EM table larger (Andreas Fernandez)
    2015-04-16  3febc79  #64904          [BUGFIX] Make advanced search work with indexed_search extbase plugin (Tymoteusz Motylewski)
    2015-04-16  1afe2a2  #66251          [BUGFIX] indexed_search: use correct TS settings in extbase plugin (Tymoteusz Motylewski)
    2015-04-16  6081baf                  [TASK] Set TYPO3 version to 6.2.13-dev (TYPO3 Release Team)

