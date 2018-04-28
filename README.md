# ReviewQA: a relational aspect-based opinion reading dataset

ReciewQA is relational aspect-based opinion reading dataset released by [NAVER LABS Europe](http://www.europe.naverlabs.com/).

It contains more than 500.000 natural language questions over 100.000 documents.

This dataset has been designed to evaluate machine reading models over a set of challenging relational tasks.

## Summary of the tasks

| TaskID | Description                                                                          | Examples                                                                |
| ------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------|
| 1       | Detection of an aspect in a review.                                                  | Is sleep quality mentioned in this review ?                             |
| 2       | Prediction of the customer general satisfaction.                                     | Is the client satisfy by this hotel ?                                   |
| 3       | Prediction of the global trend of an aspect in a given review.                       | Is the client satisfy with the cleanliness of the hotel ?               |
| 4       | Prediction of whether the rating of a given aspect is above or under a given value.  | Is the rating of location under 4 ?                                     |
| 5       | Prediction of the exact rating of an aspect in a review.                             | What is the rating of the aspect Value in this review ?                 |
| 6       | Prediction of the list of all the positive/negative aspects mentioned in the review. | Can you give me a list of all the positive aspects in this review ?     |
| 7.0     | Comparison between aspects.                                                          | Is the sleep quality better than the service in this hotel ?            |
| 7.1     | Comparison between aspects.                                                          | Which one of these two aspects, service, location has the best rating ? |
| 8       | Prediction of the strengths and weaknesses in a review.                              | What is the best aspect rated in this comment ?                         |



## Format of the data
```json
 "reviewID":"UR23105647",
 "qas":[
    {
       "answer":[
          "Rooms"
       ],
       "type":8,
       "trad":false,
       "question":"Which aspect gets the best rate in this review?"
    },
    {
       "answer":[
          "Location"
       ],
       "type":8,
       "trad":false,
       "question":"In this review, what is the worst aspect rated?"
    }
 ] 
```

**reviewID:** Each reviewID corresponds to a unique identifier that will allow you to retrieve the comment from the original dataset 

**qas:** A list of questions/answers over this review.

**type:** The identifier of the tasks associated to this question.

**trad:** False if this is one of the crowdsourced questions and True if this question comes from a backtranslated rephrasing.

## How to reconstruct the dataset
For each document of the dataset, we display a **reviewID** that corresponds to a unique ID in the original data.

You need to retrieve this review from the original dataset [available here](http://times.cs.uiuc.edu/~wang296/Data/LARA/TripAdvisor/TripAdvisorJson.tar.bz2) and then to replace this reviewID by the text you will find in the field *Content* of the original data.

## References

Hongning Wang, Yue Lu and ChengXiang Zhai. [*Latent aspect rating analysis without aspect keyword supervision.*](http://times.cs.uiuc.edu/~wang296/paper/p618.pdf) The 17th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD'2011), P618-626, 2011. 

Hongning Wang, Yue Lu and Chengxiang Zhai. [*Latent aspect rating analysis on review text data: a rating regression approach.*](https://dl.acm.org/citation.cfm?id=1835903) The 16th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD'2010), p783-792, 2010. 
