# LM-Agent

Agent with compositional reasoning.

LLM: OpenAI GPT4 / Mixtral (local).

Tools: Google real-time Search, Math Calculator.

The following is a snippet of the jupyer code file, where we ask a question, and then the LM-Agent autonomously decides if and when to use web-search tool, also the calculator tool, in order to answer our question.
Our question:
```
user_request = "how many days till the next solar eclipse"
```

The first step taken by the Agent:

```
* LLM response: 
Thought: To answer this question, I need to find out the date of the next solar eclipse and then calculate the difference between that date and today's date. 
Action: Search
Action Input: "Next solar eclipse date" 
```

Once the Agent finds the date for the next solar eclipse via internet search, it reasons and plans the next step:

```
* LLM response: 
Thought: The next solar eclipse will be on April 8, 2024. Now I need to calculate the number of days between today's date (January 8, 2024) and the date of the next solar eclipse.
Action: Calculator
Action Input: "Calculate the number of days between January 8, 2024 and April 8, 2024" 
```

And finally the Agent decides that the satisfactory answer is found, so that will present it to the human user as the last step:

```
* LLM response: 
Thought: Now that I have calculated the number of days until the next solar eclipse, I can provide the answer to the human.
Action: Response To Human
Action Input: "The next solar eclipse will occur in 90 days, on April 8, 2024." 
```
