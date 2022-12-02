# Image Magick Command Line

magick mogrify -path thumbnails -format png -quality 95 -auto-orient -thumbnail 320x213 -background transparent -gravity center -extent 320x213 '*.jpg'
