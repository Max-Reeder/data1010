# Lab 3: When Lines Aren't Enough
## Activation Functions & Nonlinearity  ·  Answer Sheet

**Course:** DATA 1010 – Artificial Intelligence in Action

**Group Members (2–4 names)**

1. Max Reeder 2. Matthew May 

3. _______________________________ 4. _______________________________

---

## Module 0: When Straight Lines Fail  (~5 min)

### Q1. Which dataset could you separate perfectly with a straight line? Describe what happened when you tried the slider on the other two — what kept going wrong no matter how you adjusted it?

**Answer:** 
Data Set 1 was the only set in which i could get 100% seperation accurancy. On data set 2 and 3 I could not sperate the data at 100%. The Maximum I could get was 50% for data set 2 and 60% for data set 3. What went wrong was that since it was a stright line and the data groups were in multiple locations the straight line could not seperate all the data equally.

<br><br><br><br>

### Q2. For the ring dataset, sketch or describe what a boundary would have to look like to correctly put the inner circle on one side and the outer ring on the other. Why is a straight line doomed before you even start?

**Answer:** 
Since the data set had two circles of data, an outter ring and an inner ring the boundary line would also have to be a ring placed inbetween each data set in order seperat the data. A stright line was doomed because it would always cut through both circles instead of seperating them.

<br><br><br><br>

### Q3. Based on what you saw, what is one thing a smarter boundary would need to be able to do that a straight line simply cannot?

**Answer:** 
A smarter boundary would need to understand how the data is is positioned and learn to change its shape to create a proper boundary. A strightline can sometimes be the answer but for more complicated data sets the line will not be able to create a 100% accuarate boundary.

<br><br><br>

---

## Module 1: Activation Functions — Bending Space  (~5 min)

> **KEY IDEA:** In Module 0, some dot patterns couldn't be separated by any straight line. One solution would be to invent a more complicated boundary — but that gets messy fast.
> Activation functions take a completely different approach: they rearrange the dots first, so that a straight line can work afterward. Think of it like untangling a knot before you measure it.
> Keep that idea in mind as you answer these questions.

### Q4. In your own words, what did the activation function do to the grid of points? Use the before/after comparison in your answer.

**Answer:**  
Before using the activation dunction the graph was sort of linear, as in for every one box vertically there was one box horizontally. Creating a perfectly square graph. After using the activation function the graph shrinks down to a scale of 1 box and begins to compress and warp the outside points of the grid. 

<br><br><br><br>

### Q5. After the warping, you drew what looked like a straight-line rule — but it created a curved boundary in the original space. How does this solve the problem you identified in Q3?

**Answer:** 
This solves the problem of creating a smarter boundary but also keeping a straight line because since you are distrorting space you can make the straight line bend around the data points to create a smarter boundary. 

<br><br><br><br>

### Q6. Compare how Sigmoid and ReLU each warped the grid. Which changed the space more dramatically? What might be a tradeoff between a dramatic warp and a gentler one?

**Answer:** 
The sigmoid warps the grid in a way that makes the line apear to curve while the ReLU cut out more of a rectangular section as well as cutting through with a diagnol. The ReLU was a much more dramatic warp as a oppsoed to the Sigmoid that was more of a gentle curce throughout the graph. The tradeoff is that a strong warp (ReLU) learns bold patterns much quicker but can lose sight of the smaller details. A gentler warp (Sigmoid) keeps the small details but takes longer to learn patterns. 

<br><br><br><br>

---

## Module 2: Activation Functions in Detail  (~5 min)

### Q7. Test a very large positive input (like 100) on Sigmoid and then on ReLU. What does each one output? Which one keeps changing, and which one flattens out?

**Answer:** 
If you have a very large input for a sigmoid there is a ceiling that limits it from going past 1.00. However if you have a larger input for a ReLU then the output will continously climb with larger and larger inputs. 

<br><br><br>

### Q8. When a function "saturates," its output barely changes even as the input keeps growing — like squeezing a sponge that's already dry. Why would that be a problem for a model that's trying to learn and adjust itself?

**Answer:** 
If a function begins to saturate then the output barely budges no matter how much of the input increases, the model has no signal to follow, it’s stuck and can no longer adjust itself effiecntly. 

<br><br><br><br>

### Q9. The Step function is the simplest of all — just on or off, like a light switch. If simple is usually good, why isn't Step the obvious choice for a learning system? What does it lose by being so rigid?

**Answer:** 
The Step function is simple but also does not give enough data. It has no smooth transisition and because of this rigidity it misses out on learning signals.

<br><br><br><br>

---

## Module 3: Building a Perceptron  (~5 min)

> **KEY IDEA:** A perceptron is the single building block of every neural network. It is tiny and simple on its own — but millions of them, connected in layers, power systems like ChatGPT and image recognition.
> Before answering, look closely at the two-step diagram in the notebook. Make sure you can trace what happens to a number as it moves through the perceptron from input to output.

### Q10. Look at the two-step diagram in the notebook. Without using any math, describe each step in plain language — what goes in, what happens, and what comes out?

**Answer:** 
In order to find which side of the line a specific point is an equation is given to find the importance of the X and Y input. and then taking into account the bias of the line gives you which side your point is on.

<br><br><br><br>

### Q11. Try adjusting only the weights while keeping the bias fixed. What changes about the decision boundary? Now try adjusting only the bias. What changes? Describe the difference between what each one controls.

**Answer:** 
When just changing the weight the ending points of the line change which in turn changes the slope of the line. While chaning the bias changes the height of the line or the y-intercept. 

<br><br><br><br>

### Q12. You've now seen activation functions bend space (Module 1) and a perceptron combine weights, bias, and an activation function (this module). Where exactly in the perceptron does the "bending" happen — Step 1 or Step 2? Why does that matter for what kinds of patterns the perceptron can separate?

**Answer:** 
The act of bending occurs in step 2. That matters because Step 1 can only draw a straight line, but Step 2’s bend lets the perceptron separate more complicated patterns.

<br><br><br><br>

---

## Module 4: Testing the Perceptron's Limits  (~5 min)

### Q13. What was your best accuracy on XOR? On the circles? Describe what kept happening each time you tried a new setting — what ceiling did you keep hitting, and why couldn't you push past it?

**Answer:** 
My best accuarcy for the XOR was 75% and 76% on the circles. Everytime I tried a new setting the line reamined in the same shape but moved in distance and I could never get all the correct points on the side of the line. Always hitting a ceiling around 3/4ths.

<br><br><br><br>

### Q14. A single perceptron can only draw one straight line. How many lines would you actually need to correctly separate XOR's four corners? Describe or sketch where you would place them.

**Answer:** 
In order to seperate an XOR you would need 2 lines in an X formation. Each line cutting inbetween the data sets or imagine the data sets in the empty space of the X

<br><br><br><br>

### Q15. Look back at the whole arc of this lab: straight lines failed → activation functions bent space → a single perceptron still hit a wall. What is the logical next move? What would you add to the system to finally break through?

**Answer:**
I believe the nest logical step is to add in more perceptons and adding them in layers to let the model combine multiple lines onto a graph to better handle complex patterns. 

<br><br><br><br>

---

## Before You Submit

Make sure you have:

- [x] Completed all 5 modules (Module 0–4) using the notebooks
- [x] Answered all 15 questions (Q1–Q15)
- [x] Tried the slider on all three datasets in Module 0
- [x] Compared Sigmoid and ReLU grid warping in Module 1
- [x] Tested large inputs in Module 2
- [x] Adjusted weights and bias separately in Module 3
- [x] Attempted to classify XOR and circles in Module 4
- [x] Written thoughtful, complete answers
- [x] Discussed your answers with your group members

---

**Submission Instructions:**

Submit this completed answer sheet according to your instructor's guidelines (PDF upload, hardcopy, etc.).
