# Islandora Video Filter

Provides a simple method for inserting video and audio stored in Islandora into Drupal nodes.

## Requirements

* Users need to download and enable the Drupal [Video Filter module](https://www.drupal.org/project/video_filter).  Review the [module's documentation](https://www.drupal.org/node/402796) for installation instructions.
* The module assumes that you have the [Islandora Video.js module](http://github.com/islandora/islandora_videojs) enabled.

## Installation

Enable the Video Filter module and the Islandora Video Filter module.  

## Configuration
You will also need to properly configure the text format(s) (admin/config/content/formats). See the Video Filters [README](http://drupalcode.org/project/video_filter.git/blob/refs/heads/7.x-3.x:/README.txt) for further instructions.

## Usage 

### Video 

To embed an Islandora video object:

 [video:url]

For an Islandora video object your url will need to follow this pattern:

 [video:http://sandbox.islandora.ca/islandora/object/islandora:121/datastream/MP4/view]

* Note the PID and ensure it has the format namespace:identifier
    * islandora%3A121 needs to be changed to islandora:121 
    * To get the URL of a video object, Manage > Datastreams > MP4 (right click and copy link)

This will output the video using the default settings and display it in the Video.js viewer.

With parameters:

[video:url width:X height:Y autoplay:1/0]

[video:http://sandbox.islandora.ca/islandora/object/islandora:121/datastream/MP4/view width:320 autoplay:1]

This will override the default settings for this video.

### Audio 

To embed an Islandora audio object follow the same pattern as described for Islandora video objects, but reference the MP3_PROXY datastream instead.

 [video:url]

 [video:http://sandbox.islandora.ca/islandora/object/islandora:69/datastream/PROXY_MP3/view]

This will output the audio using the default settings and display it in the default HTML5 audio player.

## Customization

The parent module, [Video Filter](https://www.drupal.org/project/video_filter), provides a plugin architecture.

## Troubleshooting

* If videos don't show up, try disabling any browser plugins, such as AdBlock.
* If you are having **issues in a dev env. using localhost** you may want to try 127.0.0.1. The Video Filter module looks for a . in the host name.

## Maintainer

* Robertson Library
* Paul Pound

## Sponsors

Development sponsored by the [Diversity Cape Breton](http://diversitycapebreton.ca) project.