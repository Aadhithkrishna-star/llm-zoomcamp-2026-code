# Using Groq Instead of OpenAI in LLM Zoomcamp

If you don't want to use OpenAI's paid API, you can use **Groq** as a free alternative with minimal code changes.

## 1. Create a Groq API Key

Generate an API key from the Groq Console and add it to your `.env` file:

```env
GROQ_API_KEY=gsk_your_api_key_here
```

## 2. Load Environment Variables

```python
from dotenv import load_dotenv

load_dotenv()
```

## 3. Replace the OpenAI Client

### Original (OpenAI)

```python
from openai import OpenAI

openai_client = OpenAI()
```

### Updated (Groq)

```python
from openai import OpenAI
import os

openai_client = OpenAI(
    api_key=os.getenv("GROQ_API_KEY"),
    base_url="https://api.groq.com/openai/v1"
)
```

## 4. Change the Model Name

Replace the OpenAI model with a Groq-supported model.

**OpenAI**

```python
model="gpt-4.1-mini"
# or
model="gpt-4o-mini"
```

**Groq**

```python
model="llama-3.3-70b-versatile"
```

## Summary

To switch from OpenAI to Groq, you only need to change:

* `OPENAI_API_KEY` → `GROQ_API_KEY`
* Add `base_url="https://api.groq.com/openai/v1"`
* Replace the model name with a Groq-supported model

The rest of the Zoomcamp code generally works without modification.

---
**Session timeout**
Since you are using the Github codespaces, if it is not active for certain period of time, then the session will be timed out and we need to start again. The same goes for the jupyterhub notebook that was launched from the VS Code terminal.

We shall re-open the jupyterhub with the following steps: 

***Start Jupyter*** :

```
uv run jupyter notebook
```
Create a new notebook. Throughout the course, you'll copy code from the section notes into notebook cells.

***Configure the client*** :

```
from openai import OpenAI
import os

openai_client = OpenAI(
    api_key=os.getenv("GROQ_API_KEY"),
    base_url="https://api.groq.com/openai/v1"
)
```
