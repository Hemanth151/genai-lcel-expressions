## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

### PROBLEM STATEMENT:

### DESIGN STEPS:

#### STEP 1:

#### STEP 2:

#### STEP 3:

### PROGRAM:
/*
import os
import openai

from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv())
openai.api_key = os.environ['OPENAI_API_KEY']

from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.output_parser import StrOutputParser

prompt = ChatPromptTemplate.from_template(
    "tell me biography about {topic}"
)
model = ChatOpenAI(model="gpt-4o")
output_parser = StrOutputParser()

chain = prompt | model | output_parser
chain.invoke({"topic": "gandhi"})
from langchain.embeddings import OpenAIEmbeddings
from langchain.vectorstores import DocArrayInMemorySearch

vectorstore = DocArrayInMemorySearch.from_texts(
    ["Hemanth is a engineering student", "gandhi loves tea"],
    embedding=OpenAIEmbeddings()
)
retriever = vectorstore.as_retriever()
retriever.get_relevant_documents("Hemanth is which student?")
template = """Answer the question based only on the following context:
{context}

Question: {question}
"""
prompt = ChatPromptTemplate.from_template(template)
from langchain.schema.runnable import RunnableMap

chain = RunnableMap({
    "context": lambda x: retriever.get_relevant_documents(x["question"]),
    "question": lambda x: x["question"]
}) | prompt | model | output_parser
chain.invoke({"question": "Hemanth is which student?"})
*/

''''

### OUTPUT:
<img width="852" height="167" alt="image" src="https://github.com/user-attachments/assets/05a828a5-e719-41e1-8b41-4784b7845ebd" />

<img width="837" height="252" alt="image" src="https://github.com/user-attachments/assets/5b278978-2b53-4ab2-a416-9b1564757ed1" />

<img width="855" height="326" alt="image" src="https://github.com/user-attachments/assets/409b893d-35ab-4272-8f89-a82d82aa5ff9" />




### RESULT:
