# p7zip AWS Lambda Layer

This is an AWS Lambda layer containing the statically linked `7za` binary
utility from the [`p7zip`](https://sourceforge.net/projects/p7zip/) package.
p7zip is a Unix port of the [7-Zip](https://www.7-zip.org) file archiver. It
supports high compression ratio in the 7z format, as well as many other
compression and archive formats (e.g. zip, tar, gzip, bzip2). It also supports
strong AES-256 encryption in 7z and zip formats. 
You can use this layer in your Lambda function to compress/uncompress 7z/zip
archive files, e.g. using the
[`node-7z`](https://www.npmjs.com/package/node-7z) wrapper for Node.js.

## Status & Alternatives

As we are no longer using this Lambda layer in our own projects, this repo has been archived. (No pun intended.) To generate Zip archives using strong AES-256 encryption, you can use the [archiver package](https://www.npmjs.com/package/archiver) with the [archiver-zip-encrypted plugin](https://www.npmjs.com/package/archiver-zip-encrypted) instead.

## Use within Lambda

You can use the published layer using the following ARNs (based on region):

| Region           | ARN                                                        |
|------------------|------------------------------------------------------------|
| `ap-southeast-1` | `arn:aws:lambda:ap-southeast-1:469864174306:layer:p7zip:1` |

Alternatively, if you want to publish the layer yourself, edit the provided
Makefile to set the AWS region to publish to, then run `make publish`.

The 7za binary can be found in `/opt/bin/7za` inside your Lambda container.

## P7zip Version

This package includes p7zip 16.02, pulished on 2016-07-14. For more
information, check out https://sourceforge.net/projects/p7zip/files/p7zip/.

## Copyright and License

P7zip and 7-Zip are licensed under the GNU Lesser General Public License version
2.1 (LGPLv2.1).
