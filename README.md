## Northwestern University Libraries Digital Collections Metadata

### Overview

This repository is a static metadata export of works from [Northwestern University Library's Digital Collections](https://dc.library.northwestern.edu) site. It exports metadata from the [Digital Collections API](https://api.dc.library.northwestern.edu) weekly. Use these collection-based datasets if you do not need the full-power of a dynamic search and IIIF-based responses. It is useful for individuals that want to perform analysis on the entire set of NUL's digitized works, import into other systems for retrieval, and other bulk analysis uses.

### Data Organization

Data is broken out by format (serialization) and collection. Metadata is contained within directories corresponding to the format `data/[format]` Files are named by slugged-collection-name-[collectionID].[format].gz. 

- `json` files are a straight export from the api
- `csv` files are a human readable version, favoring `labels` and using pipes to separate multi-value fields
- `xml` files are a conversion of json using the python `dict2xml` library

### Schedule of exports

Exports take place Sunday at midnight via a github action. The github action uses the nuldc cli to search for any collection that has an "indexed\_at" date later than the last update. You can check when the metadata was last updated by looking at the commit history. In the event that a fresh export is needed, a committer on this repository can remove the `upadated_at` file which will force a full re-export on the next run.   




