1. Web & HTTP Fundamentals
Q1: "What happens when you type google.com in your browser and press Enter?"
Good Answer Should Include:

DNS lookup
HTTP request
Server processing
Response rendering

Follow-up:

"What is HTTPS and how is it different from HTTP?"
"What is a DNS server?"

Q2: "Can you explain what HTTP status codes are? Give examples of common ones."
Expected Knowledge:

200 (OK)
404 (Not Found)
500 (Server Error)
403 (Forbidden)

Follow-up:

"What's the difference between 401 and 403?"
"When would you use 201 vs 200?"

2. Database Concepts
Q1: "What's the difference between WHERE and HAVING in SQL?"
Good Answer Components:

WHERE filters individual rows
HAVING works with grouped data
Simple example of each

Q2: "Explain the difference between DELETE and TRUNCATE."
Key Points:

Transaction logging
Performance impact
Rollback possibility

3. Software Development Concepts
Q1: "What is version control? Why do we use it?"
Expected Points:

Code history
Collaboration
Branch management
Basic Git knowledge

Follow-up:

"What is a merge conflict?"
"What's the difference between git pull and git fetch?"

Q2: "What is the difference between unit testing and integration testing?"
Good Answer Components:

Unit: Testing individual components
Integration: Testing component interactions
Examples of each
Purpose of each type

4. Operating System Basics
Q1: "What is a process? How is it different from a thread?"
Key Components:

Process: Independent execution unit
Thread: Lightweight unit within process
Resource sharing
Simple examples

Q2: "What is deadlock? Can you give a real-world example?"
Expected Knowledge:

Resource contention
Circular dependency
Prevention methods
Real-world analogy

5. Network Fundamentals
Q1: "What is the difference between TCP and UDP?"
Key Points:

Connection-oriented vs connectionless
Reliability vs speed
Use cases for each
Common applications

Q2: "Explain what a port number is and give some common examples."
Expected Knowledge:

Port purpose
Common ports (80, 443, 22)
Service association

6. Security Basics
Q1: "What is Cross-Site Scripting (XSS)?"
Good Answer Components:

Basic attack mechanism
Prevention methods
Impact on users
Simple example

Q2: "What is authentication vs authorization?"
Key Differences:

Identity vs permission
When each is used
Simple examples



Technical Non-Coding Questions for Entry-Level SWE1
1. Web & HTTP Fundamentals
Q1: "What happens when you type google.com in your browser and press Enter?"
Good Answer Should Include:

DNS lookup
HTTP request
Server processing
Response rendering

Follow-up:

"What is HTTPS and how is it different from HTTP?"
"What is a DNS server?"

Q2: "Can you explain what HTTP status codes are? Give examples of common ones."
Expected Knowledge:

200 (OK)
404 (Not Found)
500 (Server Error)
403 (Forbidden)

Follow-up:

"What's the difference between 401 and 403?"
"When would you use 201 vs 200?"

2. Database Concepts
Q1: "What's the difference between WHERE and HAVING in SQL?"
Good Answer Components:

WHERE filters individual rows
HAVING works with grouped data
Simple example of each

Q2: "Explain the difference between DELETE and TRUNCATE."
Key Points:

Transaction logging
Performance impact
Rollback possibility

3. Software Development Concepts
Q1: "What is version control? Why do we use it?"
Expected Points:

Code history
Collaboration
Branch management
Basic Git knowledge

Follow-up:

"What is a merge conflict?"
"What's the difference between git pull and git fetch?"

Q2: "What is the difference between unit testing and integration testing?"
Good Answer Components:

Unit: Testing individual components
Integration: Testing component interactions
Examples of each
Purpose of each type

4. Operating System Basics
Q1: "What is a process? How is it different from a thread?"
Key Components:

Process: Independent execution unit
Thread: Lightweight unit within process
Resource sharing
Simple examples

Q2: "What is deadlock? Can you give a real-world example?"
Expected Knowledge:

Resource contention
Circular dependency
Prevention methods
Real-world analogy

5. Network Fundamentals
Q1: "What is the difference between TCP and UDP?"
Key Points:

Connection-oriented vs connectionless
Reliability vs speed
Use cases for each
Common applications

Q2: "Explain what a port number is and give some common examples."
Expected Knowledge:

Port purpose
Common ports (80, 443, 22)
Service association

6. Security Basics
Q1: "What is Cross-Site Scripting (XSS)?"
Good Answer Components:

Basic attack mechanism
Prevention methods
Impact on users
Simple example

Q2: "What is authentication vs authorization?"
Key Differences:

Identity vs permission
When each is used
Simple examples

Sample Evaluation Matrix
Technical Understanding (0-5)
Copy0: No understanding
1: Very basic concept awareness
2: Can explain simply
3: Good understanding
4: Clear explanation with examples
5: Comprehensive understanding with implications
Communication (0-5)
Copy0: Unable to explain
1: Fragmented explanation
2: Basic explanation
3: Clear explanation
4: Well-structured response
5: Excellent articulation with examples
Common Follow-up Questions
For Web Knowledge:

"How does caching work in browsers?"
"What are cookies used for?"
"What is a REST API?"

For Database:

"What is an index used for?"
"What is ACID in databases?"
"What is normalization?"

For Development:

"What is continuous integration?"
"How do you handle code reviews?"
"What is agile development?"

Red Flags:

Cannot explain basic concepts
Confused about fundamental relationships
No real-world understanding
Unable to provide examples
Resistant to follow-up questions

Green Flags:

Clear conceptual understanding
Provides relevant examples
Makes real-world connections
Asks clarifying questions
Shows enthusiasm for learning

Scenario-Based Questions
Scenario 1: Performance
Q: "A website is loading slowly. What could be the possible reasons?"
Look for:

Database queries
Network latency
Server load
Client-side issues

Scenario 2: Security
Q: "How would you store user passwords securely in a database?"
Expected Points:

Hashing
Salt usage
No plain text
Security best practices

Scenario 3: Scalability
Q: "How would you handle a website with increasing user traffic?"
Key Concepts:

Caching
Load balancing
Database optimization
Resource scaling

System Design Basics
Q1: "Design a simple URL shortener service. What components would you need?"
Look for:

Basic architecture understanding
Data storage consideration
API endpoints
Error handling

Q2: "How would you design a basic file storage system?"
Expected Components:

Storage structure
File organization
Basic operations
Error handling


# Thought-Provoking Technical Questions for Entry-Level SWE

## System Design & Architecture

### 1. Chat Application Design
Q: "Design a basic WhatsApp-like chat system where messages need to be delivered even when the recipient is offline. What are the key components you would need?"

**Good Answer Components:**
- Message queue concept
- Persistent storage
- Delivery status tracking
- Basic offline handling

**Follow-up:**
- "How would you handle message ordering?"
- "What happens if messages fail to deliver?"

### 2. Cache Implementation
Q: "If you were building a photo-sharing app, where would you implement caching and why? What would you cache?"

**Look for:**
- Client-side vs server-side caching
- Cache invalidation understanding
- Resource prioritization
- User experience consideration

## Problem-Solving Scenarios

### 1. Rate Limiting Design
Q: How would you prevent a user from submitting too many requests 
   to your API? Walk me through your thought process.
   

**Key Components:**
- Counter mechanism
- Time window concept
- User identification
- Error handling approach

### 2. Data Integrity
Q: "In a system where users can like posts, how would you ensure a user can't like the same post multiple times, even if they click rapidly?"

**Expected Points:**
- Unique constraint concept
- Race condition understanding
- Client-side vs server-side validation
- Error handling

## AI/ML Concepts (Entry Level)

### Easy Level

#### 1. Classification vs Regression
Q: "If you're building a system to predict house prices, would you use classification or regression? What about for email spam detection? Explain why."

**Good Answer Components:**
- Continuous vs categorical output
- Real-world examples
- Basic understanding of prediction types
- Use case analysis

#### 2. Training Data
Q: "Why do we split data into training and testing sets? What could go wrong if we don't?"

**Key Points:**
- Overfitting concept
- Model validation
- Real-world performance
- Basic evaluation need

### Medium Level

#### 1. Bias in AI
Q: "A company uses AI to screen resumes. What kinds of biases might exist in this system and how might they have gotten there?"

**Look for:**
- Training data bias understanding
- Historical data implications
- Fairness considerations
- Mitigation ideas

#### 2. Feature Selection
Q: "If you're building a model to predict customer churn for a streaming service, what features would you consider important and why?"

**Expected Components:**
- Relevant data identification
- Feature importance concept
- Business understanding
- Data relationship awareness

### Advanced Level

#### 1. LLM Understanding
Q: "How would you explain the difference between traditional rule-based chatbots and modern LLM-based ones to a non-technical person?"

**Good Answer Components:**
- Pattern matching vs understanding
- Flexibility in responses
- Training approach differences
- Limitations of each

#### 2. Ethical AI
Q: "In a self-driving car system, how would you program the car to make decisions in unavoidable accident scenarios?"

**Key Points:**
- Ethical decision-making
- Priority setting
- Safety considerations
- Real-world implications

## Real-World Problem Solving

### 1. Performance Mystery
Q: "Users report that your application becomes very slow after being used for several hours. What could be causing this and how would you investigate?"

**Look for:**
- Memory leak understanding
- Resource monitoring
- Investigation approach
- Solution methodology

### 2. Data Loss Prevention
Q: "You're building a document editor. How would you ensure users don't lose their work if their browser crashes?"

**Expected Approach:**
- Auto-save mechanism
- Local storage usage
- Recovery strategy
- User experience consideration

## System Behavior Questions

### 1. Concurrent Updates
Q: "In a collaborative document editing system like Google Docs, how do you think multiple users can edit the same document simultaneously?"

**Key Components:**
- Conflict resolution
- Real-time sync
- State management
- User experience

### 2. Search Implementation
Q: "How would you implement a search feature that shows results as users type, like Google's autocomplete?"

**Look for:**
- Debouncing understanding
- API efficiency
- User experience
- Performance considerations

## Evaluation Guidelines

### Technical Understanding (1-5)
```
1: Basic concept awareness
2: Can explain simple relationships
3: Understands implications
4: Can connect concepts
5: Deep systematic understanding
```

### Problem-Solving Approach (1-5)
```
1: Linear thinking
2: Basic problem breakdown
3: Multiple approach consideration
4: Trade-off analysis
5: Systematic & creative solution
```

### AI/ML Understanding (1-5)
```
1: Basic terminology
2: Concept understanding
3: Application awareness
4: Implementation insight
5: Ethical & practical considerations
```

## Red Flags:
- Memorized answers without understanding
- Unable to explain reasoning
- No consideration of trade-offs
- Lack of user/business perspective
- No ethical considerations in AI/ML

## Green Flags:
- Structured thinking
- Considers multiple perspectives
- Asks clarifying questions
- Aware of limitations
- Shows ethical awareness
- Connects concepts to real world

## Follow-up Questions Strategy

### For System Design:
1. "What would break first under load?"
2. "How would you monitor this system?"
3. "What security concerns should we consider?"

### For AI/ML:
1. "How would you handle missing data?"
2. "What could go wrong with this model?"
3. "How would you explain this to stakeholders?"

## Scenario Adaptations

### For Junior Candidates:
- Focus on understanding of concepts
- Look for logical thinking
- Value learning approach
- Emphasize basic principles

### For More Experienced:
- Probe deeper into implications
- Expect system-level thinking
- Look for pattern recognition
- Value past experience application

## Interview Flow Example

1. Start with Basic Understanding:
   "What interests you about AI/ML?"

2. Move to Concept Application:
   "How might you use AI in a familiar application?"

3. Explore Problem-Solving:
   "What challenges do you think we'd face?"

4. Discuss Implications:
   "How would this affect users?"






## Note-Taking Template
```
Candidate: ________________
Date: ____________________

Conceptual Understanding:
□ System Design: __/5
□ Problem Solving: __/5
□ AI/ML Concepts: __/5

Approach:
□ Thinking Process: __/5
□ Solution Quality: __/5
□ Communication: __/5

Key Observations:
1. ____________________
2. ____________________
3. ____________________

Overall Rating: __/5

Additional Notes:
____________________
____________________
```


# Entry-Level Technical Questions (Basic Candidates)

## System Understanding Questions

### 1. File Storage
Q: "You're building an app where users can upload photos. Where would you store these photos and why?"

**Look For:**
- Basic understanding of file storage vs database
- Awareness of file size implications
- Simple reasoning about user experience

**Follow-up:**
- "What problems might occur if many users upload at once?"
- "How would you handle failed uploads?"

### 2. User Login
Q: "How would you keep a user logged in even after they close their browser?"

**Good Answer Components:**
- Basic understanding of cookies/local storage
- Simple session concept
- User experience consideration

### 3. Search Feature
Q: "If you're building a search for a small library catalog, how would you make it user-friendly?"

**Key Points:**
- Basic search functionality
- Simple error handling (no results)
- User experience (typos, case sensitivity)

## Real-World Application Questions

### 1. Shopping Cart
Q: "In an online shopping app, what could go wrong with the shopping cart? How would you handle these issues?"

**Look For:**
- Out of stock items
- Price changes
- Session timeout
- Basic error cases

### 2. Form Validation
Q: "You have a registration form. What things would you check before letting a user submit?"

**Expected Points:**
- Required fields
- Email format
- Password strength
- Basic error messages

## Basic AI/ML Understanding

### 1. Everyday AI
Q: "What AI features have you used in your daily life? How do you think they work at a basic level?"

**Good Responses Might Include:**
- Auto-complete in search
- Photo filters
- Email spam detection
- Voice assistants

### 2. Chatbot Understanding
Q: "How would you explain the difference between a simple chatbot (like an automated phone system) and ChatGPT to a friend?"

**Key Points:**
- Pre-programmed vs learned responses
- Flexibility in understanding questions
- Basic limitations understanding

### 3. AI Training
Q: "Why do you think AI needs to be trained with lots of data? Can you give an example?"

**Look For:**
- Basic pattern recognition understanding
- Simple learning analogy
- Real-world example

## Problem-Solving Scenarios

### 1. Password Reset
Q: "Walk me through how you think a password reset feature works when a user forgets their password."

**Expected Components:**
- Email verification
- Temporary link/token
- New password setup
- Basic security awareness

### 2. Mobile App Updates
Q: "Why do mobile apps need to be updated? What could be in these updates?"

**Look For:**
- Bug fixes understanding
- New features
- Performance improvements
- User experience awareness

### 3. Data Backup
Q: "Why should an application backup its data? How often would you do it?"

**Key Points:**
- Data loss prevention
- Basic recovery understanding
- Frequency considerations
- Simple examples

## Follow-up Questions (Keep them Simple)

### For System Questions:
- "What could go wrong?"
- "How would users know if there's an error?"
- "How would you make it faster?"

### For AI Questions:
- "Have you used this feature before?"
- "What problems have you noticed?"
- "How could it be improved?"

## Evaluation Guidelines

### Understanding (1-3)
```
1: Very basic awareness
2: Can explain simply
3: Shows good intuition
```

### Problem Solving (1-3)
```
1: Recognizes basic issues
2: Can suggest solutions
3: Considers multiple factors
```

### Communication (1-3)
```
1: Can convey basic ideas
2: Clear explanation
3: Good examples and reasoning
```

## Red Flags:
- Cannot explain basic concepts
- No logical thinking process
- Unaware of common technology uses
- No interest in how things work

## Green Flags:
- Shows curiosity
- Uses personal examples
- Basic logical thinking
- Asks relevant questions
- Admits when unsure

## Example Good vs Basic vs Poor Answers

### Question: "Why do websites need login systems?"

**Good Answer:**
"To keep user information private and secure. Like how my email needs a password so only I can see my messages. It also helps save my preferences and history, like how Netflix remembers what I've watched."

**Basic Answer:**
"So people can log in and use their account. To keep things private."

**Poor Answer:**
"Because all websites have them."

## Interview Tips

### 1. Starting Questions:
- Begin with their technology usage
- Ask about familiar applications
- Use their experiences as examples

### 2. Follow-up Approach:
- Keep technical depth minimal
- Focus on logical thinking
- Use real-world analogies

### 3. Encouragement:
- Acknowledge good thinking
- Guide with hints when stuck
- Use positive reinforcement

## Note-Taking Template
```
Candidate: ________________
Date: ____________________

Basic Understanding:
□ Technical Concepts: __/3
□ Problem Solving: __/3
□ Communication: __/3

Key Strengths:
1. ____________________
2. ____________________

Areas for Growth:
1. ____________________
2. ____________________

Notable Responses:
____________________
____________________

Overall Impression: □ Good  □ Average  □ Needs Development
```

## Sample Dialogue Flow

Interviewer: "Let's talk about websites you use regularly. What's your favorite website or app?"
[Let candidate choose familiar ground]

Interviewer: "How do you think it remembers your preferences?"
[Build on their personal experience]

Interviewer: "What problems have you encountered using it?"
[Connect to problem-solving]

This approach:
- Starts with familiar territory
- Builds confidence
- Reveals thinking process
- Shows potential
