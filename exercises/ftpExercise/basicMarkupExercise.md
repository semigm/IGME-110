# Web Publishing Exercise

## Overview & Goals

In today's exercise, you'll upload your personal web page from the Homework onto the web.

## Setting Up Your Folders and Files

On your computer (or on a USB drive) create a folder called `RIT Web`. Inside that folder, create a folder called `www`. Inside of the `www` folder, create a folder called `igme110`. And inside of the `igme110` folder, create a folder called `media`. Remember that case matters on the web so `Media` is not the same as `media`.

![Example File Structure](110homepage-folderstructure.png)

 The www folder represents your www directory on 'banjo.rit.edu'. Place your `index.html` and image files inside of the `igme110` folder.

 Open your `igme110` folder with File Explorer. Then right click on `index.html` and open it in any web browser `Open with -> Google Chrome`. It should look something like this:

![Screenshot of index.html page](110homepage-1.png)

## Relative References to Other Directories

As your web site gets bigger, keeping all your files in the same directory makes it harder to keep them organized. Web developers typically have different directories for different parts of their site, and also often keep images in a separate directory. You created a `media` folder in your `igme110` directory, and that’s where we’re going to put the images you use on your site.

On your computer, open the `igme110` folder you created. Move your image file into the `media` folder. Your structure should look like this:

![index.html with image added](110homepage-filestructure.png)

Now try reloading your page in the browser again.  If you followed the directions properly, the image won’t load now. The browser is still looking for it in the same directory as the HTML file, but it’s not there. We need to tell the browser how to find the image, using a relative path.

In your html file, change the img tag so that it looks like this (using your image information, of course):
   `<img src="media/dog.jpg" alt="Morgan the dog" />`

This tells the browser to look in the media folder that’s inside the igme110 folder. Reload the page in the browser to see if it worked. The image should show up again. (If not, ask for help!)

## Uploading

Now we’ll use FTP (actually SFTP, which uses a secure connection to the server) to put your web pages onto the banjo server.

You can use whichever SFTP (secure File Transfer Program) you'd like to uplaod files to the server. In the IGM labs, we have FileZilla installed, so that's what's used in this documentation. (You can download FileZilla for your own computer at <https://filezilla-project.org/download.php?show_all=1> -- if you're using Windows, I strongly suggest downloading the .zip file rather than the .exe file, since the executable file will try to install browser addons that can cause all kinds of problems.)

Launch FileZilla.  Fill in the fields at the top with the following information, and click “Quickconnect”:

-   Host: sftp://banjo.rit.edu
-   Username: your RIT username abc1234
-   Password: Your RIT user password
-   Post: 22

![FileZilla Connect Screen](filezilla-connect.png)

FileZilla may ask you if you want it to remember passwords—if you’re doing this in the lab, tell it no. If this is the first time you've used FileZilla on a lab computer, it may also give you a warning about an “unknown host key”—if that happens, check the box saying “Always trust this host” and then click OK. If you entered your user ID and password correctly, you should now see something like this:

![FileZilla File Listing Screen](filezilla-files.png)

The pane on the bottom left shows the files on your computer’s hard drive. In this case, it’s showing everything, including hidden files, that are on the main level of my computer’s hard drive. The pane on the right shows all the files, including hidden files, in your home directory on RIT’s web server.

In the pane on the left side (local site files), you’ll need to find the directory that you created at the beginning of this exercise. If you put it on a thumb drive, the drive should show up in the Volumes directory. If you put it on the Desktop, it should be in the student directory inside of the Users directory. You want to find your www folder and open it, so that you can see the igme110 and media folders in the left pane. (If you’re using Mac, there may also be a hidden file called .DS_Store, which you can ignore—it’s a Mac system file that is hidden.) If you have trouble finding your files, ask for help.

In the pane on the right side (server files), double click on the www directory. Once you’ve got the www directory on your local computer on the left side, and your www directory on banjo on the right side, you’re going to drag the igme110 directory from the www folder on the left (your computer) to the www folder on the right (the server). This will copy the folder and its contents to the web server. The file list on the right side should update to show the the new directories.

Now you need to test the files on the web server, to see if they’re accessible. Use a browser to go to `http://people.rit.edu/youruserid/igme110` (substituting your RIT ID for _youruserid_)

If the files and images show up, great! But it’s possible that they won’t, because the access to the files may not be set properly by default.

## Fixing Folder & File Access Permissions

In FileZilla, select the www folder in the right pane (on the server)
Right click on the folder in the right pane, choose “File Permissions” and make sure the permissions include read write and execute for the owner (that’s you), and read and execute for everyone else. The number in the box at the bottom should read “755” which is shorthand for those permissions. (You can either type the number into the box at the bottom, or check the boxes next to the permissions you want.) Make sure the box that reads "recurse into subdirectories" is selected, and choose "Apply to directories only." Click OK. This should change the permissions for the www directory, and all directories below of it, including the igme110 directory and the test directory.

Once you’ve changed the permissions on the folders, you need to repeat that process to change the permissions for the individual files. They don't need execute permissions, so the shortcut for their permissions is 644 rather than 755.

![Folder Permissions](folderpermissions.png)  ![File Permissions](filepermissions.png)

Once you've changed the folder and file permissions for www and everything inside of it, go back to the browser and try loading `http://people.rit.edu/{youruserid}/igme110` again. If it still won't load, ask for help!

Notice that the URL I gave you only has the directory name (igme110) and not a file name. That is because banjo, like most web servers, automatically looks for a file called index.html in a folder if no other file was specified. If you were to include the file name in the URL (e.g. `http://people.rit.edu/{youruserid}/igme110/index.html`), it would also recognize that file and load it. But if you end the URL with the directory name and don’t specify a file, the server will automatically load the index.html file if there is one in that directory.

Once your page has displayed properly, view the source in the web browser (if you're using Chrome, type Ctrl-U to display the page source). You'll probably see a big block of completely unfamiliar code near the top of your page, where your first image is embedded. In the next section, I'll explain where that came from, and how we can make it go away.

## Due Date

You must have this exercise completed by midnight tonight. I will be checking the following url to make sure that your page loads properly: `http://people.rit.edu/{youruserid}/igme110`. Double check that it works or you will receive no credit.
