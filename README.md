**The Battle of Neighborhoods**

Finding the Best Place to Open a Business in Yogyakarta

Author: Rizky Pratama Nugroho

1. **Introduction**

Yogyakarta is a popular tourist destination in Indonesia, dubbed as a city of students and culture. There are more than 50 urban areas and 20 universities located in Inner Yogyakarta. Of course, choosing a location for business is one of the stressful and controversial tasks, since there is a lot of criteria that should be satisfied in order to achieve the highest revenue.

The target audience of this report is any one that is interested in opening a business but have no idea what kind of and in which area.

1. **Data**

In this project, three different datasets will be used to solve the problem: Urban Area, College Area, and Popular Venue. Urban data were obtained from the Indonesian Postal Code. A list of colleges is obtained by scraping website of Ministry of Education and Culture. After that Geocode each area using Open Street Map to obtain coordinates (latitude and longitude). Finally, Foursquare API was used to call the top 100 popular venues based on the coordinates of each area.

1. **Methodology**

1. **Data Set**

- Urban Area Dataset

The data set contain urban area in Yogyakarta was obtained from the Indonesia Postal Code data. The raw data consists of ID, Urban, Sub District, City, Province Code, and Postal Code.

![](RackMultipart20200426-4-1iwra8h_html_a1ac3beb9a32d7fb.png)

- College Area Data Set

The second dataset used was information on boroughs in London, scrapped from Ministry of Education and Culture website. Data contain NPSN (ID), Name of College, Address, Urban, Status, City, and Sub District.

![](RackMultipart20200426-4-1iwra8h_html_5b6c64fb29f40aac.png)

1. **Visualization**

The two datasets are merged to form a new dataset that combines the necessary information in one dataset. The coordinates of the area are be obtained using Open Street Maps geocoding to get the final dataset.

![](RackMultipart20200426-4-1iwra8h_html_676e3ff4eb58e97.png)

Below is the geo-visualization of the urban and college in Yogyakarta. Many College are located near the north-east of Inner Yogyakarta

![](RackMultipart20200426-4-1iwra8h_html_866f87e1cd1706f7.png)

1. **Foursquare API**

The new dataset is used to generate the 100 most popular venues for each area using the Foursquare APIThis returns a json file containing allthe venues in each place which is converted to a pandas dataframe. This dataframe contains all the popular venues along with their coordinates and category.

![](RackMultipart20200426-4-1iwra8h_html_a778249063dc6485.png)

1. **Modelling**

One hot encoding is done on the venues data. (One hot encoding is a process by whichcategorical variables are converted into a form that could be provided to ML algorithms todo a better job in prediction). The Venues data is then grouped by the area andthe mean of the venues are calculated, finally the 10 common venues are calculated foreach of the area.

![](RackMultipart20200426-4-1iwra8h_html_65a16813fb171a59.png)

To identify groups (clusters) with similar characteristics, the unsupervised learning method to our data, namely K-Means algorithm, was applied to our data.To identify the optimal number of clusters, the Elbow method is used. It can be seen from the graph that 7 clusters are the best choice.

![](RackMultipart20200426-4-1iwra8h_html_a8da7a6ae885669d.png)

1. **Result**

Based on the venue categories, K-Means clustering was conducted to group the urban and college into 7 different clusters based on their similarity.The color dots below represent differentclusters.

| **Cluster** | **Color** |
| --- | --- |
| 0 | Purple |
| 1 | Red |
| 2 | Blue |
| 3 | Light Blue |
| 4 | Green |
| 5 | Brown |
| 6 | Orange |

 ![](RackMultipart20200426-4-1iwra8h_html_400b63aec6b22abe.png)

From that visualization there are three main cluster (1, 2, and 3) and four secondary cluster (0, 4, 5, 6).

**Main Cluster**

Cluster 1: Lively Area (Restaurant, Convenience Store, Field, Farm,….)

![](RackMultipart20200426-4-1iwra8h_html_161f7ae2a29a3dd5.png)

Cluster 2: Busy Area (Fast Food, Café, Store, Boutique, …)

![](RackMultipart20200426-4-1iwra8h_html_d85dc09ee87202a5.png)

![](RackMultipart20200426-4-1iwra8h_html_75ef4565e47be020.png)

Cluster 3: Culinary Area (Asian Restaurant, Hotel, Coffe Shop, …..)

![](RackMultipart20200426-4-1iwra8h_html_386edb40b65f492b.png)

**Secondary Cluster**

Cluster 0: Village Area (Lake, Field, Farmer Market,….)

![](RackMultipart20200426-4-1iwra8h_html_28db3447f09adee2.png)

Cluster 4: Recreation Area

![](RackMultipart20200426-4-1iwra8h_html_7c8478f342f9250d.png)

Cluster 5: Tourist Area

![](RackMultipart20200426-4-1iwra8h_html_2df12197d63d9876.png)

Cluster 6: Quiet Area

![](RackMultipart20200426-4-1iwra8h_html_207c6bc9ac191139.png)

1. **Discussion**

The clustering results show that suitable business places are in clusters 1, 2, and 3. Most of the college area is included in cluster 2 (Busy Area) so that if a business is opened targeting students as consumers business such as café, department store or restaurant becomes good choice. If you want to open a restaurant business that makes tourists as main consumers, clusters 1 and 3 can be the best choice.

1. **Conclusion**

To conclude, the basic data analysis was performed to identify the most optimal area for opening busines in the Yogyakarta. During the analysis, several important statistical features of the urban and college are were explored and visualized. Furthermore, clustering helped to highlight the group of optimal areas.Finally, cluster 1, 2, and 3 were chosen as the most attractive options for the further analysis.
