# 8. Advanced Topics and Techniques

# Conditional Formatting

1. On the **Conditional Format** tab, click the **Add Condition** button 
2. select the column then the formula 
3.  now edit how you want it to be displayed 
4. 

![Untitled](8%20Advanced%20Topics%20and%20Techniques/Untitled.png)

result → 

![Untitled](8%20Advanced%20Topics%20and%20Techniques/Untitled%201.png)

## Using Images for Conditional Formatting

select the image then position only images

![Untitled](8%20Advanced%20Topics%20and%20Techniques/Untitled%202.png)

here’s with default and only images option 

![Untitled](8%20Advanced%20Topics%20and%20Techniques/Untitled%203.png)

## Combining Multiple Analyses

create analyses that are **Unions or Intersections** of multiple analyses. **Like in** **SQL**, the number of **columns** and the corresponding **data types** must be the **same** across all joined analyses.

first analysis  

![Untitled](8%20Advanced%20Topics%20and%20Techniques/Untitled%204.png)

![Untitled](8%20Advanced%20Topics%20and%20Techniques/Untitled%205.png)

types

![Untitled](8%20Advanced%20Topics%20and%20Techniques/Untitled%206.png)

output:

![Untitled](8%20Advanced%20Topics%20and%20Techniques/Untitled%207.png)

you can add a filter prompt to control wat to display also 

![Untitled](8%20Advanced%20Topics%20and%20Techniques/Untitled%208.png)

## Add two prompts for the same columns

add the prompt

Change the column formula to a concatenation of the Fiscal Month column and a null: (two
**single quotes** without any space in between). **"Time"."Fiscal Month" || ''** 

as you can’t add two prompt to the same column in **obiee**