# TASK 3: PROMPTING FOR TASK AUTOMATION

## Objective

Automate customer feedback analysis by converting unstructured customer feedback into structured JSON data.

## 1. Reusable Prompt

You are a customer feedback analyst. Your task is to analyze the given customer feedback and extract the required information.

### Extract the following fields:

- Sentiment
- Category
- Issue
- Priority
- Action Required

### Rules:

- Use only the information provided in the customer feedback.
- Do not invent or assume any missing information.
- If no issue is mentioned, return `"None"`.
- Keep the output concise and clear.
- Sentiment must be one of: `"Positive"`, `"Negative"`, `"Mixed"`, or `"Neutral"`.
- Category must be one of: `"Product"`, `"Delivery"`, `"Payment"`, `"Service"`, or `"Other"`.
- Priority must be one of: `"Low"`, `"Medium"`, or `"High"`.
- For Action Required, provide a concise action based only on the issue mentioned. If no action is needed, return `"None"`.
- Always return the result in the same JSON format.

### Output Format

```json
{
  "Sentiment": "",
  "Category": "",
  "Issue": "",
  "Priority": "",
  "Action Required": ""
}
```

### Customer Feedback

`[Insert customer feedback here]`

---

## 2. Input-Output Examples

### Example 1

**Input:**

“The dress quality is excellent and the color is beautiful, but my order arrived two days late.”

**Output:**

```json
{
  "Sentiment": "Mixed",
  "Category": "Delivery",
  "Issue": "Order arrived two days late",
  "Priority": "Medium",
  "Action Required": "Review the delivery delay and take steps to prevent future delays"
}
```

### Example 2

**Input:**

“I was charged twice for my order. Please refund the extra payment.”

**Output:**

```json
{
  "Sentiment": "Negative",
  "Category": "Payment",
  "Issue": "Charged twice",
  "Priority": "High",
  "Action Required": "Refund the extra payment"
}
```

### Example 3

**Input:**

“The product is great and arrived on time. Thank you!”

**Output:**

```json
{
  "Sentiment": "Positive",
  "Category": "Product",
  "Issue": "None",
  "Priority": "Low",
  "Action Required": "None"
}
```

---

## 3. Reflection

Initially, my prompt did not specify fixed values for sentiment, category, and priority, which could produce inconsistent results.

I improved the prompt by defining allowed values for these fields and requiring a consistent JSON format.

I tested the revised prompt with different customer feedback examples and found that the outputs became more consistent and reliable.
