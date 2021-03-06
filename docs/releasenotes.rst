#########################################
Release notes
#########################################

^^^^^^^^^^^^
Requirements
^^^^^^^^^^^^

* Splunk 6.x / Universal Forwarder v6.x and later Only

* Universal Forwarders clients system lacking a Python 2.7.x interpreter requires Perl WITH Time::HiRes module available

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
What has been fixed by release
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

========
V1.3.33:
========

- fix: review sourcetypes definition #60
- Feature: mutex implementation to avoid simultaneous run of shell scripts #59
- Feature: override serial number #58
- fix: Removing crcSalt from inputs since it is not required anymore #57
- fix: Typo in nmon_helper.sh during Perl / Python detection #56
- fix: Host override feature improvement for non data sourcetypes #55

========
V1.3.32:
========

- fix: batch mode and fishbuckets performance issues #53
- fix: Missing rotation of external header in fifo_reader.py/pl #54

========
V1.3.31:
========

- feature: Solaris - SARMON upgrade to v1.12 (Sparc FIFO mode) #51
- fix: Rename eventgen.conf to avoid splunkd WARN messages #52

========
V1.3.30:
========

- fix: reactivating the JFSFILE / JFSINODE collections until new core release is available to prevent missing features

========
V1.3.29:
========

- fix: Python parser - header detection correction for nmon external monitoring
- fix: unexpected operator issue during process identification #48
- fix: prevent bundle validation warn messages with spec files in README directory
- feature: Add df information for improved file system monitoring and storage capacity planning
- feature: JFSFILE/JFSINODE are being replaced (and deactivated) by external collection with DF_STORAGE/DF_INODES

========
V1.3.28:
========

- fix: Perl parser write new line after each write (Case #508792 Splunk universal forwarders duplicating data due to File too small to check seekcrc #47)
- fix: minor code cleaning
- feature: complete review of eventgen configuration using TA-nmon-hec samples

========
V1.3.27:
========

- feature: index and search time parsing configuration for the nmon-logger-splunk-hec package (agent less package for Splunk http input)
- fix: Fully Qualified Domain Name improvements #46

========
V1.3.26:
========

- fix: AIX - Better management of compatibility issue with topas-nmon not supporting the -y option #43
- fix: AIX - fix repeated and not justified pid file removal message #44
- fix: ALL OS - nmon_helper.sh code improvements #45

========
V1.3.25:
========

- feature: Optimize nmon_processing output and reduce volume of data to be generated #37
- fix: Linux issue: detection of default/nmon.conf rewrite required is incorrect #41
- fix: Error in nmon_helper.sh - bad analysis of external snap processes #42

========
V1.3.24:
========

- fix: AIX issue - non terminating processes will result in collecting stop #38
- fix: time zone issue - additional sourcetypes (collect, clean) use a date format that includes TZ and can lead to confusion #39
- fix: Review interpreter (python/perl) choice in all shell scripts, specially to fix some AIX issues #40

========
V1.3.23:
========

- unpublished intermediate release

========
V1.3.22:
========

- fix: nmon from syslog - missing indexed time creation for OStype and type fields #31
- fix: nmon from syslog - uptime extraction failure #32
- fix: nmon external - manager header in a dedicated file #33
- fix: Perl parser - prevent error message when --json_output option is set #34
- feature: Linux nmon binaries upgrade to nmon 16g #35
- fix: AIX - multiplication of nmon external snap instances on some systems #36

========
V1.3.21:
========

- fix: AIX issue - fifo_reader regex match some monitors into header #29
- fix: Nmon external issue - manage metrics collection into a dedicated file #30

========
V1.3.20:
========

- unpublished intermediate release

========
V1.3.19:
========

- fix: fifo mode implementation in parsers and several corrections #27
- fix: CIM compliance improvements and corrections
- fix: missing oshost tag for ITSI
- fix: fifo_consumer.sh error in file naming for rotated files purge
- fix: fifo_consumer.sh issue generates gaps in data #28
- feature: Allows deactivating fifo mode and switch to old mechanism via nmon.conf #26
- feature: Allows deactivating nmon external generation via nmon.conf #25

==============
V1.3.16 to 18:
==============

- unpublished intermediate releases

========
V1.3.15:
========

- Fix: nmon external load average extraction failure on some OS
- Fix: TA-nmon local/nmon.conf from the SHC deployer is not compatible #23
- Fix: Use the nmon var directory for fifo_consumer.sh temp file management
- Fix: solve nmon_external issues with AIX 6.1/7.1 (collection randomly stops)
- Fix: manage old topas-nmon version not compatible with -y option
- Feature: binaries for Ubuntu 17 (x86 32/64, power)

========
V1.3.14:
========

- intermediate version not published

========
V1.3.13:
========

**This is a major release of the TA-nmon:**

- Feature: fantastic reduction of the system foot print (CPU,I/O,memory) with the new fifo implementation, the TA-nmon cost is now minimal!
- Feature: easily extend the native nmon data with any external data (OS commands, scripts of any kind, shell, perl, python...) in 2 lines of codes
- Feature: easily customize the list of performance monitors to be parsed (using the nmonparser_config.json)
- Feature: choose between legacy csv and json data generation (limited to Python compatible hosts), you can now choose to generate performance data in json format and prioritize storage over performance and licensing volume
- Feature: new dedicated documentation for the TA-nmon, https://readthedocs.org/projects/ta-nmon
- Feature: nmon binaries for Amazon Linux (AMI)
- Fix: Removal of recursive stanza in inputs.conf #21
- Fix: Increase the interval for nmon_cleaning #18
- Fix: Various corrections for Powerlinux (serial number identification, binaries and architecture identification)
- Fix: AIX rpm lib messages at nmon_helper.sh startup #22
- Various: deprecation of the TA-nmon_selfmode (now useless since the new release does use anymore the unarchive_cmd feature)

==================
Previous releases:
==================

**Please refer to:** http://nmon-for-splunk.readthedocs.io/en/latest/knownissues.html
