# FFmpeg/FFprobe for AWS Lambda

A Lambda layer containing a static version of FFmpeg/FFprobe utilities from the [`FFmpeg`](https://www.ffmpeg.org/) Linux package, compatible with Amazon Linux 2.x and Amazon Linux 1.x instances/

## Usage

The easiest way to use this is to pull it directly from the AWS Serverless Application repository into a CloudFormation/SAM application or deploy it directly from the Serverless Application Repository into your account and then link it as a layer. 

The `ffmpeg` and `ffprobe` binaries will be in `/opt/bin/` after linking the layer to a Lambda function.

For manual deployments and custom builds, read below...

## Prerequisites

* Unix Make environment
* AWS command line utilities (just for deployment)

## Deploying to AWS as a layer

This package includes FFmpeg 6.0, packaged by John Van Sickle. Please consider supporting him in maintaining statically built FFmpeg packages. For more information, check out <https://johnvansickle.com/ffmpeg/>

The output will be in the `result` dir.

Run the following command to deploy your AWS account's compiled result as a layer.

```
make deploy DEPLOYMENT_BUCKET=<YOUR BUCKET NAME>
```

### Configuring the deployment

By default, this uses `ffmpeg-lambda-layer` as the stack name. Provide a `STACK_NAME` variable when calling `make deploy` to use an alternative name.

### example usage

An example project is in the [example](example) directory. It sets up two buckets and listens to file uploads on the first bucket to convert and generate thumbnails from uploaded video files. You can deploy it from the root Makefile using the following:

```
make deploy-example DEPLOYMENT_BUCKET=<YOUR BUCKET NAME>
```

For more information on using FFmpeg and FFprobe, check out <https://ffmpeg.org/documentation.html>

## Credits

Gojko Adzic <https://gojko.net>

## License

* These scripts: [MIT](https://opensource.org/licenses/MIT)
* FFmpeg: GPLv2.1 <http://ffmpeg.org/legal.html>, John Van Sickle's static build GPL v3 <https://johnvansickle.com/ffmpeg/>

## LGPL version

*  [Giuseppe Battista](http://github.com/giusedroid) created a build that contains only LGPL components, for organisations that are concerned about GPL licensing. See it at <https://github.com/giusedroid/ffmpeg-aws-lambda-layer/tree/license/lgpl>
