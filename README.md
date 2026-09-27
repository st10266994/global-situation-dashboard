## Model Identification

**Model A (Deterministic)**
Llama 3.1, run locally via Ollama with `temperature=0`. This setting makes the model always select the single most likely next token at each step, producing identical output across repeated runs on the same prompt.

**Model B (Probabilistic)**
The same Llama 3.1 model, run locally via Ollama with `temperature=0.8`. This introduces randomness into token selection, so the same prompt can produce varying wording or conclusions across repeated runs.

**Implementation Approach**
Both models were queried identically through the `ollama.generate()` function, using the same live event data pulled from the dashboard's underlying feeds (USGS earthquakes, NASA EONET volcanic activity) as shared context. The only difference between the two calls is the `temperature` option passed to Ollama. Each of the six standard questions was asked twice per model to test output consistency, with results logged and saved to `standard_questions_results.csv`.
