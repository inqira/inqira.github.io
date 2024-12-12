---
title: "Cannot Download Pods: Quick Fix for CocoaPods Installation Issues"
date: 2024-12-12
updated: 2024-12-12
author: inqira
tags: [iOS, CocoaPods, Troubleshooting, MacOS, Flutter]
excerpt: "A quick guide to resolving CocoaPods installation issues."
---

When running `pod install`, you might encounter errors like:

```
CDN: trunk URL couldn't be downloaded: https://cdn.jsdelivr.net/cocoa/Specs/a/7/5/AFNetworking/4.0.1/AFNetworking.podspec.json Response: SSL connect error

CDN: trunk URL couldn't be downloaded: https://cdn.cocoapods.org/
```

This happens because the CDN address is blocked or the CDN is blocking your connection.

## Solution

To resolve this issue, follow these steps:

### 1. Modify Your Podfile  
Add the following line at the top of your `Podfile`:

```ruby
source 'https://github.com/CocoaPods/Specs.git'
```

### 2. Remove the Podfile.lock File  
This file can sometimes cause conflicts. You can remove it by running:

```bash
rm Podfile.lock
```

### 3. Remove the Trunk Repository  
Run the following command to remove the trunk repository:

```bash
pod repo remove trunk
```

### 4. Install Pods Again  
Finally, run the command to install your pods:

```bash
pod install
```

This solution changes the source to GitHub’s repository instead of using the CDN, allowing you to download pods without being blocked. 