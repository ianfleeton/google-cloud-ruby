# Release History

### 1.14.0 / 2018-09-10

* Add Object Lifecycle Management:
  * Add Bucket#lifecycle.
  * Add Bucket::Lifecycle and Bucket::Lifecycle::Rule.
* Update documentation.

### 1.13.1 / 2018-08-21

* Update documentation.

### 1.13.0 / 2018-06-22

* Update Policy, protect from role duplication.
* Updated dependencies.

### 1.12.0 / 2018-05-09

* Support Cloud KMS keys / Customer-managed encryption keys (CMEK).

### 1.11.0 / 2018-05-01

* Support partial Storage::File downloads. (georgeclaghorn)
* Add File#rewrite.
  * Similar to File#copy, except for being able to specify both source and destination encryption keys.
  * Refactor both File#copy and File#rotate to call File#rewrite.
* Update documentation for File-like IO parameters. The underlying libraries call #size on the argument, which is not present on IO, but is present on File and StringIO.

### 1.10.0 / 2018-02-27

* Support Shared Configuration.
* Fix verification for gzipped files.
  * Add skip_decompress to File#download
  * Update documentation and examples for gzip-encoded files.
* Fix issue with IAM Policy not refreshing properly.
* Update Google API Client dependency.
* Update authentication documentation

### 1.9.0 / 2017-11-20

* Add `Google::Cloud::Storage.anonymous` to support public data access.

### 1.8.0 / 2017-11-14

* Add `Google::Cloud::Storage::Credentials` class.
* Rename constructor arguments to `project_id` and `credentials`.
  (The previous arguments `project` and `keyfile` are still supported.)
* Document `Google::Auth::Credentials` as `credentials` value.
* Updated `google-api-client`, `googleauth` dependencies.

### 1.7.1 / 2017-10-24

* Fix bug in Bucket#create_file, Bucket#compose, File#copy and File#rotate in
  which user_project was not set on returned File object.
* Fix bug in Bucket::Acl#add_reader and Bucket::Acl#add_owner in which
  user_project was not passed in the API request.

### 1.7.0 / 2017-10-18

* Add `Bucket#compose`.
* Update documentation.

### 1.6.0 / 2017-09-28

* Add `user_project` option to `Project#buckets` and `Project#create_bucket`.
* Upgrade to Google API Client 0.14.2.
* Update documentation.

### 1.5.0 / 2017-09-26

* Add Pub/Sub notification subscriptions.
* Update `#signed_url` to support symbols (dimroc).

### 1.4.0 / 2017-08-02

* Add `skip_lookup` option for retrieving `Bucket` and `File` objects
  without accessing the Storage API
  * Add `Bucket#exists?` method
  * Add `File#exists?` method
* Add `File#generations` method
  * Add `generation` argument to `File#delete`
  * Add `generation` argument to `File#reload!`
* Add `Bucket#storage_class=` method
* Fix for when the `user_project` value set on a `Bucket` was not being
  properly set on all `File` objects returned by `Bucket`.
* Fix to use `user_project` value when reloading a `Bucket`.

### 1.3.0 / 2017-07-11

* Add `query` parameter to `#signed_url` methods (georgeclaghorn).

### 1.2.0 / 2017-06-27

* Add Requester Pays support.
* Upgrade dependency on Google API Client.

### 1.1.0 / 2017-06-01

* Add Bucket#labels.
* Update gem spec homepage links.
* Remove memoization of Policy.
* Deprecate force parameter in Bucket#policy. (Will be removed in a future version.)
* Deprecate Policy#deep_dup. (Will be removed in a future version.)


### 1.0.1 / 2017-04-10

* Add Bucket IAM support

### 1.0.0 / 2017-04-05

* Release 1.0
* Improvements to File copy for large files
* Allow file attributes to be changed during copy
* Upgrade dependency on Google API Client

### 0.25.0 / 2017-03-31

* Allow upload and download of in-memory IO objects
* Added signed_url at top-level object, without creating a bucket or file object
* Updated documentation

### 0.24.0 / 2017-03-03

* Dependency on Google API Client has been updated to 0.10.x.

### 0.23.2 / 2017-02-21

* Allow setting a File's storage_class on file creation
* Allow updating an existing File's storage_class
* Add File#rotate to rotate encryption keys
* Add PostObject and Bucket#post_object for uploading via HTML forms

### 0.23.1 / 2016-12-12

* Support Google extension headers on signed URLs (calavera)

### 0.23.0 / 2016-12-8

* Remove `encryption_key_sha256` method parameter, hash will be calculated using `encryption_key`
* Many documentation improvements

### 0.21.0 / 2016-10-20

* New service constructor Google::Cloud::Storage.new
* Bucket#signed_url added to create URLs without a File object

### 0.20.2 / 2016-09-30

* Fix issue with signed_url and file names with spaces (gsbucks)

### 0.20.1 / 2016-09-02

* Fix for timeout on uploads.

### 0.20.0 / 2016-08-26

This gem contains the Google Cloud Storage service implementation for the `google-cloud` gem. The `google-cloud` gem replaces the old `gcloud` gem. Legacy code can continue to use the `gcloud` gem.

* Namespace is now `Google::Cloud`
* The `google-cloud` gem is now an umbrella package for individual gems
