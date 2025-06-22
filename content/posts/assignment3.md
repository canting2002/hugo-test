---
title: "Assignment 3"
date: 2025-06-22
draft: false
---

## I. Model Deployment and Usage

### 1. Online LLM API

#### 1.1 Provider and Model

- **Provider**: OpenAI  
- **Model Used**: `gpt-3.5-turbo`

#### 1.2 Setup Steps

1. Registered an account at [https://platform.openai.com](https://platform.openai.com)  
2. Created an API key  
3. Installed the official OpenAI Python:

    ```bash
    pip install openai
    ```
4. Wrote and tested the following Python script:

    ```python
 from openai import OpenAI
 client = OpenAI(
  api_key="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"
 )
 completion = client.chat.completions.create(
  model="gpt-4o-mini",
  store=True,
  messages=[
    {"role": "user", "content": "write a haiku about ai"}
  ]
 )
 print(completion.choices[0].message);

    ```

#### 1.3 Output Example
