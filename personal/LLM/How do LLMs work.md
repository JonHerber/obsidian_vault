#LLM 
- LLMs take an input of words and transform them into tokens
- there are different [tokenizers](tiktokenizer.vercel.app)
![[tokenizer.png]]
- If a LLM gets an input, a tokenstream gets extended 
![[tokens.excalidraw]]
- Model is trained in two stages:
  ![[How do LLMs work? 2025-03-07 09.17.44.excalidraw]]
  --> pre training: gives **knowledge** part of the model
  (however only vague and probabilistic)
  --> post training gives the model it's **face/character**
## Tool usage
- If a model needs to access a tool like web search, it does this with tokens aswell:
  ![[HowIUseLLMs.excalidraw]]
--> e.g. encounter <webSearch> token:
  -->program escapes the "prediction" by the actual LLM (zip) and instead executes a search query
  --> scrapes the top results and tokenizens them
  --> adds them to context window
  --> program goes back to predicting by using LLM
