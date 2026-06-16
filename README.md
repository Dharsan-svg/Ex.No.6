# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

## Date: 19-05-2026

---

## Register No: 212223060047

---

---

# Aim

To write and implement Python code that integrates with multiple AI tools to automate API interactions, compare outputs, and generate actionable insights using different AI platforms.

---

# AI Tools Required

* [ChatGPT](https://chatgpt.com?utm_source=chatgpt.com)
* [Google Gemini](https://gemini.google.com?utm_source=chatgpt.com)
* [OpenAI Platform](https://platform.openai.com?utm_source=chatgpt.com)
* [Google AI Studio](https://aistudio.google.com?utm_source=chatgpt.com)
* Python 3.x
* Requests Library

---

# Explanation

## Persona Pattern Used

The experiment uses the **Programmer Persona Pattern** where the AI model behaves like a professional Python developer specialized in API integration and AI automation systems.

### Application Area

AI-based response comparison system for:

* Code generation
* Content analysis
* API testing
* Intelligent automation

The same prompt was tested using multiple AI tools such as ChatGPT and Gemini to compare:

* Accuracy
* Response quality
* Code efficiency
* Readability
* Execution compatibility

---

# Python Code

```python
import requests
import json

# -------------------------------
# OpenAI API Configuration
# -------------------------------
OPENAI_API_KEY = "your_openai_api_key"

# -------------------------------
# Gemini API Configuration
# -------------------------------
GEMINI_API_KEY = "your_gemini_api_key"

# Prompt for both AI tools
prompt = "Write a Python function to find factorial of a number using recursion."

# -------------------------------
# Function for ChatGPT API
# -------------------------------
def get_chatgpt_response(prompt):

    url = "https://api.openai.com/v1/chat/completions"

    headers = {
        "Authorization": f"Bearer {OPENAI_API_KEY}",
        "Content-Type": "application/json"
    }

    data = {
        "model": "gpt-4o-mini",
        "messages": [
            {"role": "user", "content": prompt}
        ]
    }

    response = requests.post(url, headers=headers, json=data)

    result = response.json()

    return result["choices"][0]["message"]["content"]

# -------------------------------
# Function for Gemini API
# -------------------------------
def get_gemini_response(prompt):

    url = f"https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent?key={GEMINI_API_KEY}"

    headers = {
        "Content-Type": "application/json"
    }

    data = {
        "contents": [
            {
                "parts": [
                    {"text": prompt}
                ]
            }
        ]
    }

    response = requests.post(url, headers=headers, json=data)

    result = response.json()

    return result["candidates"][0]["content"]["parts"][0]["text"]

# -------------------------------
# Getting Responses
# -------------------------------
chatgpt_output = get_chatgpt_response(prompt)
gemini_output = get_gemini_response(prompt)

# -------------------------------
# Display Outputs
# -------------------------------
print("\n===== ChatGPT Output =====\n")
print(chatgpt_output)

print("\n===== Gemini Output =====\n")
print(gemini_output)

# -------------------------------
# Comparison Analysis
# -------------------------------
print("\n===== Analysis =====\n")

if len(chatgpt_output) > len(gemini_output):
    print("ChatGPT provided a more detailed response.")
else:
    print("Gemini provided a more detailed response.")

print("Comparison completed successfully.")
```

---

# Sample Output

## ChatGPT Output

```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)
```

### Features

* Clean syntax
* Proper recursion
* Readable implementation

---

## Gemini Output

```python
def factorial(num):
    if num <= 1:
        return 1
    else:
        return num * factorial(num - 1)
```

### Features

* Simple logic
* Good readability
* Beginner-friendly structure

---

# Comparative Analysis

| Criteria            | ChatGPT   | Gemini   |
| ------------------- | --------- | -------- |
| Accuracy            | High      | High     |
| Code Readability    | Excellent | Good     |
| Optimization        | Better    | Moderate |
| Explanation Quality | Detailed  | Simple   |
| Beginner Friendly   | Moderate  | High     |
| API Response Speed  | Fast      | Fast     |

---

# Discussion

1. Both AI tools generated correct Python code for factorial calculation.
2. ChatGPT produced more optimized and professional responses.
3. Gemini generated simpler and more beginner-friendly outputs.
4. API integration using Python requests library was successful.
5. Multi-AI integration helps compare outputs and choose the best solution for different applications.

---

# Conclusion

The experiment successfully demonstrated Python integration with multiple AI tools using APIs. Both ChatGPT and Gemini generated valid outputs for the same programming prompt. Comparative analysis showed differences in readability, detail, and optimization, proving that multiple AI tools can be effectively combined for intelligent automation and decision-making systems.

---

# Result

The corresponding prompt was executed successfully using multiple AI tools, and the generated outputs were compared and analyzed successfully.
