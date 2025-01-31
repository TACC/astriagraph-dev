# dev-test

This stands up a neo4j on localhost using docker and imports astria db dump. 

It create self-signed certs during startup.

It puts the database and data in dir you define. 

# Setup 

1) Set up ~/neo4j-userpass & ~/neo4j-auth , e.g.

    # cat ~/neo4j-userpass
    NEO4J_USERNAME=neo4j
    NEO4J_PASSWORD=changeme

    # cat ~/neo4j-auth
    NEO4J_AUTH=neo4j/changeme

**NOTE** You cannot put these in the same file. If you put NEO4J_USERNAME & NEO4J_PASSWORD in the docker env it will mess up the config and not start neo4j. 


2) Download a data dump file from from here: https://astria.tapis.io/#/files/astria.archive.jstubbs

Make sure to run md5sum on the dump file and make sure it matches what's in the associated README.

3) Scripts assume your data volume for Neo4j lives in /data/neo4j. Ensure that dir is there and has sufficient space (100GB recommended).




# Operations

Then run burnup (set up neo4j):

    ./burnup
    ...

Check that it's up:
    
    ./info

Count rows in database:

    ./count

Shut server down:

    ./burndown
