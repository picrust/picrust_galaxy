PICRUSt within Galaxy
=====================

This repository provides the configuration files allowing [PICRUSt](http://picrust.github.com/) to be used within [Galaxy](http://galaxyproject.org/).

These files are **not** needed to run PICRUSt from the command line. 

Install
=======

This describes the steps of getting PICRUSt installed in Galaxy. 

1. Install [Galaxy](http://galaxyproject.org/).

2. Install [PICRUSt](http://picrust.github.com/). **(Including the download of ALL precalculated PICRUSt files from this page: http://picrust.github.io/picrust/picrust_precalculated_files.html )**

3. From within your **galaxy-dist/tools** directory, download the picrust_galaxy files:
     
          git clone git://github.com/picrust/picrust_galaxy.git picrust_galaxy

4. Copy or link to the following installed PICRUSt scripts (typically found in /usr/bin/local) to **galaxy-dist/tools/picrust_galaxy** directory.

* **normalize_by_copy_number.py** 
* **predict_metagenomes.py**
* **categorize_by_function.py**

5. Add the following to the file **galaxy-dist/tool_conf.xml**:

          <section name="PICRUSt" id="PICRUSt">
               <tool file="picrust_galaxy/normalize.xml"/>
               <tool file="picrust_galaxy/predict.xml"/>
               <tool file="picrust_galaxy/categorize.xml"/>
          </section>

7. Add the following to the file **galaxy-dist/datatypes_conf.xml**:

          <datatype extension="picrust" type="galaxy.datatypes.binary:Binary" subclass="true" display_in_upload="true"/>
          <datatype extension="picrustn" type="galaxy.datatypes.data:Text" subclass="true" display_in_upload="true"/>
          <datatype extension="picrustp" type="galaxy.datatypes.data:Text" subclass="true" display_in_upload="true"/>
          <datatype extension="picrustc" type="galaxy.datatypes.data:Text" subclass="true" display_in_upload="true"/>

8. Restart galaxy

