# job-expansion-challenge
Census &amp; Geopy Nominatim APIs


* Part One
  * Libraries Used:
    ```import xml.etree.ElementTree as et 
    from lxml import objectify
    import pandas as pd
    import numpy as np
    import codecs
  * Step 1: Use codecs module to pen notebook and save your xml file to text.xml 
  * Step 2: Create a function to return a dataframe with extracted features from json dictionary
  * Step 3: Begin with  ```np.char.array(df['streetaddress'].values)``` to create arrays for each geographic feature for pre-processing
  
  ```## For Loop to extract all features from json dictionary
  def xml2df(xml_data):
    root = ET.XML(xml_data)
    all_records = []
    for i, child in enumerate(root):
        record = {}
        for sub_child in child:
            record[sub_child.tag] = sub_child.text
        all_records.append(record)
    return pd.DataFrame(all_records)

 * Step 4: Concatanate streetaddress, city, state, postalcode and country attributes into dataFrame column "location" 
  
  
    

* Transform


* Visualizations


* Analysis
