# eb-deploy-base
This repo is designed to speed up EB deployments for single page React applications. 

To install the `eb-cli`, following the instructions [here](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html).

Once `eb-cli` is installed, copy and paste the public directory of your production build of your application into the web folder. Note: all of your necessary items must be under a directory called public, as in the example below. 
```
web/
    public/
        index.html
        bundle.js
        main.css
        assets/
```
Next, run `eb init` and follow the steps in the command line to set up the eb instance. Finally, when ready to deploy, run `eb deploy`.

Sometimes, EB will throw an error due to a node modules date being too old. To fix, run `find . -mtime +10950 -print -exec touch {} \;` before deploying.


> Last updated: 2020-03-31