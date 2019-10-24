# A Study of Urban Perception and Geometric Factor
College of Architecture and Urban Planning, Tongji University, blairdahuang@outlook.com
# ABSTRACT 
A series of recent paper (Fan Zhang et al 2018, Abhimanyu Dubey et al 2016,  Sean M. Arietta et al 2014) have presented state-of-the-art computer vision models to validate urban visual appearance, which allows the urban quantitative analysis to look beyond not only geometry feature but also the urban perception dimension. 

Taking the Anshan New Village as the research object, this paper begins using segment analysis to find out the choice and integration of network. To find out how streets with different choice and integration differ in visual appearance, I trained an image classification model based on convolutional neural network, which would measure the impression of the object area. 

Moreover, after matching the vitality score with space syntax indicator, a correlation analysis to identify the relationship of perception and geometric factors indicates that there are no strong correlation among them. Then, I used Gaussian Mixture Model to classify clusters of streets to extract features, which gives new classification method of streets. The research results can be further used to instruct street renewal based on the design concept.

#### Check the *Zhuoya Huang-percep_geo-123* for final work. 
# CNN Vitality Recognition 
###Perception Model using Keras
Using pictures from the vote-based MIT Place Pulse dataset, Baidu Static View and Bing ImageSearch, I classified them to binary category and built a convolutional model based on Keras deep learning library.

Although I used batch normalization, dropout and dense resize, the result still shows features of over-fitting. Since the training and validation dataset contains large number of pictures from nearby neighborhood and most of them are within Shanghai, it is believed that the model can still be generalized for Anshan community.
1009 photos of Anshan neighborhood crawlled from Baidu Static View are put into the trained model to predict the vitality score, which shows the human preception of streets in Anshan neighborhood. Pictures are not only along the streets but also with in the residential area. The vitality score distribution shows that the views along the residential streets have more vitality than views within the blocks. It aslo marks two most dynamic streets--Anshan street and Sujiatun street, and the least energetic streets go to the boundaries. Moreover, the most vigorous residential blocks are Tongji New villiage and Anshan 8th village. 
> Note: Due to the tight schedule of this work, my dataset is tagged by me so it is severely biased. If anyone interested in this dataset, please contact me *blairdahuang@outlook.com*.

# Segment Analysis
Put the road network in depthmap and we can get space syntax results.

Anshan Street shows great integration on radius 500m, which echos the fact that it is the most busy street in the district. While Sujiatun Street with light traffic appears to have the minimun value in the area. The boundaries of Anshan Community also gain high values on a global level, which are also the primary streets in Shanghai.

On 500m radius basis, streets with high choice are  residential-commercial street, which indicates great potential. On the contrary, the lower value streets are pedestrian walk with greening and squares. On a global level, the boundary is also clear.

# Correlation Analysis
Import the depthmap table to ArcGis and join the street vitality score to the closest path, I can have the values of integration, choice ,average vitality scores of streets in Anshan Neighborhood.
In the correlation analysis, the street vitality has no obvious relationship with integration and choice because of different rules of calculation. Integration and choice have Pearson R2=0.4856, which indicated moderate correlation.

Streets with commercial facade and beautiful landscape have the higher score of vitality, which are different from the principles of choice and integration. Sujiatun Street is not geometrically important but it has the most comfortable view and attracts great numbers of local residents even it’s a detour.

# Cluster Analysis

With scaled space syntax and vitality indicator, I use Gaussian Mixture Model to divide the street into four distinct clusters with following features：
+ **high choice(500): 
commercial facade, cycle traffic, colorful.
+ **high vitality: 
greenery, square, painting
+ **high integration:
highway, heavy vehicle traffic.
+ **low integration,low vitality: 
foot way, service way, boring facade.

In street renewal scenerio, once the design orientation is set, we can use this research result as design reference to adjust features and characteristics of the street.

# About Me
My name is Huang Zhuoya. I'm currently in my final year in Tongji University studying urban planning. I'm really interested in urban tech. Hopefully, I will learn computer science in the next two years.
