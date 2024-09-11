# Fashion E-commerce Recommendation System

This project is a basic recommendation system designed for a fashion e-commerce platform using customer transaction and product data. The system aims to provide three types of recommendation strategies: popular item recommendations, content-based filtering, and collaborative filtering, to enhance the customer experience and boost sales.

## Datasets
The project utilizes two datasets available from the [Kaggle H&M Personalized Fashion Recommendations](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations/data):
1. **Transactions dataset (`transactions_train.csv`)**: Records customer transactions, including `t_dat` (transaction date), `customer_id`, `article_id` (product), `price`, and `sales_channel_id`.
2. **Articles dataset (`articles.csv`)**: Details all products in the store, including `article_id`, `prod_name`, `product_type_name`, `product_group_name`, `colour_group_name`, and other attributes.

## Key Features
- **Customer-Based Features**: Created from the transactions data, including:
  - **Average Time Difference Between Purchases**: To identify customer purchasing habits.
  - **Average Spending**: To track customer spending behavior.

- **Item-Based Features**: Generated from the articles data, including:
  - **Item Popularity**: Count of how often each item was purchased over the analyzed period.
  - **Item Embeddings**: Created using TF-IDF on product descriptions to enable content-based similarity searches.

## Recommendations
### Popular Recommendations
- **Popular Item Recommender**: Provides the top 10 most frequently purchased items across the entire customer base.

### Content-Based Filtering
- **Content-Based Recommender**: Suggests items similar to the last purchased product of a customer using cosine similarity on TF-IDF vectors of item descriptions.

### Collaborative Filtering
- **User-Based Collaborative Filtering**: Recommends items based on purchase patterns of similar customers, using cosine similarity on a user-item interaction matrix.

## Implementation
- **Data Preprocessing**: Cleaned and filtered the transactions to a one-month period (September 20, 2019, to October 20, 2019) and matched products with corresponding transactions.
- **Feature Engineering**: Generated features such as average spending and time difference between purchases.
- **Clustering**: Customer segmentation using KMeans to group customers into 3 distinct clusters based on their average spending and purchasing frequency.
  
## Project Structure
- **Data Preprocessing**: Handles the loading and cleaning of the transaction and product datasets.
- **Feature Engineering**: Creates features like time differences between purchases and item popularity.
- **Recommendation Models**:
  - Popular recommendations
  - Content-based filtering using TF-IDF embeddings
  - User-based collaborative filtering

## Instructions
1. **Dataset Access**: Download the datasets from [Kaggle](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations/data) and place them in the appropriate directories.
2. **Google Drive Mount**: Uncomment the Google Drive mount command if running on Google Colab.
3. **Model Training**: Run the provided feature engineering and clustering methods to segment customers and build recommendation models.
4. **Recommendations**: Use the predefined functions to generate popular, content-based, and collaborative filtering recommendations for specific customers.
