# Asset Proxy for Storyblok CDN

This repo contains redirect rules to mask the asset CDN from storyblok.

## Standard Asset URLs

Use these for most assets:

* For assets from `https://a.storyblok.com` use `https://assets.stanford.edu/a`
* For assets from `https://a-us.storyblok.com` use `https://assets.stanford.edu/a-us`
* For assets from `https://img2.storyblok.com` use `https://assets.stanford.edu/i`
* For private assets from `https://private-img.storyblok.com` use `https://assets.stanford.edu/p`

## CORS-Enabled Asset URLs (a2 domains)

**When to use:** Use these URLs when you need to access assets from JavaScript in a cross-origin context (e.g., loading videos with JavaScript players, processing images with canvas, or fetching data with fetch/XMLHttpRequest).

**Why:** The a2 domains (`a2.storyblok.com` and `a2-us.storyblok.com`) include `Access-Control-Allow-Origin: *` headers, which allow browsers to access the resources from any domain. Standard asset URLs may not include these CORS headers, causing browser security errors when accessed via JavaScript.

* For CORS-safe assets from `https://a2.storyblok.com` use `https://assets.stanford.edu/a2`
* For CORS-safe assets from `https://a2-us.storyblok.com` use `https://assets.stanford.edu/a2-us`

**Note:** For simple `<img>`, `<video>`, or `<link>` tags in HTML, you don't need the a2 domains. Use standard URLs instead.

## Examples: 

**Image URL**  
Raw URL: `https://img2.storyblok.com/f/78141/360x360/1f41a7549e/do-not-delete-me-i-am-used-for-testing.png`  
Masked URL: `https://assets.stanford.edu/i/f/78141/360x360/1f41a7549e/do-not-delete-me-i-am-used-for-testing.png`  

**Asset URL (Files such as PDFs and word docs)**  
Raw URL: `https://a.storyblok.com/f/78141/x/abc123def456/sample-document.pdf`  
Masked URL: `https://assets.stanford.edu/a/f/78141/x/abc123def456/sample-document.pdf`  

**CORS-Safe Asset URL (For JavaScript cross-origin access)**  
Raw URL: `https://a2.storyblok.com/f/78141/1920x1080/def789ghi012/sample-video.mp4`  
Masked URL: `https://assets.stanford.edu/a2/f/78141/1920x1080/def789ghi012/sample-video.mp4`  

**Private Asset URL (Signed URLs)**  
Raw URL: `https://private-img.storyblok.com/200x200/https://s3.amazonaws.com/a.storyblok.co...f45cbf0b01242.png`  
Masked URL: `https://assets.stanford.edu/p/200x200/https://s3.amazonaws.com/a.storyblok.co...f45cbf0b01242.png`  

**USA Asset URL (Files such as PDFs and word docs)**  
Raw URL: `https://a-us.storyblok.com/f/78141/x/jkl345mno678/report.docx`  
Masked URL: `https://assets.stanford.edu/a-us/f/78141/x/jkl345mno678/report.docx`  

**USA CORS-Safe Asset URL (For JavaScript cross-origin access)**  
Raw URL: `https://a2-us.storyblok.com/f/78141/x/pqr901stu234/subtitles.vtt`  
Masked URL: `https://assets.stanford.edu/a2-us/f/78141/x/pqr901stu234/subtitles.vtt`  

## Resources
* https://www.storyblok.com/docs/content-and-asset-cdn
* https://www.storyblok.com/docs/custom-assets-domain
* https://stanfordits.atlassian.net/wiki/spaces/ADAPT/pages/620265473/Storyblok+Undocumented+Asset+Information
* https://www.storyblok.com/docs/concepts/assets.html