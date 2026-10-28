
 


# LangChain, LLM’s, Prompt Engineering


Open VS code with a new workspace folder and then open terminal in it. 
We will first install UV in through the terminal, with the command for windows as - 


**Command for UV installation in windows :**


powershell -ExecutionPolicy ByPass -c "irm [https://astral.sh/uv/install.ps1](https://astral.sh/uv/install.ps1) | iex"


![image](/Gen-AI/notes/images/image_1_1793175737169.png)


Then comes the step of creating an environment and activating it, the command for creating an environment or a virtual machine is - 


**Command for checking the UV version and creating a virtual environment :**


uv  - -version  (remove the space between the dashes in the terminal) 


uv venv  (for creating a virtual machine)


![image](/Gen-AI/notes/images/image_2_1793175737461.png)


Then you have to activate the virtual machine using the same command you can see above in the “Activate with: .venv\scripts\activate”. The command you have to put in the terminal would be whatever written in your terminal after the “Activate with: “ statement, as in my case the command would be : 


**Command for activating the virtual machine :** 


.venv\scripts\activate


Once the activation of the virtual machine is done, the next step includes setting up the VM or the project and adding langchain into the system - 


**Command to set up the project/VM :** 


uv init  (this will create a .toml file in your sytem)


**Command for adding langchain -** 


uv add langchain


![image](/Gen-AI/notes/images/image_3_1793175737628.png)


now to check whether langchain has been installed in our sytem or not, make a new [test.py](http://test.py/) file and run the following code prompt


![image](/Gen-AI/notes/images/image_4_1793175737764.png)


which will produce an output as such -


![image](/Gen-AI/notes/images/image_5_1793175737891.png)


Now, to use a LLM there are 2 ways to do it, either you download it locally or use the API key of the model. Using the model locally could cause you storage issues when the model is big in size for ex- openAI, Anthropic etc.


now if you have to use more than one model for ex - Gemini, Anthropic, openAI etc. you’ll have to create a new file in the workspace with the name “ **.env** “. The work of this file would be to store the API keys of each and every model you’ll use. 

The next step is to make API keys for the models, for example if i am using the gemini api key the syntax for that which has to be written in the .env file will be - 


**Command for using API key through .env file :** 


GOOGLE_API_KEY = “write your api key here”


    Now, create two folders names as “CHAT MODEL’ and “EMBEDDING MODEL” because that is what we will learn in the first lesson.


    ![image](/Gen-AI/notes/images/image_6_1793175738210.png)


To use the models we will have to download few data of that models locally as well using the API keys, for that make requirements.txt, in that ask chatgpt to make the things that you need to paste in the requirements.txt file, after pasting save the file using ctrl+s, and then in the terminal run the command listed below to download the data about the model so that you can use it - 


**Command for installing requirements.txt through terminal -** 


uv pip install -r requirements.txt


![image](/Gen-AI/notes/images/image_7_1793175738366.png)


After installing requirements you can make a “chat.py” file in the chatModel folder and then in that file you have to write following things



![image](/Gen-AI/notes/images/image_8_1793175738503.png)


```python
from dotenv import load_dotenv
load_dotenv()
```


The above mentioned code loads the “.env” file which contains all the API keys so that we can use the models.


Then go on to the langchain docs and then go to Models section and copy the code for initializing the model which is as follows - 



```python
from langchain.chat_models import init_chat_model
model = init_chat_model("gpt-6-luna")
```


You can write any model’s name in place of “gpt-6-luna” based on the pricing you can afford from the LLM’s.


Then go ahead with asking a question as follows - 


```python
response = model.invoke("what is cricket")
print(response.content)
```


Now if you only print(response) the output in the terminal would be as follows - 


![image](/Gen-AI/notes/images/image_9_1793175738617.png)


Which is quite big and there are a lot of unwanted things in the same. So instead of using print(response) we use print(response.content) to retrieve only the content portion of the output which is as follows - 


![image](/Gen-AI/notes/images/image_10_1793175738859.png)


Now if you don’t want to use “init_chat_model” and you want to use directly a specific model you can change your code to as follows - 


![image](/Gen-AI/notes/images/image_11_1793175739028.png)


it’s upto you whether you wanna use init_chat_model or the Model Class. If you want to use any other model class you can retrieve its code syntax from the langchain docs.


![image](/Gen-AI/notes/images/image_12_1793175739176.png)


the above code contains parameters such as t**emperature** and **max_tokens** these parameters can be used ahead of the model name, the temperature parameters value lies within 0 and 1, as we go towards 1 from 0 for example 0.7 or 0.9, the answer starts getting more creative. Furthermore the parameter max_tokens value sets a limit of spending tokens and hence affects the output.


# Open source LLM (Hugging face) -


There are two ways to access a model, either use it’s API key which will again have token limitation, but if you want to use a model without any limitation you can install or download that model locally in your system providing you token-less unlimited access to its resources.


So first of all you need to install Hugging Face into your system, there are two ways to do it, you either add it into requirements.txt file as “**langchain_huggingface”** or you can use the command - 


**uv pip install langchain_huggingface**


in the terminal.


Then create the access token through the website and add it into your .env file. 


Now copy a repo id of any model from hugging face for example, I’ve chosen deepseek here


![image](/Gen-AI/notes/images/image_13_1793175739453.png)


the above showed is the repo id in this case.


After copying the repo id we’ll start creating the endpoint of the hugging face by declaring our own LLM with the command - 


**Command :**


```python
from langchain_huggingface import ChatHuggingFace, HuggingFaceEndpoint

llm = HuggingFaceEndpoint(repo_id="deepseek-ai/DeepSeek-R1")

model = ChatHuggingFace(llm = llm)
response = model.invoke("who are you?")
print(response.content)
```


which can also be found on the model docs of the langchain website. Remember the above method requires you to have paid tokens in your hugging face account for that respective model.


Now, to use the model without the use of tokens, you have to download the model locally into your system. For the very same purpose, we’ll use a small model because in general models have a huge downloadable content and size. 


You can directly download the local model through code only, for which you have to install transformers first, the command for the same is - 


**uv pip install transformers**


Also, install pytorch if you still haven’t in your system, for the same, run this command in your active terminal - 


**uv pip install torch --index-url** [**https://download.pytorch.org/whl/cpu**](https://download.pytorch.org/whl/cpu)


Now, go for the installation of the model, the code for the same is as follows - 


```python
from langchain_huggingface import ChatHuggingFace, HuggingFacePipeline

llm = HuggingFacePipeline.from_model_id(
    model_id="TinyLlama/TinyLlama-1.1B-Chat-v1.0",
    task="text-generation",
    pipeline_kwargs=dict(
        max_new_tokens=512,
        do_sample=False,
        repetition_penalty=1.03,
    ),
)

chat_model=ChatHuggingFace(llm = llm)
response = chat_model.invoke("What day is today?")
print(response.content)
```


The output produced for the same is:


![image](/Gen-AI/notes/images/image_14_1793175739606.png)


# Embedding 


Now we will move forward with embedding, embedding is a dense list of number(a vector) that translates human language into a mathematical format that a computer can understand.


for embedding, what you have to do is choose an embedding model first, in my case I am going with gemini-embedding-001, because it was available to use without purchasing credits.


Create an “embedding.py” file in the embedding Model folder you created earlier.


![image](/Gen-AI/notes/images/image_15_1793175739784.png)


Then import the langchain requirement for the same and create an embedding variable to call the imported package with the model name and dimensions declared. (dimensions is the max limit only as it was in the case of chat model).


Then create a vector to use the embedding, which will have the command :


**vector = embeddings.embed_query/document**


You have 2 options to choose either the embed_query method or the embed_document method, the query method is used when you have a single line language that you need to be embedded, and document method is used when you have multiple sentences or an entire document that needs embedding. In my case as an example I'll use the query method.


```python
from langchain_google_genai import GoogleGenerativeAIEmbeddings
from dotenv import load_dotenv

load_dotenv()

embeddings = GoogleGenerativeAIEmbeddings(
    model = "models/gemini-embedding-001",
    dimensions = 64
)

vector = embeddings.embed_query("You are going to learn gen AI")

print(vector)
```


Make sure to import the dotenv package too, so that the code can use the google API key you provided in the .env file.


If you have to work with the embed_documents method, the code for the same is provided below.


```python
from langchain_google_genai import GoogleGenerativeAIEmbeddings
from dotenv import load_dotenv

load_dotenv()

embeddings = GoogleGenerativeAIEmbeddings(
    model = "models/gemini-embedding-001",
    dimensions = 64
)

text = [
    "How are you doing",
    "I'll learn gen AI",
    "You'll learn gen AI"
]

vector = embeddings.embed_documents(text)

print(vector)
```


# Prompt Engineering - 


In this, we’ll be creating a chatbot of our own which we will use in the terminal.


The first step is as usual, import the LLM package from the requirements.txt file and call the method for chatting. 


The next is to invoke the chatbot as we have already committed before too, and print the response, while keeping all in a loop, so that the chatbot can run continuously till you kill it yourself. 


Now even in this I want to introduce with a thing, in the above chat examples, we always used **“response.content”** to print the final result only. But in the case of a chatbot we wont be using **“response.content”.** Why? You’ll see with the example mentioned below - 


```python
from langchain_google_genai import ChatGoogleGenerativeAI

model = ChatGoogleGenerativeAI(
    model = "gemma-4-31b-it",
    temperature = 0.9
)

print("--------------welcome Type 0 to exit---------------")
while True:
    prompt = input("You : ")
    if prompt == "0":
        break
    response = model.invoke(prompt)
    print("bot : ",response.content)
```


See, how we have used reponse.content above, now I’ll represent you the output of the same.


![image](/Gen-AI/notes/images/image_16_1793175739952.png)


In the output, **“response.content”** also prints the thinking process of the chatbot, which we of course do not want, so instead of using **“response.content”** we will be using **“response.text”** so that it only prints the text part and not the thinking part of the output too. The same is represented below along with the output.


```python
from langchain_google_genai import ChatGoogleGenerativeAI

model = ChatGoogleGenerativeAI(
    model = "gemma-4-31b-it",
    temperature = 0.9
)

print("--------------welcome Type 0 to exit---------------")
while True:
    prompt = input("You : ")
    if prompt == "0":
        break
    response = model.invoke(prompt)
    print("bot : ",response.text)
```


And the output for the above code is as follows


![image](/Gen-AI/notes/images/image_17_1793175740117.png)


Now, our chatbot right now does not have the feature of saving the chat history or we can say does not have a memory. Now you might think that we can implement a list that store all the chats and henceforth contribute by being a memory, but what if the person chatted for very long time?? the space complexity will keep on increasing only. So to solve this langchain introduced the method **“messages”**, which has three types - 


![image](/Gen-AI/notes/images/image_18_1793175740237.png)


![image](/Gen-AI/notes/images/image_19_1793175740535.png)


Now we will use all the above mentioned methods to store the message history in a way that it doesn’t get confusing at all. The code for the same is provided below - 


```python
from dotenv import load_dotenv
load_dotenv()

from langchain_groq import ChatGroq
from langchain_core.messages import AIMessage, SystemMessage, HumanMessage

messgaes = [
    SystemMessage(content = "You are a funny person and creates jokes.")
]

model = ChatGroq(
    model = "openai/gpt-oss-20b",
    temperature = 0.9
)

print("--------------welcome Type 0 to exit---------------")
while True:
    prompt = input("You : ")
    messgaes.append(HumanMessage(content = prompt))
    if prompt == "0":
        break
    response = model.invoke(prompt)
    messgaes.append(AIMessage(content = response.text))
    print("bot : ",response.text)

print(messgaes)
```


The print(message) in the last is specifically given so that you’ll be able to see the categorization of human, system and AI messages separately.

