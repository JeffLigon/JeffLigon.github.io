# README

This is an example website built from a template from https://templated.co/fullmotion


## Steps involved with notes

Introduction
- (00:34) Creating a website
    - notes from this step
    - default thumbnail URL for YouYube videos is: https://img.youtube.com/vi/aHjpOzsQ9YI/hqdefault.jpg 
- (38:41) Getting a custom URL
    - notes from this step
- (42:45) Getting web hosting
- (48:25) Creating a custom email address
- (48:25) Updating Nameservers
    - signed up for free domain name at https://www.cloudns.net/ -  pluto.cloudns.cl
    - pointed to IOT1 server at http://4.28.45.252/
    - synced files to IOT1:
       - rsync -rv /Users/jeligon/OneDrive/Coding/GitHub/templated-fullmotion/ jeff@4.28.45.252:/home/jeff/docker/templated-fullmotion/
    - created nginx docker container
         - Dockerfile-templated-fullmotion:
         - FROM nginx
         - COPY templated-fullmotion /usr/share/nginx/html
         - docker build -t templated-fullmotion -f Dockerfile-templated-fullmotion .
    - launch docker container with website:
         - docker run -d -p 1882:80 --restart unless-stopped templated-fullmotion
    - test website at http://4.28.45.252:1882/ and http://pluto.cloudns.cl:1882/
         - This worked but removed link from cloudns to 4.28.45.252 after.
- (51:35) Hosting for free with GitHub Pages
    - Now pushing to https://github.com/JeffLigon/JeffLigon.github.io
    - Test website at:  https://jeffligon.github.io/
    - changed domain in GitHub to point to custom domain name so now works at http://pluto.cloudns.cl/
- (56:08) Updating DNS Settings
- (59:15) Conclusion


### References

- **How to Put a Website Online: Template, Coding, Domain, Hosting, and DNS**. YouTube. Available at: https://www.youtube.com/watch?v=NQP89ish9t8&feature=youtu.be
