# Change Log
This project adheres to [Semantic Versioning](http://semver.org/).

This CHANGELOG follows the format listed  [here](https://github.com/sensu-plugins/community/blob/master/HOW_WE_CHANGELOG.md)

## [Unreleased]

## [4.1.0] - 2019-012-12
### Added
- Updated asset build targets to support centos6

## [4.0.0] - 2019-04-18
### Breaking Changes
- Update minimum required ruby version to 2.3. Drop unsupported ruby versions.
- Bump `sensu-plugin` dependency from `~> 1.2` to `~> 4.0` you can read the changelog entries for [4.0](https://github.com/sensu-plugins/sensu-plugin/blob/master/CHANGELOG.md#400---2018-02-17), [3.0](https://github.com/sensu-plugins/sensu-plugin/blob/master/CHANGELOG.md#300---2018-12-04), and [2.0](https://github.com/sensu-plugins/sensu-plugin/blob/master/CHANGELOG.md#v200---2017-03-29)

### Added
- Travis build automation to generate Sensu Asset tarballs that can be used n conjunction with Sensu provided ruby runtime assets and the Bonsai Asset Index
- Require latest sensu-plugin for [Sensu Go support](https://github.com/sensu-plugins/sensu-plugin#sensu-go-enablement)

## [3.2.1] - 2018-08-31
### Fixed
- check-whois-domain-expiration.rb: corrected warn and critical flag value parsing per: https://github.com/sensu-plugins/sensu-plugins-network-checks/issues/81 (@aww-yiss)

## [3.2.0] - 2018-08-06
### Added
 - metrics-net.rb: allow including only interfaces whos status is `up` (@johannagnarsson)

## [3.1.2] - 2018-06-10
### Fixed
- metrics-netif.rb: allow you to actually pass in a value for `--average-key` (@scones)

## [3.1.1] - 2018-03-27
### Security
- updated yard dependency to `~> 0.9.11` per: https://nvd.nist.gov/vuln/detail/CVE-2017-17042 (@majormoses)

## [3.1.0] - 2018-03-17
### Changed
- check-netfilter-conntrack.rb: ditch the associated shellscript and turned into pure Ruby.

## [3.0.0] - 2018-03-17
### Security
- updated rubocop dependency to `~> 0.51.0` per: https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-8418. (@majormoses)

### Breaking Changes
- removed ruby `< 2.1` support (@majormoses)

### Changed
- appeased the cops and updated cop config (@majormoses)

## [2.3.1] - 2018-02-28
### Changed
- update whois-parser gem dependency to version 1.0.1 (@amdprophet)

## [2.3.0] - 2018-02-09
### Changed
- check-whois-domain-expiration.rb, check-whois-domain-expiration-multi.rb and check-jsonwhois-domain-expiration.rb: better resilience against errors, better reporting of erroneous responses (@DrMurx)

## [2.2.0] - 2018-02-02
### Added
- check-ports.rb: support for multiple hosts (@DDSloan96)

### Changed
- updated changelog guidelines location (@majormoses)

## [2.1.1] - 2018-01-06
### Fixed
- check-whois-domain-expiration-multi.rb: report a `critical` error on a domain that it gets back an empty expires_on. (@edgan)

## [2.1.0] - 2017-11-03
### Added
- metrics-interface.rb: Option to listen to specfic interface. (@parin921996)

## [2.0.1] - 2017-08-01
### Added
- ruby 2.4 testing to travis (@majormoses)

### Fixed
- misc changelog na PR template fixes (@majormoses)
- check-whois-domain-expiration.rb: "Check failed to run: invalid date" caused by a change to the whois gem which removed the parser from the main repository (issue #59) (@akatch)

## [2.0.0] 2017-06-07
### Breaking Changes
- check-multicast-groups.rb: Stop loading system wide settings from `settings['check-multicast-groups']` and use only the config specified as `-c` (#57 via @maoe)

## [1.2.0] - 2017-06-07
### Added
- Added check-ports-bind.rb (@hanynowsky)
- Added interval option to metrics-netif.rb (@Evesy)
- metrics-netif.rb: expose average-key option that is used to `grep` to more easily handle locale issues (@majormoses)
- metrics-netif.rb: unknown if it can not find `sar` in its `$PATH` (@majormoses)
- check-ping.rb: unknown if using `--reports` and do not have `mtr` installed and in "$PATH" (@majormoses)

### Fixed
- metrics-netstat-tcp.rb: Option to disable IPv6 check (#44 via @MattMencel)
- check-multicast-groups.rb: Fix undefined method deep_merge for []:Array (@maoe)
- check-whois-domain-expiration-multi.rb does not fail as timeout is cast to integer (@majormoses)

### Changed
- check-banner.rb: Option to enable SSL socket for secure connection

## [1.1.0] - 2016-08-07
### Added
- metrics-netstat-tcp.rb: Add IPv6 state counts (@mlf4aiur)

### Fixed
- check-ping.rb: Fix false positives (#34 via @kai101)

## [1.0.0] - 2016-06-14
### Fixed
- check-whois-domain-expiration-multi.rb: Handle whois errors better by retrying failed lookups
- Use Timeout.timeout not deprecated Object#timeout

### Added
- check-whois-domain-expiration-multi.rb: Add timeout option
- Support for Ruby 2.3.0

### Removed
- Support for Ruby 1.9.3

### Changed
- Update to Rubocop 0.40 and cleanup

## [0.2.4] - 2016-04-02
### Fixed
- metrics-ping.rb: Fix error when a host cannot be pinged. Convert to a proper metrics check.

### Added
- basic check for netfilter conntrack
- Option for newline character in write string for check-banner

## [0.1.4] - 2016-01-22
### Added
- IPv6 support for check-ping

## [0.1.3] - 2016-01-15
### Added
- Added check-socat.rb

## [0.1.2] - 2016-01-08
### Fixed
- Bugfix for `check-whois-domain-expiration-multi` and `check-jsonwhois-domain-expiration`: return a warning-level response if there were any domains with expiration dates in the warning time period but none in the critical time period.

## [0.1.1] - 2015-12-21
### Added
- activesupport runtime dependency locked to 4.2.5 to ensure that we do not need ruby > 2.2

## [0.1.0] - 2015-12-03
### Added
- Added include and ignore options for devices at `metrics-net.rb`

### Changed
- Updated whois gem to 3.6.3

## [0.0.8] - 2015-11-12
### Added
- Support multiple port ranges for check-ports

### Changed
- Updated net-ping gem to 1.7.8
- Updated whois gem to 3.6.2

## [0.0.7] - 2015-10-27
### Added
- Added `check-jsonwhois-domain-expiration.rb` plugin which uses the API at https://jsonwhois.com to check domain expiry.

## [0.0.6] - 2015-10-01
### Added
- Added new port check

### Changed
- Changed name of check-ports to check-ports-nmap

## [0.0.5] - 2015-08-05
### Added
- Added new metrics-ping.rb plugin
- Added check-whois-domain-expiration-multi.rb plugin to check multiple domains for expiration using whois records

### Changed
- general gem cleanup

## [0.0.4] - 2015-07-14
### Changed
- updated sensu-plugin gem to 1.2.0

## [0.0.3] - 2015-06-03
### Fixed
- check-rbl.rb had a typo in the require statement for 'dnsbl-client'

### Changed
- cleaned up the gemspec
- cleaned up Rakefile
- updated documentation links

### Refactored
- renamed check-ports.rb to check-ports-nmap.rb
- added check-ports.rb based in TCPSocket instead of nmap

### Refactored
- renamed check-ports.rb to check-ports-nmap.rb
- added check-ports.rb based in TCPSocket instead of nmap

## [0.0.2] - 2015-06-03

### Fixed
- added binstubs

### Changed
- removed cruft from /lib

## 0.0.1 - 2015-05-01

### Added
- initial release

#### 0.0.1.alpha.7

* add gem metadata
* add chef provisioner to Vagrantfile
* fix ruobcop issues
* pin all dependencies

#### 0.0.1.alpha.6

* added check-whois-domain-expiration #7

#### 0.0.1.alpha.5

* updated check-banner to allow checking for no banner

#### 0.0.1.alpha.4

* added check-mtu functionality #7

#### 0.0.1.alpha.3

* additional functionality to check-banner #6

#### 0.0.1.alpha.2

* all tests pass
* initial gem release

#### 0.0.1.alpha.1

* initial release, same as community repo

[Unreleased]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/4.1.0...HEAD
[4.1.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/4.0.0...4.1.0
[4.0.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/3.2.1...4.0.0
[3.2.1]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/3.2.0...3.2.1
[3.2.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/3.1.2...3.2.0
[3.1.2]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/3.1.1...3.1.2
[3.1.1]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/3.1.0...3.1.1
[3.1.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/3.0.0...3.1.0
[3.0.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/2.3.0...3.0.0
[2.3.1]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/2.3.0...2.3.1
[2.3.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/2.2.0...2.3.0
[2.2.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/2.1.1...2.2.0
[2.1.1]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/2.1.0...2.1.1
[2.1.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/2.0.1...2.1.0
[2.0.1]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/2.0.0...2.0.1
[2.0.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/1.2.0...2.0.0
[1.2.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/1.1.0...1.2.0
[1.1.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/1.0.0...1.1.0
[1.0.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.2.4...1.0.0
[0.2.4]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.1.4...0.2.4
[0.1.4]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.1.3...0.1.4
[0.1.3]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.1.2...0.1.3
[0.1.2]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.1.1...0.1.2
[0.1.1]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.1.0...0.Ï.1
[0.1.0]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.0.8...0.1.0
[0.0.7]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.0.7...0.0.8
[0.0.7]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.0.6...0.0.7
[0.0.6]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.0.5...0.0.6
[0.0.5]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.0.4...0.0.5
[0.0.4]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.0.3...0.0.4
[0.0.3]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.0.2...0.0.3
[0.0.2]: https://github.com/sensu-plugins/sensu-plugins-network-checks/compare/0.0.1...0.0.2
