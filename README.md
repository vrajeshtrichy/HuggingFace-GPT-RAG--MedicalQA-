# Building A RAG System with OpenAI GPT 4.0, Elasticsearch and Hugging Face Models

Authored By: [Rajesh Kanna](https://www.linkedin.com/in/vrajeshtrichy/)

This notebook walks you through building a Retrieval-Augmented Generation (RAG) powered by Elasticsearch (ES) and Hugging Face models, letting you toggle between ES-vectorising (your ES cluster vectorises for you when ingesting and querying) vs self-vectorising (you vectorise all your data before sending it to ES).

## Data sourcing and preparation

The data utilised is sourced from Hugging Face datasets, specifically the
[MongoDB/whatscooking.restaurants dataset](https://huggingface.co/datasets/MongoDB/whatscooking.restaurants).

Embedding model from HuggingFace: [thenlper/gte-small](https://huggingface.co/thenlper/gte-small)

GPT Model from OpenAI: [OpenAI /gpt-4o-mini](https://platform.openai.com/docs/models/gpt-4o-mini)


## Perform Vector Search on User Queries

If `USE_ELASTICSEARCH_VECTORISATION` is true, the text query is sent directly to ES where the uploaded model will be used to vectorise it first before doing a vector search. If `USE_ELASTICSEARCH_VECTORISATION` is false, then we do the vectorising locally before sending a query with the vectorised form of the query.

## Sample Query and Results

Enter your search query: Suggest 5 non alcoholic Chinese restaurant in Queens


########################################################## 


USER:  Suggest 5 non alcoholic Chinese restaurant in Queens

XBOT:  Here are five non-alcoholic Chinese restaurants in Queens:

1. **A Taste Of Shanghai Restaurant**
   - **Stars:** 3.5
   - **Review Count:** 14
   - **Price Range:** 2
   - **Menu Highlights:** Wonton soup, sweet and sour chicken with lemon, dumplings, and sesame chicken.
   - **Parking:** Available.

2. **New Dragon City Kitchen**
   - **Stars:** 3.5
   - **Review Count:** 124
   - **Price Range:** 2
   - **Menu Highlights:** Chicken chow mein, potstickers, shrimp fried rice, and sweet rice.
   - **Parking:** Available.

3. **Yummy Dim Sum**
   - **Stars:** 4
   - **Review Count:** 7
   - **Price Range:** 1
   - **Menu Highlights:** Hot and sour soup, wonton wrappers, steamed buns, and crab rangoons.
   - **Parking:** Available.

4. **Ru Yi Restaurant**
   - **Stars:** 3.5
   - **Review Count:** 48
   - **Price Range:** 1
   - **Menu Highlights:** Char siu bao, Szechuan chicken, egg rolls, and hot and sour soup.
   - **Parking:** Available.

5. **Happy Gathering**
   - **Stars:** 2
   - **Review Count:** 9
   - **Price Range:** 2
   - **Menu Highlights:** Wonton wrappers, spring rolls, chicken chow mein, and sweet and sour pork.
   - **Parking:** Available.

These restaurants provide a variety of Chinese dishes without alcoholic beverages, making them great options in Queens.

