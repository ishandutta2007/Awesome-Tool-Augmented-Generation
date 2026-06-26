# Single-Turn Function Dispatch

Single-Turn Function Dispatch is the simplest form of Tool-Augmented Generation, where a query maps directly to a single external function call. Once the tool executes, its result is returned to the model to generate the final response.

## Architecture & Flow

The user query is processed, the tool is called once, and the response is finalized. There is no feedback loop or multi-step reasoning.

```mermaid
flowchart LR
    A[User Query] --> B[LLM Identifies Tool]
    B --> C[Format Tool Payload]
    C --> D[Execute Tool]
    D --> E[Inject Result into LLM]
    E --> F[Generate Final Answer]
```

## Key Characteristics
- **Low Latency:** Only includes a single tool execution turn, making it fast and predictable.
- **Deterministic Routing:** Ideal for structured utility tasks like calculations, currency conversions, or fetching specific records.
- **Foundational Paper:** [TALM: Tool Augmented Language Models](https://arxiv.org/abs/2205.12255) (Parisi et al., 2022).
