# FFmpeg/FFprobe Lambda Layer for Amazon Linux 2 AMIs

Static build of FFmpeg/FFprobe for Amazon Linux 2, packaged as a Lambda layer. Bundles FFmpeg 6.0.

This application provides a single output, `LayerVersion`, which points to a
Lambda Layer ARN you can use with Lambda runtimes based on Amazon Linux 2 (such
as the `nodejs10.x` runtime).

For an example of how to use the layer, check out 
<https://github.com/OpenReel/ffmpeg-aws-lambda-layer/tree/master/example>
