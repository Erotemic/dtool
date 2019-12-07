# TODO:

* Allow for algorithm tables to store one-vs-one results efficiently.
    - allow for daids to be independent 
    - allow for qaids to be non-independent
    - allow for ordering to matter / not matter
    - Need to update:
        - depc.new_algo_request
        - AlgoRequest.execute
    - Careful, the descendant rowids of annot for vs one are [(1, 1), (2, 2), ...]
      this is because there is no way to say what daids you want to compare against

* ~~Allow for custom external write functions to be specified.~~

* Move all version flags to config objects.
    - involves allowing differnt configs to have the same value
    - requires config namespaces

* Allow annotation of implicit edges.


* Need to remove algorithm request structure completely from the dependency
  cache. Algorithms should be specified strictuly with configs and the 
  configs should know how to address the storage of long configuration 
  options like the daid list for vsmany.


* root\_uuids should be specified as the base\_root\_uuid plus a hash of the
  attributes that matter for the requested computation.

* Need to standardize and keep track of places where we use row-wise or
  column-wise indicies.


* Need to add support for precomputed models

* REQUIRED: get config property of child computation
* REQUIRED: different configs for items in n-wise edges
* REQUIRED: handle gets of any table that has an ancestors with a multi-edge

* FIXME: duplicate rowids

REQUIRED: Request objects should be able to handle nodes at any depth


* Add rootmost-input rowids to data tables for quick access.

* Override ancestor default configuration value when defining a table.
- Force parameter to be static.


* Make lazy computable columns that can be manually overwritten.
Motivating example:
we want to access image orientation from the image EXIF data.
We don't want to read it all when images are added.
Solution, make image orientation a depcache property of images.
Then allow for that property to be manually overwritten.
Challenges involve how do you deal with precedence and whatnot.
Maybe you don't.
Maybe you have a manual property that defaults to a computed property.
Then you either request the manual or the computed version.

* delete_property should be able to work for ALL configs, not just 
  a the default config 
