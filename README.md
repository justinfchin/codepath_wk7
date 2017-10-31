# Project 7 - WordPress Pentesting

Time spent: **16** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. Authenticated Stored XSS via Image Filename
  - [X] Summary: .  
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.6
  - [X] GIF Walkthrough: 
    - ![1](/gifs/1.gif?raw=true)
  - [X] Steps to recreate: 
    1. Log in as Admin.
    2. Create an .jpg file with '''<img src=a onerror=alert(document.cookie)>''' in the file name. 
    3. Upload it into the media section.
    4. View attachment page. 
    5. Note: this also works for media filename 
  - [X] Affected source code:
    - [Vulnerability DB](https://wpvulndb.com/vulnerabilities/8615)
    - [Source Code](https://github.com/WordPress/WordPress/commit/c9e60dab176635d4bfaaf431c0ea891e4726d6e0)

2. Authenticated Shortcode Tags XSS
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.2
  - [X] GIF Walkthrough:
    - ![2](/gifs/2.gif?raw=true)
  - [X] Steps to recreate:
    1. As admin, write in the comment '''<a href = "XSS" onmouseover=alert(1) rel="nofollow">CLICK ME!</a>'''
    2. Hover over the link. 
  - [X] Affected source code:
    - [Vulnerability DB](https://wpvulndb.com/vulnerabilities/8186)
    - [Source Code](https://github.com/WordPress/WordPress/commit/f72b21af23da6b6d54208e5c1d65ececdaa109c8)

3. Authenticated Stored XSS in YouTube URL Embeds
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.2
  - [X] GIF Walkthrough: 
    - ![3](/gifs/3.gif?raw=true)
  - [X] Steps to recreate: 
    1. As admin, edit a page.
    2. Insert the following '''[embed src='https://youtube.com/embed/1234\x3csvg onload=alert(1)\x3e'][/embed]'''
    3. Go to view the page.  
  - [X] Affected source code:
    - [Vulnerability DB](https://wpvulndb.com/vulnerabilities/8768)
    - [Source Code](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)

4. Authenticated Stored XSS
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.4
  - [X] GIF Walkthrough: 
    - ![5](/gifs/5.gif?raw=true)
  - [X] Steps to recreate: 
    1. Upload User Comments Containing XSS Attack
    '''javascript
    POW<script>alert(1)</script>
    '''
  - [X] Affected source code:
    - [Vulnerability DB](https://wpvulndb.com/vulnerabilities/8358)
    - [Source Code](https://github.com/WordPress/WordPress/commit/7ab65139c6838910426567849c7abed723932b87)  

## Assets

List any additional assets, such as scripts or files
- None

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2017] [Justin Chin]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.# CodePath Cybersecurity - Week7
