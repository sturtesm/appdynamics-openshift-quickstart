#Installation of AppDynamics Agent into an OpenShift Application:

##Step 1. Create an OpenShift app

* Create an OpenShift account: http://openshift.redhat.com
* Set up your local machine with the client tools: https://www.openshift.com/developers/rhc-client-tools-install
* Create a JBoss application (you can call your application whatever you want). 

```
   $ rhc app create appdynamicsdemo jbossews-2.0 --from-code https://github.com/Appdynamics/openshift-appdynamics-quickstart
```

##Step 2. Sign up for AppDynamics by visiting the following web-page:

https://portal.appdynamics.com/account/signup/signupForm/

##Step 3. Log into your AppDynamics Controller 

Log in using your account details in your email titled "Welcome to your AppDynamics Pro SaaS Trial" 
or the account details you have entered during On-Premise installation.

##Step 4.  Configure the AppDynamics agent (from your app's local git repo):

a. Go to the AppDynamics agent configuration directory.

```
		$ cd $OPENSHIFT_REPO_DIR/AppServerAgent/conf
```

b. Edit the file controller-info.xml

c. Change CONTROLLER_HOST, ACCOUNT_NAME and ACCOUNT_ACCESS_KEY to be your values determined after sign up.

##Step 5.  Commit your changes to git

```
	$ git add controller-info.xml
	$ git commit -m "AppDynamics Agent configuration commit"
	$ git push
```

##Step 6. Visualize and start monitoring your app 

Go to http://\<CONTROLLER_HOST\>[:\<CONTROLLER_PORT\>]/controller to see your application integrated.

If CONTROLLER_PORT is 80 (as it is for SaaS controllers) it may be omitted.
