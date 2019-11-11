# Project 7 - WordPress Pentesting

Time spent: **4** hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. Unathenticated stored cross-site scripting
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [x] GIF Walkthrough: 
      Attacker:
  <img src="https://github.com/ThoMot/CodePathLab7-8/blob/master/gifs/attacker1.gif">
      Admin:
  <img src ="https://github.com/ThoMot/CodePathLab7-8/blob/master/gifs/admin1.gif">
  
  - [x] Steps to recreate: 
      - add a comment with: <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>
      - make sure comment is longer than accepted length for database storage (64kb)
      - Admin will approve comment
      - Now admin can run the script on accident and the attacker will have access to his account
  - [x] Affected source code:
    - [Link 1](https://wpvulndb.com/vulnerabilities/7945)
2. Authenticated Cross-Site Scripting (XSS) via Media File Metadata
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.7.3
  - [x] GIF Walkthrough: 
  <img src="https://github.com/ThoMot/CodePathLab7-8/blob/master/gifs/XSSmp3Vulnerability.gif">
  
  - [x] Steps to recreate: 
      Add mp3 with embedded script in description
      Get an adming to make a new post and put this mp3 into a playlist on there
      when it is embedded the script is run
      
  - [x] Affected source code:
    - [Link 1](https://blog.sucuri.net/2017/03/stored-xss-in-wordpress-core.html)
3. Authenticated Shortcode Tags Cross-Site Scripting
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.3.1
  - [x] GIF Walkthrough: 
  <img src="https://github.com/ThoMot/CodePathLab7-8/blob/master/gifs/XSSinShortCode.gif">
  
  - [x] Steps to recreate: 
    Get an admin or editor to post the following short code format on their page: 
    This is a XSS attack[caption width="2" caption='<a href="' ">]</a><a href="http://onMouseOver='alert(1)'">Click here!</a>
    Could be perceived as a link but is not
    
  - [x] Affected source code: 
    - [Link 1](https://wpvulndb.com/vulnerabilities/8186)

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

I tried a lot of different vulnerabilities but a lot of them I could not get to work..

## License

    Copyright [2019] [Thora Mothes]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
