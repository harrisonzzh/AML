## Large-Scale Image Search Engine

Our image search engine will search for relevant images given a natural language query. For instance, if a user types "dog jumping to catch frisbee," our system will rank-order the most relevant images from a large database.

### Data

During training, we have a dataset of 10,000 samples. Each sample has the following data available for learning:
* A 224x224 JPG image.
* A list of tags indicating objects appeared in the image.
* Feature vectors extracted using ResNet, a state-of-the-art Deep-learned CNN . The features are extracted from pool5 and fc1000 layer.
* A five-sentence description.

During testing, our system matches a single five-sentence description against a pool of 2,000 candidate samples from the test set. Each sample has:
* A 224x224 JPEG image.
* A list of tags for that image.
* ResNet feature vectors for that image.

### Model Flow Chart
Here is a overview of our model. For more detail, please check our 
[paper](https://github.com/harrisonzzh/CS-5785-Applied-Machine-Learning/blob/master/final%20project/Image%20search%20paper.pdf)



<img src="Reference/flow_chart.jpeg" width="800px" />




### Searching Examples
Here are two example of our searching result. Given a five sentences description, our model will return the most relevant images. 
### 
<img src="Reference/example1.png" width="700px"  />
<img src="Reference/example2.png" width="700px"  />





### Evaluation Metric
There are 2,000 descriptions, and for each description, we need to compare against the entire 2,000-image test set. That is, rank-order test images for each test description. We will use MAP@20 as the evaluation metric. If the corresponding image of a description is among our algorithm's 20 highest scoring images, this metric gives us a certain score based on the ranking of the corresponding image. Please refer to the evaluation page for more details. 


