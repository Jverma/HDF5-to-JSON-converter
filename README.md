HDF5-to-JSON-converter
======================

Converting contents of a HDF5 file into a JSON file. 

This class contains methods to convert the contents of a [Hierachical Data Format file (HDF5)] (http://www.hdfgroup.org/HDF5/) into a JavaScript Object Notation (JSON) file. HDF5 files are not human readable and this class renders them in a human-readable data objects consisting of key–value pairs. 

The method HDF5toJSON.converter creates a JSON file of the same name as the input HDF5 file with json extension. When decoded the file contains a nested dictionary. 

Every object in an HDF5 file has a name, and the are arranged in a POSIX – style hierarchy with / separators.
e.g. 

	/group1/group2/dataArray


The JSON file the objects are accesed as -- 

	json_file = open('createdJSONfile.json')	
	for line in json_file:	
		record = json.loads(line)
		print record['/']['group1']['group2']['dataArray']

There are also methods to access the contents of a group directly without following the hierarchy. e.g. if you want to check the contents hanging from group2, use method groupContents. 

Check out my <a href="http://januverma.wordpress.com/2014/07/08/hdf5-to-json-converter-in-python/">blog</a> for a discussion on this class. 

