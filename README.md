# MEAN-VARIANCE-AND-CROSSCORRELATION
# Simulation of Mean and Variance Using Scilab

## Aim
To write a program for **mean**, **variance**, and **cross-correlation** in Scilab and verify the output.
 
---

## Equipment Needed
- Computer with i3 Processor  
- Scilab Software

---

## Algorithm
1. **Define the Function:** Specify the function you want to simulate. For example, `f(x) = sin(x)` or any other function.  
2. **Generate Sample Points:** Decide on the range and the number of sample points. Generate these sample points within the desired range.  
3. **Evaluate the Function:** Compute the function values at each of these sample points.  
4. **Compute Mean, Variance, and Cross-Correlation:** Use Scilab's functions to calculate the mean and variance of the computed function values.  
5. **Display Results:** Output the computed mean, variance, and cross-correlation.

---

## Procedure
1. Refer to the algorithm and write code for the experiment.  
2. Open **Scilab** on your system.  
3. Type your code in a new editor.  
4. Save the file.  
5. Execute the code.  
6. If any errors occur, correct the code and execute again.  
7. Verify the generated results.

---

## Program

```scilab
clc;
clear;

function fx = pdfx(x)
    fx = 3*(1-x)^2 * x;
endfunction

function fy = pdfy(x)
    fy = 6*(1-x)^2 * x;
endfunction

EX = intg(0, 1, pdfx);
EY = intg(0, 1, pdfy);

disp("1)Mean of X =", EX);
disp("2)Mean of Y =", EY);

function p = f1(u)
    p = u^2 * 3*(1-u)^2;
endfunction

function r = f2(v)
    r = v^2 * 6*(1-v)^2;
endfunction

EX2 = intg(0, 1, f1);
EY2 = intg(0, 1, f2);

vX2 = EX2 - EX^2;
vY2 = EY2 - EY^2;

disp("3)Variance of X =", vX2);
disp("4)Variance of Y =", vY2);

x = input("type in the reference sequence = ");
y = input("type in the second sequence = ");

S1 = max(size(y)) - 1;
r = corr(x, y, S1);

n = 0:length(r)-1;

clf();
plot2d3(n, r);
xtitle("Cross-Correlation", "n", "r[n]");

// Fix x-axis ticks to show 0,1,2,3,4,...
ax = gca();
ax.x_ticks = list(n, string(n));   // positions + labels

xgrid();

```

--- 

## Output

### Mean Values
- Mean of X = 0.25
- Mean of Y = 0.25

### Variance Values
- Variance of X = 0.0375 
- Variance of Y = 0.0375

### Cross-Correlation Input Example
- Reference sequence: `[1, 2, 3, 4, 5, 6, 7, 8]`  
- Second sequence: `[2, 1, 3, 4, 5, 7, 6, 8]`

---

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/326f8ca6-47f1-40bc-b7be-0544d418834f" />


---

## MANUAL CALCULATION:

![WhatsApp Image 2025-12-04 at 15 32 10_29198cbb](https://github.com/user-attachments/assets/c7b59a50-80e6-4b52-87b0-1b49dd71de45)

![WhatsApp Image 2025-12-04 at 15 32 10_d34ed483](https://github.com/user-attachments/assets/795db698-d113-466a-9ba0-7f0d724afa77)


---

## RESULT:
Thus the mean , variance and cross correlation are executed in Scilab and output is verified.
