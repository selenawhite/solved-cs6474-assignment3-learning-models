Download Link: https://assignmentchef.com/product/solved-cs6474-assignment3-learning-models
<br>
The goal of this option of the assignment is to develop different supervised learning models to identify success or failure of altruistic requests on social media. The questions derive from social computing research that aims to understand linguistic markers of altruism as described on social media [1]. The questions in the assignment will test your understanding of theoretical notions of language and help seeking (narratives, moral foundations) and to what extent they can provide insights into the social construct of altruistic requests.

<strong>Part 1: </strong>Please refer to the enclosed zipped folder that contains dataset and associated information<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>. The dataset, named the file pizza_request_dataset.json, contains a collection of 5671 textual requests for pizza from the Reddit community “Random Acts of Pizza”2 (henceforth referred to as ROAP) together with their outcome

(successful/unsuccessful) and meta-data. All requests ask for the same altruistic request: a free pizza, and span the timeframe December 8, 2010 to September 29, 2013. The outcome of each request – whether its author received a pizza (successful) or not (unsuccessful) – is known. In the questions below, the ground truth data for all of the classification models will be this outcome, specifically in the file pizza_request_dataset.json, the field

requester_received_pizza. Please refer to Appendix I of this assignment document for an elaborate listing and description of all of the fields in the dataset file.

The features to be used in the classification models are described in the questions below. Please develop one classifier, specifically a Support Vector Machine model with a linear kernel and default parameters corresponding to each question below. For all of the classifiers, use a randomly sampled 10% of the dataset as test set (567 posts), and the remaining 90% as the training dataset (5104 posts) – the training and test sets need to be consistent across all classifiers below, i.e., the same 567 posts should be used for testing and the same 5104 for training for a), b), c) and d).  a) <em>Model 1 – n-grams (20 points)</em>: This model will extract the top 500 unigrams and top 500 bigrams<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a> as features to classify posts that would be successful or those that will be unsuccessful in their pizza requests. Here “top” means most frequently occurring unigrams and bigrams in the posts belonging to the training set. Using these <em>n</em>-gram features, train and test an SVM classifier as described above. Report a table containing the accuracy of your classifier, precision, recall, F1, specificity, and AUC.

<ol>

 <li>b) <em>Model 2 – Activity and Reputation </em>This model will utilize a variety of the activity and reputation data included in the dataset file (pizza_request_dataset.json) as features to distinguish between successful and unsuccessful requests. The specific activity features will use the values included in the following fields corresponding to each post: post_was_edited</li>

</ol>

requester_account_age_in_days_at_request requester_account_age_in_days_at_retrieval requester_days_since_first_post_on_raop_at_request requester_days_since_first_post_on_raop_at_retrieval requester_number_of_comments_at_request requester_number_of_comments_at_retrieval requester_number_of_comments_in_raop_at_request requester_number_of_comments_in_raop_at_retrieval requester_number_of_posts_at_request requester_number_of_posts_at_retrieval requester_number_of_posts_on_raop_at_request  requester_number_of_posts_on_raop_at_retrieval requester_number_of_subreddits_at_request requester_subreddits_at_request

And the specific reputation features will use the values included in the following fields for each post: number_of_downvotes_of_request_at_retrieval number_of_upvotes_of_request_at_retrieval requester_upvotes_minus_downvotes_at_request requester_upvotes_minus_downvotes_at_retrieval  requester_upvotes_plus_downvotes_at_request requester_upvotes_plus_downvotes_at_retrieval

requester_user_flair

Using these values for activity and reputation as features, train and test an SVM classifier as described above. Report a table containing the accuracy of your classifier, precision, recall, F1, specificity, and AUC.

<ol start="3">

 <li><em>Model 3 – Narratives </em>: This third model will extract features corresponding to the narrative dimensions identified in [1]. Refer to the enclosed files within “/resources/narratives”. There are five narratives – <em>desire, family, job, money, </em>and<em> student</em>. Each narrative file has a set of words associated with it. To extract post features corresponding to a narrative, perform regular expression match between all words corresponding to the narrative and those corresponding to a post (in the training and test sets)3. The narrative features for a post will be the ratio of the number of matches for each narrative to the total number of white spaced words in the post. Using these five narrative features, train and test an SVM classifier as described above. Report a table containing the accuracy of your classifier, precision, recall, F1, specificity, and AUC.</li>

 <li><em>Model 4 – Moral foundations </em>: This third model will use the dimensions of “moral foundations” as features for classifying successful and unsuccessful requests. These dimensions are based on the moral foundations theory<a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a> that seeks to understand why morality varies so much across cultures yet still shows so many similarities and recurrent themes. In brief, the theory proposes that several innate and universally available psychological systems are the foundations of “intuitive ethics.” The dimensions of the moral foundations include: <em>care/harm, loyalty/betrayal, authority/subversion, </em>and<em> sanctity/degradation</em>. Their descriptions can be found in Appendix II. To extract features corresponding to the different dimensions, first refer to the enclosed file “MoralFoundations.dic” under “/resources” – the file opens with any simple plain text editor program. The dictionary contains terms indexed by integers, where the integers are mapped to the moral foundations dimensions. Then, for a given post in your training or test data3, obtain one feature corresponding to each dimension, by matching (with regular expressions) each word in the dictionary for that dimension to each word in the post. This way, you will obtain a count variable of the occurrence of the dimension in the post. By dividing this count by the total number of white spaced words in the post, you will obtain a normalized feature value for the same dimension. Using these dimensions as features, train and test an SVM classifier as described above. Report a table containing the accuracy of your classifier, precision, recall, F1, specificity, and AUC.</li>

</ol>




<strong>Part 2: </strong>Present a discussion of the performance of the above four models:

<ol>

 <li>Which of the four classifiers performed the best; which one performed the worst?</li>

 <li><em> </em>Describe your anticipated reasoning driving these differences in performance of the classifiers.</li>

 <li><em> </em>For models 3 and 4 in particular, describe their performance compared to models 1 and 2. Why do you think they perform better or worse than models 1 and 2? Between models 3 and 4, which one is better? What could be the reason behind this observation?</li>

 <li><em> </em>Present your reasoning if your models indicate that language is able to predict success of altruistic requests – other than model 2, all of the other models rely on language.</li>

</ol>

<strong>Part 3:</strong> Presentation a comparative discussion of the performance of all of your classification models and the performance metrics (AUC) reported in Table 4 of [1]:

<ol>

 <li>In what ways are your models similar or different from those in Table 4 of [1]?</li>

 <li> Where and why do they perform better or worse compared to [1]?</li>

</ol>

<a href="#_ftnref1" name="_ftn1">[1]</a> Downloaded from the SNAP Stanford website: <u>http://snap.stanford.edu/data/web-RedditPizzaRequests.html</u>  <sup>2</sup> <u>https://www.reddit.com/r/Random_Acts_Of_Pizza/</u> Excerpt from the subreddit description: “Feel like giving a random redditor a free pizza, but don’t know how or who? Well this is the right place for you! Random giving is why we are here!”

<a href="#_ftnref2" name="_ftn2">[2]</a> Post content is given in the field “request_text” in the dataset file pizza_request_dataset.json.

<a href="#_ftnref3" name="_ftn3">[3]</a> <u>http://moralfoundations.org/</u>