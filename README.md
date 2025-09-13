# Prompt for an AI Debugging Assistant

##  Project Overview  
This repository defines an **AI Debugging Mentor**, a structured prompt designed to guide students through debugging Python code.  
Rather than providing the complete solution, the assistant encourages **critical thinking**, **self-discovery**, and **step-by-step problem solving**.

🔗 **Full Prompt:** [View Here](https://github.com/NAMITHA-L/AI-DEBUGGING-ASSISTANT---PROMPT/blob/main/prompt%20for%20debug.md)

---

##  Setup Instructions  

You can test this prompt with any LLM platform that supports custom system prompts or instructions.

**Steps to Use:**
1. Copy the full prompt from the [Prompt File](https://github.com/NAMITHA-L/AI-DEBUGGING-ASSISTANT---PROMPT/blob/main/prompt%20for%20debug.md)  
2. Paste it into the **System Prompt / Custom Instructions** section of your LLM interface (e.g., OpenAI Playground)  
3. Provide a Python code snippet with one or more bugs  
4. Review the structured output and follow the debugging steps  
5. Iterate until the code runs correctly  

---

##  Tone and Style  

- **Professional yet approachable** – avoids negative language  
- **Clear and concise** – uses headings, bullet points, and numbered lists  
- **Socratic questioning** – helps students think critically rather than spoon-feeding answers  
- **Compact but complete** – enough guidance to resolve confusion without overloading details  

---

##  Balancing Bug Identification and Guidance  

The assistant aims to:  
- **Identify bugs clearly** – categorizing syntax, logic, runtime, or performance issues  
- **Guide with hints** – offers micro-diagnostics and test suggestions  
- **Promote self-discovery** – encourages students to run tests, re-check results, and think through fixes  

This balance ensures students learn *why* the bug exists, not just how to fix it.

---

##  Adapting for Learner Levels  

| Learner Level | Adaptation Strategy |
|--------------|------------------|
| **Beginner** | Adds extra explanations of terms, provides smaller hints and step-by-step reasoning |
| **Intermediate** | Balanced hints, focuses on understanding debugging patterns |
| **Advanced** | Minimal hints, emphasizes edge cases, efficiency, and deeper conceptual debugging |

---

##  Design Choices and Prompt Engineering Rationale  

### **Why This Design**  
The prompt is divided into **seven structured parts** to maximize clarity:

1. **Role** – Sets AI persona as a Python Debugging Mentor  
2. **Task** – Defines precise objective (help fix code without full solution)  
3. **Context** – Specifies the learner scenario and goal  
4. **Reasoning** – Guides step-by-step analysis for consistent output  
5. **Rules** – Includes constraints and forbidden actions (no full solution)  
6. **Stop Condition** – Ensures analysis ends with structured, actionable steps  
7. **Output Style** – Ensures crystal-clear, compact, student-friendly formatting  

### **Why This Structure is Effective**  
- Multi-layer instruction eliminates ambiguity  
- Explicit rules preserve academic integrity  
- Stepwise reasoning ensures transparent, reproducible analysis  
- Output format is easy to follow and repeat  

---

##  Safety, Privacy, and Academic Integrity  

- **No malicious code assistance** – refuses to debug code that performs unauthorized access, malware, or credential theft  
- **Secrets protection** – asks students to remove/redact API keys, passwords, or sensitive data before sharing code  
- **No full solution leaks** – forbids multi-line fixes that solve the entire problem; only minimal scaffolding allowed  

---

##  Example  

### **Student Code**
```python
n, m, a, b = list(map(int, input().split()))
q = m * a
c = 0
if (q < b):
    c += n * a
else:
    w = (n // m)
    c += (w * b)
    e = n % m
    c += e * a
print(int(c))
```
###  AI Output (Structured)

**1. Intent Summary**  
This code calculates a minimum cost based on `n, m, a, b` by comparing two approaches.

**2. Key Findings & Diagnostics**  
- Logic is mostly correct but may miss a cheaper option when `e * a > b`  
- **Diagnostic:** Try input where `n % m != 0` and compare remainder cost vs. package cost

**3. Guiding Questions**  
- What if buying one extra package is cheaper than buying `e` tickets individually?  
- Should the program use `min()` to compare both options?  

**4. Conceptual Hints**  
- Compare cost of remainder tickets vs. one more package  
- Consider taking the minimum of the two before final sum  

**5. Debugging Flow**  
1. Reproduce with input where `e * a > b`  
2. Observe current output vs. expected output  
3. Adjust logic to pick the cheaper of the two options  
4. Re-run and verify with multiple test cases  

**6. Minimal Tests**  
- **Input:** `7 3 2 5` → **Expected:** `12` (two packages cheaper)  
- **Input:** `7 3 1 5` → **Expected:** `7` (individual tickets cheaper)  

**7. Next Action**  
Update remainder handling using `min(e * a, b)` before final calculation, then re-test.

---

###  Submission Checklist  

- [x] Prompt is clear, specific, and well-structured  
- [x] Reasoning and design rationale included  
- [x] Tone and style well-defined  
- [x] Beginner vs advanced learner adaptation explained  
- [x] Solution-leak prevention ensured  
- [x] Applicable across diverse debugging tasks  



