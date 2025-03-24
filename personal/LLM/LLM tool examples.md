#LLM 
[[How do LLMs work?]]
## Deep-research
- Tool to get a first in-depth report to a more complex topic
- **Always** look at the citations, this tool can still hallucinate at any point!
- Sorta good as an "give me a first summary of this topic"
## File uploads
- Tool that lets you upload something and it gets added to the working memory/context window
- Really helpful, to read books/papers with that feature
## Code interpreters
- Sort of like my understanding of agents
- upon finding a task, that should not be done "by memory":
  --> special tokens that basically say "don't output, but instead write a code that solves this"
  --> output the result of this code
## ChatGPT Analysis
- If you want to have a "junior data analyst" that you can collaborate with
- Can write code and plot charts
- Produces bad code a lot of the times, so be aware of it!
## Claude artifacts
- can write code like other LLMs but can e.g. display personalized apps directly
  --> example usage: 
	  { "prompt": "I added an attachement about Adam Smith, can you create 20 flashcards for me to learn about his life and his work?",
	  "attachment": "<text about adam smith>"
		}
		--> will create the flashcards
		{"prompt": Can you now create an interactive learning app for me that allows me to study those questions?",
		"attachements": ""
		}
		--> will create an anki-like app to study

