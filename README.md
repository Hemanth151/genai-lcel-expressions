## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

### PROBLEM STATEMENT:

### DESIGN STEPS:

#### STEP 1:

#### STEP 2:

#### STEP 3:

### PROGRAM:
import os
import openai

from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv())
openai.api_key = os.environ['OPENAI_API_KEY']

from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.output_parser import StrOutputParser

prompt = ChatPromptTemplate.from_template(
    "Summarize the following {type} meeting in simple words: {content}"
)

model = ChatOpenAI(model="gpt-4o-mini", temperature=0.7)
output_parser = StrOutputParser()

chain = prompt | model | output_parser

response = chain.invoke({
    "type": "project",
    "content": "The team discussed project progress, upcoming deadlines, task assignments, and the next review meeting."
})

print("Generated Summary:")
print(response)

### OUTPUT:
<img width="713" height="371" alt="image" src="https://github.com/user-attachments/assets/d911a4be-2328-47c0-b35e-293d94c33cc9" />





### RESULT:
Thus, the LCEL expression was successfully implemented using two prompt parameters and three key components. The chain generated meaningful responses and demonstrated its applications in real-world scenarios.
