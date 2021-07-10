# job-expansion-challenge
Census &amp; Geopy Nominatim APIs


* Part One
  ### Part One - Preparing XML file
  * Libraries Used:
    ```import xml.etree.ElementTree as et 
    from lxml import objectify
    import codecs
    import pandas as pd
    import numpy as np
  * Step 1a: Use codecs module to pen notebook and save your xml file to text.xml 
  * Step 1b: Create a function to return a dataframe with extracted features from json dictionary
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
    
    df = df_xml1[['referencenumber', 'title', 'city', 'state', 'streetaddress', 'storeNumber', 'postalcode', 'country']][2:].reset_index(drop=True)
    
  * Step 1c: Begin with  ```np.char.array(df['streetaddress'].values)``` to create arrays for each geographic feature for pre-processin
  * Step 1d: Concatanate streetaddress, city, state, postalcode and country attributes into dataFrame column "location"
  
   ### Part Two - Adding Latitude & Longitude 
   * Libraries Used:
  ```from geopy.geocoders import Nominatim
  geolocator = Nominatim(user_agent= 'alison.sadel@gmail.com')
  from geopy.extra.rate_limiter import RateLimiter
  import pandas as pd
  import numpy as np

   ### Part Three - Adding Population Columns
   * Libraries Used:
   ```import requests
  import json
  from census import Census
  from us import states
  
 ### Part Four - Visualizations
   * Libraries Used:
     ```import folium
  from folium.plugins import FastMarkerCluster
  from folium.utilities import normalize
  import branca.colormap as cm
  import webbrowser
  
  
    

* Transform


* Visualizations


* Analysis
