# Project 7 - WordPress Pentesting

Time spent: **10** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

	1. (Required) Wordpress Plugin Tribulant Newsletters 4.6.4.2 - File Disclosure / Cross-Site Scripting
  - [ ] Summary: Multiple File Disclosure and cross site scripting vulnerabilities. 
    - Vulnerability types:File Disclosure / XSS
    - Tested in version: WP 4.2 // Tribulant 4.6.4.1
    - Fixed in version: 4.6.4.3
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: as wp-admin, use the following URL:
  http://vmdistillery.vm/wp-admin/admin-ajax.php?action=newsletters_gauge&value=1});alert(1);</script> 
  which generates an alert (as seen in the screenshot).
  - [ ] Affected source code:
  	-[Link 1](https://www.exploit-db.com/exploits/42129)	
  
	
	2. (Required) WordPress <= 4.2.2 - Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: This is an XSS attack that allows for privilege escalation with a post. [CVE-2015-5622]
    - Vulnerability types: XSS, Privilege Escalation
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: Create a user profile with contributor or author priveleges. Add the following text to the post
  <a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>
  This specific text creates an alert message when the mouse goes over the link displayed in the post
  - [ ] Affected source code:
    - [Link 1](https://wpvulndb.com/vulnerabilities/8111)
    - [Link 2](https://nvd.nist.gov/vuln/detail/CVE-2015-5622)

	3. (Required) WordPress <= 4.4 Admin level XSS
  - [ ] Summary: This is a XSS attack against a logged in admin that 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.4.1
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: I was only able to recreate this once (using 4.2), then got the error message "cheatin' uh"
  This is a DOM attack, so provide the following link:
  http://wpdistillery.vm/wp-admin/customize.php?theme=%3Csvg%20onload=alert(1)%3E
  (for a logged in admin level user)
  - [ ] Affected source code:
    - [Link 1](https://twitter.com/brutelogic/status/685105483397619713?lang=en)

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)
- [Exploit-Database Reference] (https://www.exploit-db.com/exploits/42129/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
