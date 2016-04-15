# FlyBase GFF 3 validation

## Overview

This image builds a container that is used to validate GFF v3 files.

It currently contains two GFF validators

 * Genome Tools (http://genometools.org/)
 * GAL (http://www.sequenceontology.org/software/GAL.html)

## Installing

This command will fetch the current image, create a container named gff-validator,
mount the /local/path/to/your/gff/files on your machine to /data in the container,
and execute an interactive bash shell.

     > docker run -i -t -v /local/path/to/your/gff/files:/data --name gff-validator flybase/gff-validator /bin/bash

## Using

This will run the Genome Tools GFF validator on whichever file you specify.

    # gt gff3validator /data/path/to/your/file.gff > validation.log 2>&1 


