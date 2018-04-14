# Scale down folder inplace

    mogrify -path <fullpath> -scale <percentage> -quality <quality> -format<format> *.<extension>

`<format>` e.g. jpg, png

`<quality>` must be chosen depending on the scene complexity of the images

# Rotate images by EXIF info

    mogrify -auto-orient *

# Generate thumbnails from image

    convert <name> -thumbnail 16384@ -gravity center -background <color> -extent <size> <new_name>

`<color>` e.g. white, black

`extent <size>` is the total size which can be padded out with the background color

The `thumbnail` option takes the total amount of pixels for the image and applies the resize operator `@` to the specified target. With this technique, the original image will be as big as possible while not cutting away too much. 
