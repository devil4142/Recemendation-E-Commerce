# Recemendation-E-Commerce
Build intelligence to help customers discover products they may like and most likely purchase

# 1.	Abstract	
# 2.	Introduction	
# 3.	Architecture:	
# 4.	Implementation	
# 5.	Conclusion	

# 1.	Abstract
In our day-to-day life everyone of us happen to use the e-commerce websites to shop many items. This leads to an increasing diversity of consumers’ demand, turning into a challenge for a retail store to provide the right products accordingly to customer preferences. These e-commerce websites use different types of recommendation systems to provide a positive shopping experience to the user. Recommender systems are a tool to cope with this challenge, through product recommendation it is possible to fulfill customers’ needs and expectations, helping maintaining loyal customers while attracting new customers. In this project we have used the ratings given to a product by other users to make recommendations to the current user. We have created a matrix to represent the ratings given to the product by the different users. Next we have created the user profile and item profile and provide recommendations depending on the similarity to the other groups. Then we apply KNN algorithm which is a part of machine learning and Pearson’s Correlation Coefficient to make recommendations to the user. To evaluate the performance of the model , RMSE was used which gives information on the closeness of recommendations being generated.

 
 # 2.Introduction:

The history of recommendation system date back to early 90’s. Ever since then the recommendation systems have been evolving continuously. These recommendation systems have become the integral part of the web applications. This is mainly because the e-commerce websites have a large variety of product inventory’s available the data which is to be displayed to the user can be overwhelming. As a result the user may face difficulties to search for the product that they maybe looking for. At this point the recommendation system’s comes to usage. Harvard Business Review said that these recommendation algorithms are the key difference between “born digital” enterprises and legacy companies. This is mainly because the recommendation engine can provide personalized suggestion of products to the users depending on their browsing patterns and previous purchase history. As it provides these personalized recommendations users will be much interested to come back and do more purchases in the interactive environment provided by our system. With more number of visits from the user to our website, we can be able to collect more data about the user and the products, which in turn provides a chance to know the areas of improvements of the product. The better quality of product we have there is a much likely chance of acquiring more number of users. This is a whole continuous cyclic process which can be seen in the figure below[1].The recommendation system helps to increase the sales of items related to a particular product too. For example if a user buys a monitor from the website, our recommendation system will suggest him different types of keyboards and mouse. In this way it helps in increasing the

 
sales of certain items which the user by himself may not be searching. This recommendation 

system reduces the load on the database as they provide a personal recommendation to every

 individual users instead of displaying whole inventory. These recommendation systems usually 

are based on two different filtering techniques namely Collaborative filtering and Content based 

filtering. content based filtering is based on the content i.e. item-item relationship. In this method 

we form a relationship or cluster between group of items and display the relevant items to the 

customer when the customer searches for one item from the cluster. Collaborative filtering is based 

on the user behavior .Depending on the use behavior we do the further recommendations. In 

Collaborative filtering we form a cluster among different customers depending on their previous 

# 3.Architecture:
There are multiple steps involved in the architecture of the recommender system.

-- 1.1	Candidate Generation 
In candidate generation we generate a small subset of products for the use from the large size of products available. To get this small subset of products we consider the users previous activity as input.
1.2	Scoring


In the scoring part of the system, the model will give a rank to the candidates generated on the scale of 10. The candidates with the higher scores are recommended to the user.

-- 1.3	Re-ranking
Once the scoring process is done the system undergoes re-ranking to satisfy the additional constraints like ensuring diversity of products, freshness. To achieve this the system usually do not suggest the product which was disliked by the user and usually suggest the products that are newly available.


The pipeline of a recommendation system has the following five phases 

1).Pre-processing
2).Model Training

3).Hyper Parameter Optimization 4).Post Processing
5).Evaluation.

Pre-Processing

The key idea to perform the pre-processing is to generate a user-item matrix as shown in the figure 3

Normalization:

In the dataset there are users who are over reactive and provide high ratings or least ratings. We need to normalize the ratings from such users. For this we find the average rating of the product and average rating of the user and add them to the global average .
Formula for normalization is

User-item rating bias= global average + item’s average rating + user’s average rating.

Model Training:

After the pre-processing the next step is to train the model. In model building the common technique is to use matrix factorization We have used Single Value Decomposition (SVD) to do the decomposing of the original matrix and obtain the latent factor which helps in generating the recommendations .
Hyper Parameter Optimization:

An evaluation metric is to be chosen before the parameters are being tuned. In this we choose the value of K which indicates the number of recommendations to be generated as suggestion to the 
user. In our work conducted we have chosen the value of K as twenty five 5 so it recommends the top twenty five products to the user.
Post Processing:

As a part of post-processing we identify if there are any items that are previously purchased by the user and remove them from the generated recommendations. Thus in post-processing we ensure that there are no duplicates of the products.
Evaluation:

The performance of the model can be tested using one of the evaluation metric. In this project we have chosen Root Mean Square Error ( RMSE) as the evaluation metric. This paper makes use of python libraries like NumPy, pandas, matplotlib, and Seaborn, Scikit learn. These libraries are part of the system design as they work on the data set and provide the appropriate results.

# 4.	Implementation:
The system was built using Python as the programming language. Python was chosen because of it’s ease of use and lot of libraries are available inbuilt, which makes the implementation part convenient and less stressful. In the initial step we consider the dataset that we need for the recommender system. The dataset has four columns. The first column is User id which is unique for every user, Second column is the Product id which is unique for every product in the dataset, Third column has the rating for a product given by the respective user. Fourth column is timestamp which gives information about the time of the rating. After considering the dataset the next step is
 
to perform Exploratory Data Analysis(EDA) as it helps in providing the context that is needed for building a good model. EDA gives information which is used for identifying any errors in the dataset. We pre-process the dataset to check if there is accurate data in each field of all the four columns of the dataset and to avoid any null values. The results of the pre-processing of the dataset can be observed from the results .

# 5.Conclusion:
The primary goal of this project is to provide recommendations to the user in a e-commerce website by making use of machine learning algorithms. We have designed and implemented the system using collaborative filtering and Pearson correlation coefficient. The dataset considered has the ratings given by the other users to a specific product and depending on the similarity between the rated product we try to recommend the products to our current user. The future work of the project includes improving the efficiency of the system. And it should also be able to give appropriate recommendations to the users who don’t have any previous purchase history or to the new users. In future we can try to use recurrent neural networks and deep learning. With the help of deep learning techniques we can overcome some of the drawbacks of the matrix factorization technique. Deep learning uses recurrent neural networks to accommodate time in the recommender system which is not possible in the matrix factorization method. We can also work on providing sub-optimal recommendations to the user and record the reaction of the user and it can be used in the future by the system.

