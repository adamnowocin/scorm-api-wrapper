# scorm-api-wrapper

Created by Philip Hutchison, January 2008
https://github.com/pipwerks/scorm-api-wrapper

Modified by Adam Nowocin, July 2016
https://github.com/adamnowocin/scorm-api-wrapper

Copyright (c) Philip Hutchison
MIT-style license: http://pipwerks.mit-license.org/

Inspired by APIWrapper.js, which was a demo file created by the ADL and Concurrent Technologies Corporation.

The SCORM.API.find() and SCORM.API.get() functions are based on ADL code, which was modified by Mike Rustici (http://www.scorm.com), then further modified by Philip Hutchison.

WARNING: Use at your own risk! These files are provided as-is with no implied warranties or guarantees.

## Background 

These wrappers are intended to make your life easier so you don't need to be a SCORM expert to add SCORM support to your e-learning course.

The SCORM API wrapper is an abstraction layer that makes adding SCORM code to your course a much simpler, less confusing task. They provide simple logic and error-checking for your course's SCORM code, and include some auto-handling, such as setting cmi.exit (aka cmi.core.exit) when exiting a course.

This repository contains SCORM API Wrapper for JavaScript.

This wrapper is SCORM version-agnostic, and will work with both SCORM 1.2 and SCORM 2004.

## Usage

```javascript
import default from 'SCORM_API_wrapper';

var scormAPI = default.SCORM;

// Initialize the API wrapper and establish connection to the LMS
scormAPI.init();

// Get a value of the SCORM Data Model
var value = scormAPI.get('cmi.(...)');

// Set a value of the SCORM Data Model
scormAPI.set('cmi.(...)', 'someValue');

// Set cmi.score.raw / cmi.core.score.raw (according to the SCORM version)
scormAPI.setScoreRaw(50);

// Set cmi.score.min / cmi.core.score.min (according to the SCORM version)
scormAPI.setScoreMin(0);

// Set cmi.score.max / cmi.core.score.max (according to the SCORM version)
scormAPI.setScoreMax(100);

// Set lesson status
scormAPI.status('set', 'completed');

// Get cmi.score.raw / cmi.core.score.raw (according to the SCORM version)
var score = scormAPI.getScoreRaw();

// Persist current state of the Data Model (i.e. LMSCommit() / Commit() )
scormAPI.save();

// Persist the Data Model and close the connection to the LMS
scormAPI.quit();

```

## Useful links

http://scorm.com/scorm-explained/technical-scorm/run-time/

http://scorm.com/scorm-explained/technical-scorm/run-time/run-time-reference/