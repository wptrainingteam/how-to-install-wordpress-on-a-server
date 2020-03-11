# How To Install WordPress On A Server

## Issues:

*   PC images should be replaced with macOS equivalents
*   Database permissions need to be reworked to include only the ones that are **needed**

## Description

In this lesson, you will learn how to get WordPress up and running on-line. This lesson will walk you through the tools, as well as the steps needed to setup WordPress on a live server.  

## Objectives

After completing this lesson, you will be able to:

*   Download and extract the WordPress installation files
*   Connect your server with (S)FTP.
*   Install WordPress.
*   Set up a database for WordPress.
*   Install script.
*   Anticipate and correct any possible problems.

## Prerequisite Skills

You will be better equipped to work through this lesson if you:

*   Have purchased a domain name and hosting account

## Assets

*   [WordPress](https://wordpress.org/download/) Source Files
*   [Cyberduck](https://cyberduck.io/) FTP Client
*   An archive utility (e.g. [7-Zip](http://www.7-zip.org/))

## Screening Questions

*   Do you already have a domain name and hosting account?
*   Have you used WordPress before?
*   Do you know how to use (S)FTP software?
*   Do you know what a database is?

## Teacher Notes

*   You will want to have a hosting account for the demo
*   Make sure that you test the ability to connect to the hosting account at the venue where you are teaching. Some schools and networks block (S)FTP connections and you will need to request the ability to use (S)FTP connections (port 21 for FTP, port 22 for SFTP).
*   Sometimes it can take a while to complete the upload of WordPress. You may want to have the WordPress files already uploaded to the server before you start. You would then show how to connect with FTP to the server, show what the files look like once they're uploaded and then proceed to the database setup and installation script.

## Hands-on Walkthrough

The following steps walk through how to install WordPress.

### Why You Need a Domain Name and Hosting Account

A domain name is what people type into a browser to access your website. For example, yourdomain.com is a domain name. For this exercise, we will use the domain name wordpresshostingexample.com. You can purchase a domain name at the same company where you purchase your hosting account. A hosting account, or a server, store the files for your website. When you setup and install WordPress, you are doing it on your server or hosting account. To use a metaphor, think of a domain name as the address for a house and the hosting account as the house itself. During the installation process, you will need to login or connect to your hosting account to do things create a database or upload the WordPress files. WordPress.org <span class="s1">offers a <span class="s2">[list of some hosting providers](https://wordpress.org/hosting/)</span></span> where you can purchase a domain name and hosting account. Many other hosting companies exist, however, when you purchase a hosting account you will want to make sure they support WordPress. For this walkthrough, we will be using Bluehost.

### Download and Extract the WordPress Installation Files

Before you upload WordPress to your server, you must first download it. Go to the [WordPress download page](https://wordpress.org/download/) and download the latest version of WordPress to your local computer. For this example, we will use the free, cross-platform archive manager [7-Zip](http://www.7-zip.org/). Once you have 7-Zip installed, locate the wordpress.zip file you just downloaded to your computer. Double-click the file to open 7-Zip. [![7-Zip Archive Manager Interface](/images/extract-wprdpress-with-7-zip.jpg)](/images/extract-wprdpress-with-7-zip.jpg) Select the **wordpress** folder and extract the files to a location you can get to. [![7-Zip Archive Manager extraction interface](/images/extracted-wprdpress.jpg)](/images/extracted-wprdpress.jpg)  

### How to Connect to Your Server with FTP

File Transfer Protocol (FTP) Software allows you to connect to your hosting account and drag and drop files from your computer to and from your server. When you upload files to your server, they become visible to people who visit your domain name. ![Cyberduck FTP, the initial screen on login](/images/How-to-Connect-to-Your-Server-with-FTP.jpg) For this example, we will use the free, cross-platform FTP software [Cyberduck](https://cyberduck.io/). Once you install and open Cyberduck, click **Open Connection** and enter in the following information to connect to your server: ![Cyberduck FTP, login window with FTP selected](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-26-at-5.59.15-PM.png)

*   Server: the domain name for your site
*   Username: should receive in the welcome email from hosting provider
*   Password: should receive in the welcome email from hosting provider

You should have received this information from your hosting company in an initial welcome email. ![Cyberduck FTP, use SFTP prompt screen](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-26-at-5.59.22-PM.png) During the login process you may receive a message that tells you that you are using an insecure connection and that a secure connection is available. The insecure method of connecting is called FTP and a secure way is called SFTP. If you see this message it means that SFTP is available and you should try clicking "Change" to use the more secure method of connecting. SFTP is the preferred method of connecting to your server as it protects your credentials as you are logging in. ![Cyberduck FTP, use SFTP confirmation screen](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-26-at-5.59.27-PM.png) If you choose to use SFTP you may need to click Continue to accept the SFTP security certificate. ![Cyberduck FTP, logged in to root with public_html folder selected](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-26-at-5.59.36-PM.png) Once you're connected to the server you should see a screen that shows the root level files you have access to. With most shared hosting accounts, when you first login with (S)FTP you will see a number of folders and one is named public_html. Depending on your hosting provider your public_html folder may have an alternative name such as “htdocs”. Go ahead and click into your public_html (or htdocs) folder. Anything that goes in this folder will then be accessible on your site. This is where we will install WordPress. ![Cyberduck FTP, logged in to empty public_html folder](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-26-at-5.59.40-PM.png) NOTE: If when you login with (S)FTP and you don't see any public_html or htdocs folder then it means you are probably already inside of the correct folder and can proceed to the next step.

### Uploading WordPress Files

Login to your server using (S)FTP and navigate into the folder where you want to install WordPress. ![WordPress folder selected in Finder](/images/uploading-wordPress-files.jpg) If you want to install WordPress in the root of your site, for example, at yourdomain.com then you will upload the WordPress files directly into the public_html folder. However, if you want to install WordPress at yourdomain.com/test/ then you would go into your public_html folder, create a new folder called "test" and then navigate into that folder. Once you have navigated into the correct folder on your server, select all of the WordPress files and drag and drop them from your computer into the Cyberduck window. Make sure you drag and drop the actual files and not the actual WordPress folder. ![Dragging and dropping WordPress files from Finder to Cyberduck](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-12.22.12-PM.png) It may take a while for all of the files to upload. If the process is interrupted, it's best to delete the files that had been uploaded and then start over from the beginning with an empty public_html folder. While you wait for your files to upload you can move on to the next step of installing a database.

### How to Setup a Database for WordPress

WordPress stores all of its text-based content in a database, a tool for storing and organizing information. This means that when you post a page or post, all of the content of that post gets saved into a database. ![cPanel screen of Bluehost](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-1.51.56-PM.png) The process to setup a database changes depending on hosting providers. However, most hosts use the software tool known as cPanel for managing the process of setting up databases. If your hosting provider does not have cPanel, you can search their knowledge base for how to create a database. For our example site, using Bluehost, we login and then click on **Hosting** and **cPanel** to get to the screen pictured above. ![cPanel screen showing the icon for MySQL Database Wizard circled](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-12.36.10-PM.png) To setup a database, login to your cPanel hosting control panel and search for and click on **MySQL DB Wizard**. ![cPanel MySQL Database Creation - Step 1](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-12.38.00-PM.png) The first step of setup process involves naming your database. You can choose your short name with no spaces, however, for this example, we're going to use wp to designate that the database is for WordPress. Note that the wp is appended to the end of a unique username for your hosting account. So, although we only enter in wp, the actual database name is going to be wordprz4_wp. Make sure to write down the database name because you will need it later. ![cPanel MySQL Database Creation - Step 2](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-12.38.18-PM.png) Next you will be prompted to create a username. For our example we're going to use the wpuser, however, you can select your username. Note again that the final username will be the unique username for the server, plus the database username you create. So, for our example, the final database username is wordprz4_wpuser, not just wpuser. cPanel offers a [strong password](https://en.wikipedia.org/wiki/Password_strength#Guidelines_for_strong_passwords) generator, which will auto-generate a [strong password](https://en.wikipedia.org/wiki/Password_strength#Guidelines_for_strong_passwords). If you decide to make your password, be sure it is strong. If you choose a password with a low strength, hackers will easily be able to guess your password, compromising your database and potentially your site. Make sure to record the password somewhere, because you will need it when going through the install script. ![cPanel MySQL Database Creation - Step 3](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-12.38.29-PM.png) In the final step you grant the user access to the database. Click the checkbox for **All Privileges** and then **Next Step**. You should now have the following:

*   Your database name (ie wordprz4_wp)
*   Your database username (ie wordprz4_wpuser)
*   Your database password (something secure)
*   Granted user privileges to the database

Now that we have our WordPress files uploaded to the server and our database setup, we can move on to the last step of the installation process, walking through the install script.

### The WordPress Install Script

The WordPress install script is a series of pages where you select and set options for configuring WordPress. Once you have your files uploaded and database created you can access the install script by using your browser go to the URL where you have the WordPress files uploaded (in our example case: wordpresshostingexample.com).  It will redirect you to the Install page. ![The language selection option of the WordPress install script](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-1.44.23-PM.png) First, select your language and click **Continue**. Next, you're presented with a screen asking for your database information. You should have all of these values from the previous steps, so enter the information and click on the **Let's go!** button to move forward. ![WordPress Install Screen with information entered](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-1.56.43-PM.png) First, enter the database name, username, and password we created earlier. The database host will likely be localhost and you can leave with this value. Some hosting providers, like MediaTemple, make you use something different (see the Possible Problems section for more details on this). The Table Prefix is something that you will want to change for security reasons. Makeup something 3-6 characters followed by an underscore. For our demo, we choose "myexm_" as the Table Prefix. ![WordPress Install Script - Information Details](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-2.57.16-PM.png) Once you have the form complete, click on **Submit** and it should take you to a screen that says it was able to connect to your database and is ready to run the rest of the install. Click to **Run the Install**. In the final step, you enter information about the WordPress site itself. Here you can set the title for the site, which you can change later if needed. You will also choose a username and password to use to login to your WordPress site. This should be different information from your database username and password. Also, make sure to enter the correct email address. WordPress will use this for password resets and site notifications. The Privacy checkbox adds the code to your site like a robots.txt file that gives search engine instructions on whether or not to index content from your site. While building a site you should **uncheck** this. When you finish setting up your site and it's ready for the general public, you can update this setting under **Settings > Reading > Search Engine Visibility**. Note that unchecking this box will not make your site private or prevent people from visiting it. It only requests that search engines do not visit the site, however, as WordPress points out, "It is up to search engines to honor this request." After completing the form, click **Install WordPress** and you should see a final screen telling you WordPress is installed. You'll also see your username and a link to login.

### How to Login to WordPress

![WordPress Login Page](/images/login-wp-admin.jpg) To login to your WordPress site you simply type in the URL for your site and add /wp-admin/ to the end. For example, the login URL for our test side is http://wordpresshostingexample.com/wp-admin/. This will lead you to a page where you can enter your username and password as well as receive instructions for resetting your password. If a WordPress site has registration enabled, you will also see a link to Register on this page.

### Possible Problems

When installing WordPress you may come across some of the following problems:

#### Can't login with (S)FTP

If you have trouble connecting with the (S)FTP client there are a couple of steps you can take:

*   Try copying and pasting your login information into the (S)FTP software client instead of typing it. You may also try typing instead of copying and pasting.
*   Check to make sure that you can access your domain name from the browser. If you cannot visit your domain name in the browser and you purchased your domain name and hosting from different companies you may need to update something called your DNS. Try contacting the domain name registrar or hosting provider for help if this is the case.
*   Check your ports. If you choose to use (S)FTP you will likely need to enter a different value in the Port field. Your hosting provider can tell you if this is the case.

In general, if you have trouble with (S)FTP, your hosting company should be able to help you resolve the problem.

#### Files don't finish uploading

The WordPress files can take a long time to upload and you run the risk of something interrupting the upload process. If this happens it is best to delete all of the files uploaded and start the process over. Make sure, however, not to delete your actual public_html folder as that will break your hosting account.

#### Problem Connecting to Database

![WordPress Install Screen for Database Connection Error](http://make.wordpress.org/training/files/2014/10/Screen-Shot-2014-10-28-at-2.03.03-PM.png) During the database portion of the install script you may see the error message above that tells you WordPress was unable to connect to your database. Please try the following steps if this happens:

*   Double-check your database name, username, and password
*   If you forgot any of that information, login to cPanel and click on MySQL Databases. On this page, you can see the names of your database and username as well as the ability to reset the password
*   Ask if your host uses localhost as the Database Host value.
*   If none of this works, try deleting the database and walk through the MySQL Database Wizard again.

#### White Screen of Death

Sometimes people get a White Screen of Death when they try installing WordPress. This error shows itself as a pure white screen when you go to visit your site and login. You can try searching for "WordPress White Screen of Death After Install" for a number of articles and support forum threads that address this topic. However, a common solution can be found by simply deleting the WordPress files, setting up a new database and starting the install process over again.  

## Exercises

The following exercises reinforce the skills needed to install WordPress: **Practice Using (S)FTP Software** This exercise helps you practice logging into your server and uploading and deleting files.

*   Use (S)FTP software to login to your server
*   Try creating a new folder called test and uploading files to this folder
*   Practice deleting the files and folders once you have finished uploading them

**Practice Setting Up Databases** This exercise helps you practice the creation and deletion of databases.

*   Practice setting up another database and user in cPanel
*   Then find the main MySQL Databases page in cPanel and try deleting the database and user

**Installing WordPress in a Different Folder** Sometimes you will have to install WordPress inside of a subfolder of your main public_html folder. This exercise helps you practice this process.

*   Create a new folder inside of your public_html folder named "test" or something similar
*   Try installing WordPress inside of this folder

**Deleting a WordPress Site**

*   Create a new folder inside of your public_html folder named "test" or something similar
*   Try installing WordPress inside of this folder.
*   When you're done, delete the site

## Additional Resources

*   [New To WordPress - Where to Start](https://codex.wordpress.org/New_To_WordPress_-_Where_to_Start)
*   [WordPress Installation Techniques](https://codex.wordpress.org/WordPress_Installation_Techniques)
*   [Famous 5-Minute Install](https://codex.wordpress.org/Installing_WordPress#Famous_5-Minute_Install)
*   [Installing WordPress](https://codex.wordpress.org/Installing_WordPress)
*   [Installing WordPress Locally on Your Mac With MAMP](https://codex.wordpress.org/Installing_WordPress_Locally_on_Your_Mac_With_MAMP)

## Quiz

**What do you need in order to install WordPress?**

1.  A hosting account
2.  A domain name
3.  (S)FTP Software
4.  All of the above

**Answer:** 4\. All of the above

* * *

**What do you use (S)FTP software for?**

1.  To setup a database
2.  To upload files to a server
3.  To run the installation script
4.  For editing posts and pages

**Answer:** 2\. To upload files to a server

* * *

**What information about your database do you need when installing WordPress?**

1.  Name
2.  Username
3.  Password
4.  All of the above

**Answer:** 4\. All of the above

* * *

**5\. Once you have uploaded the WordPress files and created a database, what do you do next?**

1.  Complete the install script
2.  Delete the files
3.  Login to your site
4.  Use (S)FTP to login to your server

**Answer:** 1\. Complete the install script

## Additional Resources

[WordPress Installation Techniques](https://codex.wordpress.org/WordPress_Installation_Techniques) @ Codex
