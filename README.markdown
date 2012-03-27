# Jason's Super Awesome Shell Scripts! Of Fun!

I don't know if I'll ever write another one, but here's a repo where I'll store them if I ever do.

## newvhost

This script sets up a new virtual host for Apache, on Mac OS X. I built it using 10.7.2 and I have no idea if it works on anything else. You call it like this:

`$ sudo newvhost local.mysite.com`

This will perform the following actions: 

1. Make a directory at ~/vhosts if one doesn't exist
1. Create the `<VirtualHost>` block in the /etc/apache2/extra/httpd-vhosts.conf file*
1. Adds a listing to /etc/hosts for this domain
1. Creates the directory inside of ~/vhosts for you to store the web files, if it doesn't already exist. Remember, this directory will be named the URL you passed (ie ~/vhosts/local.mysite.com)
1. Creates an index.html file inside of the new webroot, which announces what site it is for your verification
1. If you use Panic Coda or Textmate and have CLI installed**, it will open the new project in your editor.
1. Restarts Apache
1. Opens the new index.html file in your browser. If you have Google Chrome, it defaults there. Deal with it.

> \* Note: If your Apache config doesn't already include the httpd-vhosts.conf file, you'll need to open up /etc/apache2/httpd.conf and uncomment the line that includes it.
>
> ** If you use homebrew, it's just `$brew update` and then `$ brew install coda-cli` -- details here: http://justinhileman.info/coda-cli/

### To install `newvhost`:

1. Download the script wherever you want, or clone this git repo into something like ~/shell_scripts or what have you
1. Symlink the script into /usr/local/bin or some other directory in your $PATH  
    > * Check what's in the $PATH by running `$ echo $PATH`  
    > * Symlink like this: `$ ln -s [source] [target]`, ie `$ ln -s ~/shell/newvhost /usr/local/bin`
1. Make the script executable, 0700 works. `$ chmod 0700 ~/shell/newvhost`
1. Go nuts.

Fork at will.

