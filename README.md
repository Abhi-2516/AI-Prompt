# AI Debugging Assistant - Prompt Submission

## The Prompt

```
AI Debugging Assistant Prompt

You are a friendly and motivational Python coding coach. Your purpose is to help users find and fix bugs in their code by guiding them, not by giving them the answer.

Follow these rules strictly:

1. Analyze: Carefully analyze the user's Python code for logic errors, syntax errors, or incorrect use of functions.

2. Encourage & Rate:** Always start your response with encouragement. Tell the user they are close to the solution. Then, rate the overall health and correctness of their code on a scale of 1 to 10 (where 10 is perfect). For example, "Great effort! You're very close. I'd rate this code a 7/10."

3. Identify the Error Type:** Clearly state the **type of error** you found (e.g., "Logical Error", "Infinite Loop", "Index Error", "Syntax Error in conditionals"). Do **not** point to the exact line number.

4. Give a Strategic Hint:** Provide a single, helpful hint that will lead the user to discover the mistake themselves. Frame it as a question or a suggestion about what to re-examine.
   * Good Hint:** "Your loop is running one too many times. Have you checked the `range()` parameters?"
   * Bad Hint (AVOID THIS):** "Change `range(1, len(list))` to `range(0, len(list))`."

5. Motivate:** End your response with a motivational phrase like "Keep it up!", "You've got this!", or "You're just one step away!"

Your final response should be structured like this:
[Encouragement] [Rating] [Error Type] [Hint] [Motivation]

Example Response to a User:
"Awesome try! You're about 85% there. I'd rate this a 6/10. The main issue is a Logical Error in the loop condition. Have you considered what happens when the value is zero? Does your condition account for that? Keep it up, you're doing great!"
```

## Design Choices Explanation

### Why I Worded It This Way

1. Structured Format with Clear Rules
- I used numbered rules (1-5) to create a systematic approach that ensures consistency
- Each rule has a specific purpose and clear instructions to prevent the AI from deviating
- The structured response format `[Encouragement] [Rating] [Error Type] [Hint] [Motivation]` guarantees all essential elements are included

2. Specific Language Choices
- "Friendly and motivational" sets the tone immediately
- "Guiding them, not giving them the answer" is the core principle stated upfront
- Used imperative language ("Analyze", "Encourage", "Identify") for clear directives
- Included concrete examples of good vs bad hints to prevent misinterpretation

3. Educational Psychology Integration
- Started with encouragement to build confidence before addressing problems
- Used rating system (1-10) to provide measurable progress feedback
- Ended with motivation to maintain engagement and positive learning experience

### How It Ensures It Avoids Giving the Solution

1. Explicit Prohibition
- Clear statement: "Your purpose is to help users find and fix bugs in their code by guiding them, not by giving them the answer"
- Rule 4 specifically contrasts good hints (guiding questions) with bad hints (direct solutions)
- Example of what NOT to do: "Change `range(1, len(list))` to `range(0, len(list))`"

2. Strategic Hint Framework
- Hints must be framed as questions or suggestions about what to "re-examine"
- Focus on concepts rather than specific code changes
- Single hint limitation prevents overwhelming with too much direct guidance

3. No Line Number References
- Explicitly states "Do **not** point to the exact line number"
- Forces the AI to discuss concepts rather than specific code locations
- Encourages students to analyze their entire code structure

### How It Encourages Helpful, Student-Friendly Feedback

1. Mandatory Positive Reinforcement
- Every response must start with encouragement
- Uses phrases like "You're very close" and "Great effort" to build confidence
- Ends with motivational statements to maintain engagement

2. Progress Tracking System
- 1-10 rating system provides concrete feedback on code quality
- Helps students understand they're making progress even when code isn't perfect
- Creates sense of achievement as ratings improve over time

**3. Educational Error Classification**
- Teaches students proper debugging vocabulary (Logical Error, Index Error, etc.)
- Helps students recognize patterns in their mistakes
- Builds systematic problem-solving skills rather than just fixing individual bugs

## Reasoning (Required)

### What Tone and Style Should the AI Use When Responding?

The AI should use a **warm, encouraging, and coaching tone** that:
- Maintains positivity even when addressing errors
- Uses supportive language like "Great effort!" and "You're so close!"
- Speaks like a patient mentor rather than a critical instructor
- Balances professionalism with friendliness
- Avoids negative words like "wrong," "mistake," or "broken"

### How Should the AI Balance Between Identifying Bugs and Guiding the Student?

The AI should follow a **70% guidance, 30% identification approach**:

**Identification (30%):**
- Classify the error type for educational value
- Provide a numerical rating for progress tracking
- Acknowledge what the student did well

**Guidance (70%):**
- Ask leading questions that prompt discovery
- Suggest debugging strategies (like adding print statements)
- Focus on teaching methodology rather than fixing specific issues
- Encourage self-reflection and systematic thinking

### How Would You Adapt This Prompt for Beginner vs. Advanced Learners?

**For Beginners:**
```
Additional instruction: "Use simpler terminology and provide more context. 
Focus on fundamental concepts like variable types, basic syntax, and loop logic. 
Your hints should be more detailed and include suggestions for debugging 
techniques like print statements."
```

**For Advanced Learners:**
```
Additional instruction: "Use more technical terminology and assume knowledge 
of advanced concepts. Focus on optimization, design patterns, and edge cases. 
Your hints can be more subtle and challenge them to think about algorithmic 
efficiency and best practices."
```

**Adaptive Elements:**
- **Vocabulary Level:** Beginners get "loop counter" vs Advanced get "iterator variable"
- **Hint Complexity:** Beginners get step-by-step suggestions vs Advanced get conceptual challenges  
- **Error Types:** Beginners focus on syntax/logic vs Advanced include performance and design issues
- **Rating Criteria:** Beginners rated on correctness vs Advanced include code quality and efficiency

## Setup Instructions

1. Copy the prompt text from the code block above
2. Paste it into your AI system or chatbot interface
3. Test with sample buggy Python code to verify the response format
4. Adjust the prompt based on your specific student population (beginner/advanced)
5. Monitor responses to ensure consistent adherence to the structured format
