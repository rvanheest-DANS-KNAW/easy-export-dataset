easy-export-dataset
===================

Export an EASY dataset to a Staged Digital Object set.


SYNOPSIS
--------

    easy-export-dataset <dataset-pid> <staged-digital-object-set>
    
 
DESCRIPTION
-----------

Exports an EASY dataset to a [Staged Digital Object set]. All the digital objects belonging to the dataset are 
exported, including: the dataset, all file and folder items, download history and jump-off pages. If `dataset-pid`
is not present in the Fedora repository or `stage-digital-object-set` cannot be created (e.g., it already exists)
the program terminates with an error.

All datastreams except `RELS-EXT` are exported to external files referenced from a `cfg.json` ([Digital Object Configuration]) 
file. `RELS-EXT` is exported to the "relations"-map in this file. Fedora PIDs that reference digital objects in the
same dataset are replaced by the appropriate SDO-name. 

ARGUMENTS
---------

<!-- Paste here from command line -->




INSTALLATION AND CONFIGURATION
------------------------------

### Installation steps:

1. Unzip the tarball to a directory of your choice, e.g. /opt/
2. A new directory called easy-export-dataset-<version> will be created (referred to as `$APPHOME` in the following)
3. Create a symbolic link to `$APPHOME/bin/easy-export-dataset` at `/usr/bin/easy-export-dataset` (or at some other
   location that is on the `PATH`. 

 
### Configuration:

Configuration settings must be specified in `$APPHOME/cfg/application.properties`. These include the connection 
settings for Fedora and for the File-system RDB.


BUILDING FROM SOURCE
--------------------

Prerequisites:

* Java 8 or higher
* Maven 3.3.3 or higher
 
Steps:

        git clone https://github.com/DANS-KNAW/easy-export-dataset.git
        cd easy-export-dataset
        mvn install
  
[Staged Digital Object set]: https://github.com/DANS-KNAW/easy-ingest#staged-digital-object-set
[Digital Object Configuration]: https://github.com/DANS-KNAW/easy-ingest#digital-object-configuration-file
[EASY Metadata]: https://easy.dans.knaw.nl/schemas/md/emd/2013/11/emd.xsd
[DCTERMS format]: http://dublincore.org/documents/dcmi-terms/#terms-format
[MIME Type]: https://en.wikipedia.org/wiki/MIME
