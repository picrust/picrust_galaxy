Installation instructions for PICRUSt  in a galaxy environment.

These instructions assume:
1.PICRUSt will be installed in the following directories: //usr/local/galaxy-dist  and //usr/local/galaxy-dist/tools
2. The name of the directory where the programs will be posted is:
//usr/local/galaxy-dist/tools/picrust_galaxy

Instructions:
=============

1. Please allocate an empty directory in  //usr/local/galaxy-dist/tools named "picrust_galaxy" (//usr/local/galaxy-dist/tools/picrust_galaxy)

2. Please allocate an empty directory called "picrust" under //usr/local/galaxy-dist/tools/picrust_galaxy
   (//usr/local/galaxy-dist/tools/picrust_galaxy/picrust)

3. Please allocate an empty directort called "data" under //usr/local/galaxy-dist/tools/picrust_galaxy/picrust
   (//usr/local/galaxy-dist/tools/picrust_galaxy/picrust/data)

4. Update member tool_conf.xml  in the galaxy directory adding the following: 
  <section name="PICRUSt" id="PICRUSt">
     <tool file="picrust_galaxy/normalize.xml"/>
     <tool file="picrust_galaxy/predict.xml"/>
  </section>

5. Update member datatypes_conf.xml  in the galaxy directory adding the following THREE lines:
    <datatype extension="picrust" type="galaxy.datatypes.binary:Binary" subclass="true" display_in_upload="true"/>
    <datatype extension="picrustn" type="galaxy.datatypes.data:Text" subclass="true" display_in_upload="true"/>
    <datatype extension="picrustp" type="galaxy.datatypes.data:Text" subclass="true" display_in_upload="true"/>

6. Population if the xml programs:
   Please copy the following two members from git into //usr/local/galaxy-dist/tools/picrust_galaxy
	normalize.xml
	predict.xml

 7.Population of the python programs:
   Please copy the following 2 members from git into //usr/local/galaxy-dist/tools/picrust_galaxy
	normalize_by_copy_number.py 
 	predict_metagenomes.py
   <<<<Make sure they are authorized to execute>>>>

8. Please populate the subdirectory //usr/local/galaxy-dist/tools/picrust_galaxy/picrust with the following members from git:

	ace.py
	ancestral_state_reconstruction.py
	bayestraits.py
	count.py
	evaluate_test_datasets.py
	format.py
	format_tree_and_trait_table.py
	__init__.py
	make_cluster_jobs.py
	make_test_datasets.py
	metagenome_contributions.py
	parallel.py
	parse.py
	picrust
	predict_metagenomes.py
	predict_traits.py
	util.py

9. Please populate the data directory (//usr/local/galaxy-dist/tools/picrust_galaxy/picrust/data) with the following members from git:

	16S_precalculated.biom.gz  
	ko_precalculated.biom.gz

10. Recycle galaxy

