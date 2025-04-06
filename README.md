# Getting Structured LLM Output 📊🤖

- Code files from the deeplearning.ai [short course on Structured LLM Output](https://www.deeplearning.ai/short-courses/getting-structured-llm-output)
- [Certificate](https://learn.deeplearning.ai/accomplishments/8ed6fab3-53e7-464e-8b17-e85c6a558751)

## Why Structured LLM Outputs? 🧩

Structured outputs transform raw LLM responses into predictable, machine-readable formats that:

- **Ensure consistency** in response format and structure
- **Simplify integration** with downstream systems and databases
- **Reduce hallucinations** by constraining output scope and format
- **Improve reliability** for production applications
- **Enable validation** of output against schema requirements
- **Facilitate parsing** without complex regex or post-processing

## Types of Structured Output Approaches 🛠️

### 1. Schema-Based (OpenAI)
Uses JSON schema to define the structure directly in the API call, enforced by the model itself.
```python
client.beta.chat.completions.parse(
    response_format=MySchema
)
```

### 2. Retry-Based (Instructor)
Iteratively improves outputs by validating against schemas and retrying when validation fails.
```python
instructor_client.chat.completions.create(
    response_model=MySchema,
    max_retries=3
)
```

### 3. Grammar-Constrained (Outlines)
Uses parsing expression grammars to constrain token generation at inference time.
```python
outlines.generate.json(model, MySchema)
# or
outlines.generate.regex(model, pattern)
```

| No. | Concepts | NBSanity | GitHub |
|-----|----------|----------|--------|
| 1 | • Defining output schemas with Pydantic<br>• Using OpenAI's parse() for structured output<br>• Sentiment analysis of social media mentions<br>• Converting structured data to pandas DataFrames | [![Open In NBSanity](https://nbsanity.com/assets/icon.png)](https://nbsanity.com/Prajwalsrinvas/getting_structured_llm_output/blob/main/1_openai_structured_outputs/L_2.ipynb) | [![GitHub](https://cdn-icons-png.flaticon.com/32/270/270798.png)](https://github.com/Prajwalsrinvas/getting_structured_llm_output/blob/main/1_openai_structured_outputs/L_2.ipynb) |
| 2 | • Using Instructor for structured outputs<br>• Retry-based output generation<br>• Error handling with max_retries<br>• Custom regex validation in Pydantic models<br>• Tracking token usage with retries | [![Open In NBSanity](https://nbsanity.com/assets/icon.png)](https://nbsanity.com/Prajwalsrinvas/getting_structured_llm_output/blob/main/2_reprompting_using_instructor/L_3.ipynb) | [![GitHub](https://cdn-icons-png.flaticon.com/32/270/270798.png)](https://github.com/Prajwalsrinvas/getting_structured_llm_output/blob/main/2_reprompting_using_instructor/L_3.ipynb) |
| 3 | • Structured generation with Outlines<br>• JSON output generation with constraints<br>• Visualizing token probabilities<br>| [![Open In NBSanity](https://nbsanity.com/assets/icon.png)](https://nbsanity.com/Prajwalsrinvas/getting_structured_llm_output/blob/main/3_structured_generation_using_outlines/L_4.ipynb) | [![GitHub](https://cdn-icons-png.flaticon.com/32/270/270798.png)](https://github.com/Prajwalsrinvas/getting_structured_llm_output/blob/main/3_structured_generation_using_outlines/L_4.ipynb) |
| 4 | • Structured generation beyond JSON<br>• Classification with choice()<br>• Regex-based output generation<br>• HTML, CSV and pattern-based outputs<br>• Simplifying regex with DSL<br>• Multi-modal structured outputs (vision) | [![Open In NBSanity](https://nbsanity.com/assets/icon.png)](https://nbsanity.com/Prajwalsrinvas/getting_structured_llm_output/blob/main/4_structured_generation_beyond_json/L_5.ipynb) | [![GitHub](https://cdn-icons-png.flaticon.com/32/270/270798.png)](https://github.com/Prajwalsrinvas/getting_structured_llm_output/blob/main/4_structured_generation_beyond_json/L_5.ipynb) |

## Resources 📚

- [OpenAI Structured Outputs Guide](https://platform.openai.com/docs/guides/structured-outputs?api-mode=responses)
- [Instructor Documentation](https://python.useinstructor.com/start-here/)
- [Outlines Documentation](https://dottxt-ai.github.io/outlines/latest/reference/)