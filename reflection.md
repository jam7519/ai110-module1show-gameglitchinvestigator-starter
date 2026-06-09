# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| Open Developer Debug Info| Secret number should be hidden from players | Secret number was visible in Developer Debug Info | None |
| Guess 1 when secret was 39| Hint should say "Go HIGHER" | HInt incorrectly said "Go LOWER" |None|
| Start new Game  | Score, attempts, and history should reset | Score and guess history carried over into the new game | None |
| Multiple guesses | Attempts should match guess history | Attempts counter and history became inconsistent| None |
| Several wrong guesses | Score should not become negative | Score displayed a negative value (-10) | None |
---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?

  I used ChatGPT to help investigate bugs, understand the application behavior, and verify whether the game was functioning correctly.

  Give one example of an AI suggestion that was correct.

  ChatGPT suggested checking the Developer Debug Info panel for hidden issues. When I opened it, I discovered that the secret number was visible to the user, which was a real bug. I verified this by starting multiple games and observing that the secret number was displayed every time.

  Give one example of an AI suggestion that was incorrect or misleading.

  Initially, I assumed the score reset problem might be caused by Streamlit caching. After testing the New Game button several times, I determined that the actual issue was that the game state variables were not being fully reset. I verified this by observing that the score and history remained after starting a new game.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?

 I tested the application after each change and compared the results to the expected behavior. A bug was considered fixed only when the application consistently behaved correctly across multiple tests.

- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.

 I manually started several new games and checked the Developer Debug Info panel. This test showed that score and history values were not resetting correctly, which helped identify issues with session state management.


- Did AI help you design or understand any tests? How?

 Yes. AI suggested testing edge cases such as repeatedly starting new games, checking the debug information panel, and comparing hints against the secret number. These tests helped reveal bugs that were not immediately obvious.


---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
 
 I learned that Streamlit reruns the entire script whenever a user interacts with the application. Session state is used to preserve information such as scores, guesses, and game progress between reruns. Without properly managing session state, values can persist unexpectedly and create bugs.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?

 I want to continue testing applications systematically and documenting bugs with clear reproduction steps before attempting fixes.
  
- What is one thing you would do differently next time you work with AI on a coding task?

 Next time, I would verify AI suggestions earlier through testing instead of assuming the recommendation is correct. 

- In one or two sentences, describe how this project changed the way you think about AI   generated  code.

 This project showed me that AI-generated code can contain significant bugs even when it appears to work. AI is a useful assistant, but developers must still test, verify, and debug the code themselves.

