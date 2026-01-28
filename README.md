# StudyGeniePro
![Alt text](assets/studygenie.png)


StudyGeniePro is a cutting-edge console-based sequential multi-agent system that provides a structured, agent-driven learning experience. Designed for self-learners in the era of Generative AI, StudyGeniePro eliminates the fragmentation and inefficiencies of traditional self-study methods. It guides users from "Zero-to-Hero" with a cohesive workflow, ensuring both structure and validation throughout the learning journey.

---

## Problem Statement

In the age of infinite information, self-learners face two core challenges:

1. **Tutorial Hell & Analysis Paralysis**: Constantly searching for the "perfect" roadmap or learning videos often wastes more time than actual learning.  
2. **The Illusion of Competence**: Passive consumption (e.g., watching videos or reading AI-generated summaries) creates a false sense of mastery. Without proper active recall or testing, learners move forward with shaky foundations, leading to frustration and often dropping out.

**StudyGeniePro** addresses these challenges by replacing fragmented self-study approaches with a unified, agentic workflow.

---

## Why Agents?

Traditional Large Language Models (LLMs) are "stateless" conversational engines that are not ideal for structured learning systems. **Agents** offer specific advantages for solving this:

1. **State Management**:
   - Persistent memory ensures that the user's progress (e.g., `Module 4 of 10`) is recorded and progressions remain structured.

2. **Orchestration**:
   - Task-specific personas (e.g., "Professor" for teaching, "Examiner" for testing) ensure highly focused operations, reducing errors like hallucinations.

3. **Control Flow**:
   - With remedial logic loops in place, the user cannot skip essential material without passing validation. This creates an active-feedback learning cycle impossible with static models.

---

## Architecture

StudyGeniePro uses a dedicated multi-agent system orchestrated through Python code to deliver an interactive and thoroughly validated learning experience.

### Core Agents and Responsibilities

1. **The Architect Agent (The Planner)**:
    - **Input**: User-provided topic (e.g., "Learn Python").  
    - **Task**: Generates a structured 10-Module Syllabus (`Beginner to Advanced`) in JSON format.  
    - **Output**: Validated JSON syllabus.

2. **The Professor Agent (The Teacher)**:
    - **Input**: Current Module Title + Topic.  
    - **Task**: Produces deep-dive, textbook-quality lesson content (~600 words) using `Chain-of-Thought` prompting. Covers "Why", "How", and real-world analogies.  
    - **Output**: Lesson in Markdown format.

3. **The Examiner Agent (The Auditor)**:
    - **Input**: Text from the Professor Agent.  
    - **Task**: Creates a progressive 3-question quiz (Easy, Medium, Hard). Answers are extracted only from the lesson to ensure fairness.  

4. **The Supervisor Logic (The Guardrails)**:
    - **Logic**: Python-defined flow to validate performance.  
    - **Pass Criteria**: ≥ 2/3 correct -> Advance to next module.  
    - **Fail Criteria**: < 2/3 correct -> Retry remedial loop (review lesson and re-test).  

---

## Features

- **Stateful Learning**: Tracks module progress and enforces completion steps.
- **Agent-Specific Workflows**: Modular agent system separates planning, teaching, and validation processes.
- **Active Recall**: Built-in testing guards against illusions of mastery.
- **Error Recovery**: Remedial loops ensure learners build strong foundations.
- **Human-in-the-Loop Validation**: Users actively participate in validation gates.

---

## User Journey

1. **Initialization**:
    - User runs the system in a Kaggle Notebook.  
    - Interactive ASCII banner loads for branding.  

2. **Topic Selection**:
    - User enters a topic (e.g., "Quantum Physics").  

3. **Planning**:
    - The Architect generates a 10-module roadmap (e.g., Wave-Particle Duality, Quantum Entanglement).  

4. **Learning**:
    - The Professor produces detailed chapters for each module.  

5. **Testing**:
    - The Examiner provides 3 multi-choice questions per lesson.  

6. **Feedback**:
    - Results determine progression:
        - 2/3 or higher: Advance to the next module.  
        - Below 2/3: Trigger remedial loop and reload.  

7. **Graduation**:
    - After completing all modules, a certificate is issued.  

---

## Demo

**Run Environment**: Kaggle Notebook Console.  

Workflow:
1. Clone and run the repository.
2. Follow sequential prompts from topic selection to graduation.

Sample Initialization Snippet:
```python
print("===== Welcome to StudyGeniePro =====")
# Get started with a new journey
```

---

## Built Using

- **Language**: Python  
- **Notebook**: Kaggle Console for stability & execution.  
- **Brain**: Google Gemini 1.5 Flash  
- **Data Format**: JSON for agent task communication.  

---

## Potential Enhancements

If extended, the following features would strengthen StudyGeniePro:  

1. **Persistent Database**:
    - Add SQLite for saving progress between sessions.  

2. **PDF Export**:
    - Compile lessons and quizzes into a downloadable coursebook.  

3. **Socratic Tutor Mode**:
    - Introduce a conversational tutor agent to delve into incorrect answers and support users before retrying a quiz.  

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/srkeyyyy/StudyGeniePro.git
   ```

2. Navigate to the repository:
   ```bash
   cd StudyGeniePro
   ```

3. Open the Kaggle Notebook and run the system.

---

## Final Thoughts

StudyGeniePro represents a significant step forward in self-learning solutions. By blending structured content, smart agents, and remedial logic, it offers a complete, user-centric educational platform.

Unlock your learning potential with StudyGeniePro and experience the future of education today!
