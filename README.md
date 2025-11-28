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
// ---------- MEAN VALUE ----------
function X = f(x)
    z = 3 * (1 - x)^2;
    X = x * z;
endfunction

a = 0;
b = 1;
EX = intg(a, b, f);

function Y = c(y)
    z = 3 * (1 - y)^2;
    Y = y * z;
endfunction

EY = intg(a, b, c);

disp("Mean of X = " + string(EX));
disp("Mean of Y = " + string(EY));

// ---------- VARIANCE ----------
function X2 = g(x)
    z = 3 * (1 - x)^2;
    X2 = x^2 * z;
endfunction
EX2 = intg(a, b, g);
vX2 = EX2 - (EX)^2;

function Y2 = h(y)
    z = 3 * (1 - y)^2;
    Y2 = y^2 * z;
endfunction
EY2 = intg(a, b, h);
vY2 = EY2 - (EY)^2;

disp("Variance of X = " + string(vX2));
disp("Variance of Y = " + string(vY2));

// ---------- CROSS CORRELATION ----------
x = input("Type in the reference sequence = ");
y = input("Type in the second sequence = ");

n1 = max(size(y)) - 1;
n2 = max(size(x)) - 1;

r = corr(x, y, n1);

plot2d3('gnn', r);

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
- Second sequence: `[2, 1, 3, 5, 6, 3, 5, 9]`

---

<img width="795" height="760" alt="image" src="https://github.com/user-attachments/assets/3a736c17-cdc9-4534-8d1b-81a5688ca336" />


---

## MANUAL CALCULATION:

![20251128_200109](https://github.com/user-attachments/assets/ff7ecc4c-d67c-4ee0-a1ca-48e75045c6a8)


---

## RESULT:
Thus the mean , variance and cross correlation are executed in Scilab and output is verified.
