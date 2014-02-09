drumbs
===========

On demand image manipulation for PHP 5.3+

This tool generates images on the fly by request.
The image is always sent over the HTTP server for better performance.

## How it works

Considering you have an image located in /demo/images/demo.jpg, you can
generate various versions on the fly by adding another segment before the filename.

This segment is the task name that will be used, and the parameters are separated
by underscores.

Tasks names must have a prefix, as defined in the .htaccess demo and the config file.

When the file does not exist, the .htaccess automatically binds the request to *drumbs*,
where the new image will be generated if the task name is valid (and allowed) and the original
file exists in the parent folder.

When it's done *drumbs* will refresh the request so Apache can handle and send the new image.
If there's some errors or the request is not valid, a 404 error with an empty body is sent.

Check the config.sample.php file and navigate to the demo/index.html page to see the possibilities.

Drumbs comes with many predefined actions, but you can create your own.

Of course, the 'demo/images' folder is only for demonstration purposes, you can use drumbs with any folders.