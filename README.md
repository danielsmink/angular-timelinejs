angular-timelinejs
==================

Angular directive wrapping TimelineJS.

Installation
------------

To use the angular-timelinejs directive you can simply install it using Bower:

```
$ bower install angular-timelinejs
```

Load the Javascript and CSS files in appropriate places:

```html
<link rel="stylesheet" href="bower_components/TimelineJS/build/css/timeline.css" />
<link rel="stylesheet" href="bower_components/TimelineJS/build/css/themes/font/Rancho-Gudea.css">
<script src="bower_components/TimelineJS/build/js/timeline.js"></script>
<script src="bower_components/angular-timelinejs/build/angular-timelinejs.js"></script>
```

and make sure you inject it in your application (i.e. app.js):

```javascript
angular.module('myModule', ['pippTimelineDirectives']);
```

then simply include the following somewhere into your HTML (i.e. view).

```html
<pipp-timeline-j-s source="timelineData"
                   height="600"
                   width="98%"
                   start-zoom-adjust="0"
                   start-at-end="false"
                   start-at-slide="0"
                   hash-bookmark="false"
                   lang="en"
                   debug="false"
                   state="timelineState"></pipp-timeline-j-s>
```

and in a controller you would have your data and initial state which you can pull from services and manipulate as you wish. Set the index in state to anything else but 0 to start at that record.

```javascript
$scope.timelineData = {
  "timeline":
  {
    "headline":"The Main Timeline Headline Goes here",
    "type":"default",
    "text":"<p>Intro body text goes here, some HTML is ok</p>",
    "asset": {
      "media":"http://yourdomain_or_socialmedialink_goes_here.jpg",
      "credit":"Credit Name Goes Here",
      "caption":"Caption text goes here"
    },
    "date": [
      {
        "startDate":"2011,12,10",
        "endDate":"2011,12,11",
        "headline":"Headline Goes Here",
        "text":"<p>Body text goes here, some HTML is OK</p>",
        "tag":"This is Optional",
        "classname":"optionaluniqueclassnamecanbeaddedhere",
        "asset": {
          "media":"http://twitter.com/ArjunaSoriano/status/164181156147900416",
          "thumbnail":"optional-32x32px.jpg",
          "credit":"Credit Name Goes Here",
          "caption":"Caption text goes here"
        }
      }
    ],
    "era": [
      {
        "startDate":"2011,12,10",
        "endDate":"2011,12,11",
        "headline":"Headline Goes Here",
        "text":"<p>Body text goes here, some HTML is OK</p>",
        "tag":"This is Optional"
      }

    ]
  }
};

$scope.timelineState = {
  index: 0
}
```

Examples
--------

The demo directory contains two web applications: one using TimelineJS with Angular and one using Angular through this directive. This is mainly to help observe difference during development.

To see the examples you can simply `cd` into the example directory and execute `grunt serve` to start a development web server. Then access the example at `http://localhost:9002` or `http://localhost:9003` depending on which one you started.


Development Requirements
------------------------

These requirements are to work *on* the directive (see Contributing below) and not the requirements to *use* the directive (see Installation above).

* NodeJS - Used to run test, deploy distributables, run development web server
* npm - Manage Javascript packages on the server (i.e. development machine)
* Grunt - Automated tasks runner (testing, deploying, running web server...)
* Bower - Manage packages on the frontend
* Karma - Run tests

All those should be installed if you need to do work on the directive itself; it is not needed if you simply desire to use the directive as it is offered.

General Notes
-------------

* Namespacing - the pipp prefix on directive names is the namespace portion as this was initially developed within a project at the Pacific Insitute of Public Policy (PiPP).
* Versioning - should follow the Semantic Versioning formal specifications as described in http://semver.org/.
* Committing Dependencies - dependencies are not committed but only declared in package.json and bower.json.

Support
-------

Only bugs and feature request should be included in Github's Issues.

Contributing
------------

Contributing to this project is welcome. The process to do so is outlined below:

1. Create a fork of the project
2. Work on whatever bug or feature you wish
3. Include at least basic tests for your work
4. Ensure all tests still pass
5. Add a example usage in the demo
6. Create a pull request (PR)

We won't guarranty that we will merge all PRs but we will evaluate them all.

Licence
-------

See LICENSE.
