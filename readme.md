# Author
Gleb Sigalov<br>
Student at Queen Mary University of London<br>
glebsigalov@gmail.com


# Project
This is my Capstone Project - The Battle of Neighborhoods for Coursera.org

# Problem and Motivation
I want to analyse the various venues in Canary Wharf, London and see if there is a potential for opening a new restaurant. 
The audience that has the potential to be interested in this problem may be people who want to open a restaurant business in Canary Wharf.

# Data Sources
I plan to use the Foursquare API service (https://developer.foursquare.com/), 
specifically: data on categories, venues, locations; as well as ratings and likes.<br>
I will use 2 methods from this service:<br> 1) Get Details (https://developer.foursquare.com/docs/api/venues/details)<br>
2) Venues search (https://developer.foursquare.com/docs/api/venues/search)<br>
This is an example of the DataFrame that I will use in this project.

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>name</th>
      <th>categories</th>
      <th>referralId</th>
      <th>hasPerk</th>
      <th>location.address</th>
      <th>location.crossStreet</th>
      <th>location.lat</th>
      <th>location.lng</th>
      <th>location.labeledLatLngs</th>
      <th>location.distance</th>
      <th>location.postalCode</th>
      <th>location.cc</th>
      <th>location.city</th>
      <th>location.state</th>
      <th>location.country</th>
      <th>location.formattedAddress</th>
      <th>category</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>55412714498eba342dfd063f</td>
      <td>Sticks'n'Sushi</td>
      <td>[{'id': '4bf58dd8d48988d1d2941735', 'name': 'Sushi Restaurant', 'pluralName': 'Sushi Restaurants', 'shortName': 'Sushi', 'icon': {'prefix': 'https://ss3.4sqi.net/img/categories_v2/food/sushi_', 'suffix': '.png'}, 'primary': True}]</td>
      <td>v-1581275210</td>
      <td>False</td>
      <td>1 Crossrail Place</td>
      <td>Level -1</td>
      <td>51.506178</td>
      <td>-0.018287</td>
      <td>[{'label': 'display', 'lat': 51.506178, 'lng': -0.018287}]</td>
      <td>834</td>
      <td>E14 5AR</td>
      <td>GB</td>
      <td>London</td>
      <td>Greater London</td>
      <td>United Kingdom</td>
      <td>[1 Crossrail Place (Level -1), London, Greater London, E14 5AR, United Kingdom]</td>
      <td>Sushi Restaurant</td>
    </tr>
    <tr>
      <th>1</th>
      <td>54caa6f9498e6c4d94e01bcd</td>
      <td>Sticks'n'Sushi</td>
      <td>[{'id': '4bf58dd8d48988d1d2941735', 'name': 'Sushi Restaurant', 'pluralName': 'Sushi Restaurants', 'shortName': 'Sushi', 'icon': {'prefix': 'https://ss3.4sqi.net/img/categories_v2/food/sushi_', 'suffix': '.png'}, 'primary': True}]</td>
      <td>v-1581275210</td>
      <td>False</td>
      <td>1 Nelson Road</td>
      <td>NaN</td>
      <td>51.481200</td>
      <td>-0.008296</td>
      <td>[{'label': 'display', 'lat': 51.4812, 'lng': -0.008296}]</td>
      <td>2103</td>
      <td>SE10 9JB</td>
      <td>GB</td>
      <td>London</td>
      <td>Greater London</td>
      <td>United Kingdom</td>
      <td>[1 Nelson Road, London, Greater London, SE10 9JB, United Kingdom]</td>
      <td>Sushi Restaurant</td>
    </tr>
    <tr>
      <th>2</th>
      <td>58af108dabf632097b5e32bd</td>
      <td>Sushi Fresh</td>
      <td>[{'id': '4bf58dd8d48988d111941735', 'name': 'Japanese Restaurant', 'pluralName': 'Japanese Restaurants', 'shortName': 'Japanese', 'icon': {'prefix': 'https://ss3.4sqi.net/img/categories_v2/food/japanese_', 'suffix': '.png'}, 'primary': True}]</td>
      <td>v-1581275210</td>
      <td>False</td>
      <td>108 Salmon Lane</td>
      <td>NaN</td>
      <td>51.513944</td>
      <td>-0.033801</td>
      <td>[{'label': 'display', 'lat': 51.513943993735474, 'lng': -0.03380119800567627}]</td>
      <td>1957</td>
      <td>E14 7PQ</td>
      <td>GB</td>
      <td>London</td>
      <td>Greater London</td>
      <td>United Kingdom</td>
      <td>[108 Salmon Lane, London, Greater London, E14 7PQ, United Kingdom]</td>
      <td>Japanese Restaurant</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5131c941e4b09cc35d6698ba</td>
      <td>River Sushi</td>
      <td>[{'id': '4bf58dd8d48988d1d2941735', 'name': 'Sushi Restaurant', 'pluralName': 'Sushi Restaurants', 'shortName': 'Sushi', 'icon': {'prefix': 'https://ss3.4sqi.net/img/categories_v2/food/sushi_', 'suffix': '.png'}, 'primary': True}]</td>
      <td>v-1581275210</td>
      <td>False</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>51.506708</td>
      <td>-0.004449</td>
      <td>[{'label': 'display', 'lat': 51.506708, 'lng': -0.004449}]</td>
      <td>1377</td>
      <td>NaN</td>
      <td>GB</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>United Kingdom</td>
      <td>[United Kingdom]</td>
      <td>Sushi Restaurant</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5b6830542f97ec002cbad0c3</td>
      <td>Nuha Sushi</td>
      <td>[{'id': '4bf58dd8d48988d1d2941735', 'name': 'Sushi Restaurant', 'pluralName': 'Sushi Restaurants', 'shortName': 'Sushi', 'icon': {'prefix': 'https://ss3.4sqi.net/img/categories_v2/food/sushi_', 'suffix': '.png'}, 'primary': True}]</td>
      <td>v-1581275210</td>
      <td>False</td>
      <td>22 Kerbey street</td>
      <td>NaN</td>
      <td>51.512388</td>
      <td>-0.014623</td>
      <td>[{'label': 'display', 'lat': 51.51238826954448, 'lng': -0.014623403549194336}]</td>
      <td>1560</td>
      <td>E14 6AB</td>
      <td>GB</td>
      <td>London</td>
      <td>Greater London</td>
      <td>United Kingdom</td>
      <td>[22 Kerbey street, London, Greater London, E14 6AB, United Kingdom]</td>
      <td>Sushi Restaurant</td>
    </tr>
  </tbody>
</table>
