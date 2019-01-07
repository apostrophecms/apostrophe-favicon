# Changelog

## 1.1.0

* Progress is now displayed via the new server-side support for `apos.notify` in Apostrophe. Note that Apostrophe must be at least version 2.73.0.

* Performance is drastically improved when the source image is large. We now start with the prescaled version of the image not less than 512 pixels in size on both axes, rather than wasting a great deal of time and RAM scaling a large original many times.

* All operations are now performed in a forked process. This prevents the favicon scaling computation, which is mostly synchronous code, from blocking the use of the Apostrophe site in the meantime.

Further performance improvement is possible by using external tools such as `imagemagick` for the image conversion work but this is already a major improvement.
