# MongoAgent
MongoAgent is an AI-powered assistant that helps generate and execute MongoDB queries using OpenAI. It supports intelligent querying, CRUD operations, collection/documentation exploration, and metadata generation.

# Features
Connect to MongoDB
Auto-generate queries using OpenAI (GPT-3.5)
CRUD operations on collections and documents
Smart prompt handling for listing collections
Auto-inferred schema from sample documents
Optional verbose logging for debugging
Extendable for aggregation and custom operations

# How to install
```
pip install MongoAgent
```
## How to use?

# list where conditions 
```
from MongoAgent import MongoAgent
from dotenv import load_dotenv
import os

load_dotenv()

mongo_url = os.getenv("MONGO_URL")
openai_token = os.getenv("OPENAI_TOKEN")
db_name = os.getenv("DB_NAME")

agent = MongoAgent(mongoURL=mongo_url, openAI_token=openai_token, db_name=db_name)

ai_query = agent.execute(prompt="list all the data in the database name start wihth 'jig'")
print("\n🤖 AI Response:\n", ai_query)
result = agent.execute_from_ai_query(ai_query)
print(result)
```
# Add new entry 
```
from MongoAgent import MongoAgent
from dotenv import load_dotenv
import os

load_dotenv()

mongo_url = os.getenv("MONGO_URL")
openai_token = os.getenv("OPENAI_TOKEN")
db_name = os.getenv("DB_NAME")

agent = MongoAgent(mongoURL=mongo_url, openAI_token=openai_token, db_name=db_name)
ai_query = agent.execute(prompt="Add name jignesh in the database")
print("\n🤖 AI Response:\n", ai_query)

result = agent.execute_from_ai_query(ai_query)
print(result)
```

