# Version 0.3.1

A bugfix release. Drop in compatible with 0.3.0.

* [fixed] Saving a record with a mounted Uploader no longer removes uploaded file
* [fixed] The file returned by S3 storage now has the path set to the full store path
* [added] File returned by S3 storage now responds to S3 specific methods 

# Version 0.3

This is a stabilization release. Most features are now working as expected and
most bugs should be fixed.

* [changed] Reworked how storage engines work, some internal API changes
* [added] Macro-like methods for RMagick, no need to call #process any more!
* [added] Ability to super to any Mount method 
* [fixed] Sequel support should now work as expected
* [fixed] ActiveRecord no longer saves the record twice 

# Version 0.2.5

* [added] Added convenient macro style class methods to rmagick processing

# Version 0.2.4

* [added] `resize_to_limit` method for rmagick
* [added] Now deletes files from Amazon S3 when record is destroyed

# Version 0.2.2

* [changed] Mount now no longer returns nil if there is no stored file, it returns a blank uploader instead
* [added] Possibility to specify a default path
* [added] Paperclip compatibility module

# Version 0.2.1

* [changed] Url method now optionally takes versions as parameters (like Paperclip)
* [added] A field which allows files to be removed with a checkbox in mount
* [added] Mount_on option for Mount, to be able to override the serialization column
* [added] Added demeter friendly column_url method to Mount
* [added] Option to not copy files to cache dir, to prevent writes on read only fs systems (this is a workaround and needs a better solution)


# Version 0.2

* [changed] The version is no longer stored in the store dir. This will break the paths for files uploaded with 0.1
* [changed] CarrierWave::Uploader is now a module, not a class, so you need to include it, not inherit from it.
* [added] Integiry checking in uploaders via a white list of extensions
* [added] Validations for integrity and processing in ActiveRecord, activated by default
* [added] Support for nested versions
* [added] Permissions option to set the permissions of the uploaded files
* [added] Support for Sequel
* [added] CarrierWave::Uploader#read to read the contents of the uploaded files

# Version 0.1

This is a very experimental release that has not been well tested. All of the major features are in place though. Please note that there currently is a bug with load paths in Merb, which means you need to manually require uploaders.