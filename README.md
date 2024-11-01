# AI Personalized Real Estate Agent: HomeMatch Application

## About the App

In an industry where personalization is key to customer satisfaction, we want to revolutionize how clients interact with real estate listings. The goal is to create a personalized experience for each buyer, making the property search process more engaging and tailored to individual preferences.

## The Challenge

Your task is to develop an innovative application named "HomeMatch". This application leverages large language models (LLMs) and vector databases to transform standard real estate listings into personalized narratives that resonate with potential buyers' unique preferences and needs.

## Core Components of "HomeMatch"

### 1. Understanding Buyer Preferences

- Buyers will input their requirements and preferences, such as location, property type, budget, amenities, and lifestyle choices.
- The application uses LLMs to interpret these inputs in natural language, understanding nuanced requests beyond basic filters.

### 2. Integrating with a Vector Database

- Connect "HomeMatch" with a vector database, where all available property listings are stored.
- Utilize vector embeddings to match properties with buyer preferences, focusing on aspects like neighborhood vibes, architectural styles, and proximity to specific amenities.

### 3. Personalized Listing Description Generation

- For each matched listing, use an LLM to rewrite the description in a way that highlights aspects most relevant to the buyer’s preferences.
- Ensure personalization emphasizes characteristics appealing to the buyer without altering factual information about the property.

### 4. Listing Presentation

- Output the personalized listing(s) as a text description of the listing.

## Requirements and Setup

### 1. Required Technologies

```
- OpenAI
- LangChain
- ChromaDB for Vector/Embeddings Storage
- RAG (Augmented-Retrieval Generation)
- Semantic Search
```

### 2. Project Structure

- HomeMatch.ipynb: The main script that runs the AI real estate agent.
- requirements.txt: A list of the required Python packages.
- credentials.json: File containing all access keys such as the OpenAI API key.
- listings.csv: The CSV file containing the real estate listings. These are LLM generated.

### 3. Deployment Instructions

#### Installation

```
pip install -r requirements.txt
```

#### Setup

Update the `credentials.json` file with your OpenAI API key

## Usage

### 1. High level walkthrough

1. Synthetic Data Generation

   a. Generate at least 10 home listings using a LLM.

2. Semantic Search

   a. Create embeddings of the home listings and store them in a vector database.

   b. Run a semantic search on the embeddings based on the buyer's preferences.

3. Augmented Response Generation

   a. Chain the full conversation (Q&A and results) and augment the listings descriptions by personalizing them while keeping the information factual.

   b. Use the LLM for generating the personalized descriptions of the matched listings.

### 2. Example

The buyer's input or preferences might be something like:

```
A comfortable three-bedroom house with a spacious kitchen and a cozy living room.
A quiet neighborhood, good local schools, and convenient shopping options.
A backyard for gardening, a two-car garage, and a modern, energy-efficient heating system.
Easy access to a reliable bus line, proximity to a major highway, and bike-friendly roads.
A balance between suburban tranquility and access to urban amenities like restaurants and theaters.
```

Here's an example of how the output might look:
The sematic search will return a list of home matches follwoing the format below:

```plaintext
Neighborhood: Meadowbrook Estates
Price: $750,000
Bedrooms: 4
Bathrooms: 3
House Size: 2,500 sqft
Description: Discover this spacious 4-bedroom, 3-bathroom home located in the peaceful neighborhood of Meadowbrook Estates. This property features a gourmet kitchen with granite countertops, a cozy fireplace in the living room, and a private backyard with a patio and garden. The master suite offers a relaxing retreat with a spa-like bathroom and a walk-in closet.
Neighborhood Description: Meadowbrook Estates is a family-friendly community with parks, playgrounds, and walking trails for outdoor activities. Residents can enjoy the nearby shopping centers, restaurants, and schools, as well as easy access to highways and public transportation for commuting to work or exploring the city.
```

After augmenting the results, the matched listings will be scored and personalized using the results along the buyer's preferences and priorities. The final recommendation can look as follows:

```
Home Match Score: 90
Neighborhood: Meadowbrook Estates
Price: $750,000
Bedrooms: 4
Bathrooms: 3
Size sqft: 2,500 sqft
Description: Embrace the comfort and space of this 4-bedroom, 3-bathroom home in Meadowbrook Estates. The gourmet kitchen with granite countertops is perfect for preparing family meals, while the cozy fireplace in the living room creates a warm atmosphere for relaxation. Step outside to the private backyard with a patio and garden, ideal for enjoying outdoor activities and gardening. The master suite offers a spa-like bathroom and a walk-in closet for a peaceful retreat after a long day.
Neighborhood Description: Meadowbrook Estates is a peaceful and family-friendly community with parks, playgrounds, and walking trails for outdoor enjoyment. Conveniently located near shopping centers, restaurants, and schools, this neighborhood offers a serene environment with easy access to highways and public transportation.
```

### 3. Testing

Modify the buyer's answers/preferences to see how the HomeMatch agent generates new home matches and personalizes those matches.
