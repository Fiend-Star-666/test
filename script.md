# Technical Interview Script - SWE1 Position

## Introduction (2-3 minutes)
"Hi [Candidate Name], I'm [Your Name], a [Your Role] here at [Company]. Today we'll be doing a technical interview that will last about 60 minutes. We'll solve a few coding problems together, and I encourage you to think aloud as you work through them. Feel free to ask any clarifying questions along the way.

Before we begin, do you need a few minutes to set up your preferred coding environment? We can use [mention available options: shared doc/IDE]."

[Wait for response and setup]

"Great! Just to set expectations:
- We'll work through 3 problems of increasing difficulty
- Please think aloud as you solve them
- Feel free to ask questions at any point
- We'll reserve some time at the end for your questions

Does that sound good?"

## Problem Introduction Format (Use for Each Problem)

### Easy Problem (15-20 minutes)
"Let's start with our first problem. I'll paste it in the shared document and give you a moment to read it. Let me know when you're ready to discuss."

[After they read]
"Could you explain your understanding of the problem back to me?"

[After their explanation]
"Good. Before you start coding, could you walk me through your approach?"

#### For Circular Printer:
"Imagine you're building this for a real printer system. What edge cases should we consider?"

##### Hints if stuck:
- "What happens when we need to move from 'z' to 'a'?"
- "Is there always only one optimal path between two letters?"

#### For Alternating Digit Sum:
"What assumptions can we make about the input number?"

##### Hints if stuck:
- "How would you handle the digits one by one?"
- "Is there a pattern in how we treat odd vs even positioned digits?"

### Medium Problem (25-30 minutes)
"Great work on the first problem. Let's move on to something a bit more challenging."

#### For Consecutive Array Construction:
"Before you start coding, what would make this problem particularly tricky?"

##### Hints if stuck:
- "How can we efficiently check if numbers are consecutive?"
- "Do we need to try every possible split point?"

#### For Document Version Compare:
"What are some edge cases we should consider for this version comparison?"

##### Hints if stuck:
- "What happens if we have more dots than characters?"
- "How do we handle consecutive dots?"

### Hard Problem (35-40 minutes)
"For our final problem, we'll tackle something more complex. Take your time to think through this one."

#### For Network Delay Optimizer:
"What makes this problem different from a standard shortest path problem?"

##### Hints if stuck:
- "How can we keep track of both time and cost constraints?"
- "What data structure would be most efficient here?"

#### For Dynamic Data Stream Analyzer:
"Let's think about the trade-offs in data structure choice for this problem."

##### Hints if stuck:
- "How can we efficiently maintain sorted order?"
- "What's the bottleneck in the range removal operation?"

## General Guidance Lines

### When They're Stuck:
"Would you like to talk through what you're thinking? Sometimes explaining it helps clarify the approach."

### When They're Going Off Track:
"That's an interesting approach. Could we take a step back and think about [specific aspect they're missing]?"

### When They're Moving Too Fast:
"Could you explain why you chose this approach? I'd like to understand your reasoning."

### When They've Finished a Solution:
1. "Can you walk me through how this works with the example input?"
2. "What's the time and space complexity of this solution?"
3. "Are there any edge cases we should test?"
4. "Could we optimize this further?"

## Code Review Points
When reviewing their code, look for and ask about:

1. Variable Names:
   "How did you choose these variable names? What was your naming convention?"

2. Error Handling:
   "What kind of error cases should we handle here?"

3. Code Organization:
   "Could you explain how you structured this solution?"

4. Optimization:
   "Are there any performance improvements we could make?"

## Wrapping Up (5 minutes)
"We're coming to the end of our time. You've worked through some challenging problems, and I appreciate your thought process throughout.

Do you have any questions about the problems we discussed or about the technical work we do here at [Company]?"

## Post-Interview Notes Template
```
Candidate Name: 
Date: 
Position: SWE1

Problem Solving:
- Understanding: [1-3]
- Approach: [1-5]
- Solution Quality: [1-5]

Code Quality:
- Naming/Style: [1-2]
- Organization: [1-2]
- Error Handling: [1-2]

Communication:
- Clarity: [1-3]
- Technical Communication: [1-3]
- Question Handling: [1-3]

Problems Completed:
1. [Problem Name] - [Score]
2. [Problem Name] - [Score]
3. [Problem Name] - [Score]

Total Score: [/30]

Key Strengths:
1.
2.
3.

Areas for Improvement:
1.
2.

Overall Recommendation:
□ Strong Pass
□ Pass
□ Weak Pass
□ No Pass

Additional Notes:
```

## Emergency Situations

### If Technical Issues Arise:
"I see we're having some technical difficulties. Let's take a minute to resolve this. We can also switch to [alternative method] if needed."

### If Candidate is Very Nervous:
"Let's take a step back. Could you walk me through how you would solve this with a simple example?"

### If Running Out of Time:
"We have about [X] minutes left. Let's focus on getting a basic solution working, and then we can discuss optimizations if time permits."

### If Candidate is Struggling Significantly:
"Let's break this down into smaller parts. What's the first step we need to take?"

## Follow-up Questions for Strong Candidates
If a candidate finishes early or shows strong performance:

1. System Design Mini-Question:
   "How would you modify this solution to handle millions of records?"

2. Scalability:
   "What would change in your approach if this needed to be distributed across multiple machines?"

3. Real-World Application:
   "How would you test this in a production environment?"

## Red Flags to Watch For:
- Unable to explain their thought process
- Dismissive of edge cases
- Resistant to hints or suggestions
- Poor error handling
- No consideration for performance
- Copy-paste style solutions without understanding

## Green Flags to Note:
- Clarifies requirements before coding
- Discusses trade-offs between approaches
- Writes clean, well-organized code
- Considers edge cases proactively
- Tests their solution
- Communicates clearly throughout

Remember: Stay neutral in your responses, provide consistent hints across candidates, and maintain a supportive but professional environment throughout the interview.
