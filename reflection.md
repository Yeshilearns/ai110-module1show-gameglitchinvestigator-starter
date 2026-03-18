# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

The first time I ran the game, it looked like a simple number guessing game with a clean interface but it quickly felt inconsistent while playing. Some of the hints didnt make sense and the number of attempts seemed off from the start.
One major bug I noticed was that the hints were reversed. When I guessed a number that was too high, the game just told me to "Go Higher", which is incorrect. Another issue was that the attempt counter seemed wrong as it looked like I had already used an attempt even before making my first guess. I also noticed that when starting a new game, the number range didnt always match the selected difficulty, which made the gameplay inconsistennt.

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I mainly used Chatgpt and Gemini to understand the faulty logic and how both tools would interpret the same problem. I used them to break down the code and understand why certain bugs were happening instead of just guessing fixes.
One example where AI was helpful was verifying that the hint logic was reversed in the check_guess function. It confirmed the hint logic was reversed when the guess is greater than secret number, the message should "go lower" but the code was doing the  exact opposite. I had already suspected thiswhile playing game and AI helped confirm and explain it clearly.
However, one limitation I noticed was that AI sometimes assumes behavior without fully testing it. For example, it suggested that certain parts of the code might cause crashes but when I actually ran the game, those crasehes didnt occur. This showed me that I still need to verfiy AI suggestion by running and testing code instead of blinding relying on it.


---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

To decide whether a bug was actually fixed, I tested both manually and using pytest. I would run the game and try different guesses to see if the hints matched correctly, and also check if the attempt counter behaved as expected.
One test I ran using pytest was checking that a guess of 60 against a secret of 50 returns “Too High.” This confirmed that the logic in check_guess was working correctly after the fix. I also tested the win condition by checking that guessing the correct number returns “Win.”
AI helped me understand how to structure the tests properly, especially how the function returns a tuple instead of just a string. This helped me fix my test cases so they correctly checked the output.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

Through this project, I learned that Streamlit reruns the entire script every time the user interacts with the app, like clicking a button or entering input. Because of this, session state is important to store values like the secret number, attempts, and score so they don’t reset on every interaction.
If I were to explain this to a friend, I would explain it by saying that Streamlit keeps refreshing the app from top to bottom, but session state acts like memory that keeps track of important variables between those reruns.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

One habit I want to reuse is testing my fixes instead of assuming they work. Writing simple pytest tests helped me confirm that my logic was correct and made debugging more reliable.
Next time I work with AI on a coding task, I would be more careful about verifying its suggestions. Instead of directly applying changes, I would test them step by step and compare them with my own understanding.
This project changed how I think about AI-generated code because I realized that AI is helpful for guidance and explanation, but it is not always correct. I still need to think critically and verify everything myself.
