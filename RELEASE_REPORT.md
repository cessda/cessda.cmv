# Name of the service(s) the release is affecting

CESSDA Metadata Validator

## Date of release

24/01/2023

## Specify the name of the Process manager

John Shepherdson

## Specify the list of audience to this report

MO Technical Team

## Release tag associated with release

1.0.0

## Release type

Major

## Brief description to explain the main changes happening as part of the release

- Added SQAaaS badges
- Replaced references to Bitbucket, following migration of code to Github
- Added option to view DDI profiles in XML or HTML format
- Create issues in EOSC Helpdesk, rather than JIRA

## A short description of each change made as part of the release

### Added

- Add Release Report to cessda.cmv directory root 144
  ([#144](https://github.com/cessda/cessda.cmv.core/issues/144))
- Add the Maven wrapper to the repository
  ([#98](https://github.com/cessda/cessda.cmv.core/issues/98))
- Added latest version redirects for monolingual CDC profiles
  ([#63](https://github.com/cessda/cessda.cmv.server/issues/63))
- Enabled CORS for the Swagger documentation and the public API
  ([#67](https://github.com/cessda/cessda.cmv.server/issues/67))
- Validate the documents against the XML schema when validating in the user interface
  ([#68](https://github.com/cessda/cessda.cmv.server/issues/68))
- Transform the metadata profiles as part of the build process
  ([#DOCS-21](https://github.com/cessda/cessda.cmv.documentation/issues/21))

### Changed

- Improve SQAaaS score for cessda.cmv component
  ([#146](https://github.com/cessda/cessda.cmv/issues/146))
- Replace references to Bitbucket
  ([#107](https://github.com/cessda/cessda.cmv.core/issues/107))
- Improve SQAaaS score for cessda.cmv.core component
  ([#106](https://github.com/cessda/cessda.cmv.core/issues/106))
- Update the readme to include the GitHub source URL
  ([#97](https://github.com/cessda/cessda.cmv.core/issues/97))
- Improve SQAaaS score for cessda.cmv.server component
  ([#83](https://github.com/cessda/cessda.cmv.core/issues/83))
- General code refactor
  ([#86](https://github.com/cessda/cessda.cmv.core/issues/86))
- Update OpenJDK to 17
  ([#64](https://github.com/cessda/cessda.cmv.server/issues/64))
- Replace the JIRA feedback form with the EOSC helpdesk feedback form
  ([#79](https://github.com/cessda/cessda.cmv.server/issues/79))

### Fixed

- Fix tests failing on Windows due to differences in platform string conventions
  ([#85](https://github.com/cessda/cessda.cmv.core/issues/85))
- Fixed EQB v0.1.1 profile redirect
  ([#66](https://github.com/cessda/cessda.cmv.server/issues/66))

## Impact

Specify any steps users or admins need to take to support the new release

None.

## Additional resources

Link to press release and/or document about new features or enhancements
in the release

None.
