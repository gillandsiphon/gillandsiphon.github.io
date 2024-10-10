+++
title = '🐁 Mini-Project: Calories Vibe Check'
date = 2024-10-09T08:45:00-04:00
draft = false
weight = 1
+++

🐁 This is a 100 minute time-constrained mini-project (speedrun), so this is very informal!

### Coarse Calorie Counting

To what extent can current LLMs estimate calorie counts? Rather than a formal evaluation, this is a vibe check to explore Claude's performance on returning calorie estimates. 

{{< figure src="/img/calorie1.PNG" caption="The Humane Ai Pin video (attempting to) measure the amount of protein in a handful of almonds." >}}

I was inspired to do this mini-project after reading [@AvitalBalwit's How I Use Claude](https://www.avitalbalwit.com/post/how-i-use-claude) piece, which mentions using Claude to provide coarse approximations of totaled calorie counts. I definitely understand the appeal of receiving broad estimates of calorie counts based on descriptions compared to the work required to receive somewhat accurate amounts using traditional counters, which includes: balancing working memory, opening another app, manually inputting measurement and food type, discretion to ensure the right choice was clicked, up to using a food scale or  to measure out food for easier measurement, and so on.

### Claude 3.5

I'll use Claude 3.5 via the API to make this assessment in this mini-project.

I'll also separately use Claude UI to help me with some of the boilerplate and grunt work required to do this mini-project. 

### Generate Test Food Items

With the UI, I generate a few exemplars. I'll focus on common food items with popular and descriptive measurements for this mini-project.

>**Prompt**: Generate some samples I can test and put through claude to see if they're right. I'm thinking like 25 items: 1 egg, 1 cup chicken breast, 1 cup rice, 1 tablespoon butter, eg some common ones.

### Get Ground Truth

I use a calorie counter app called [Cronometer](https://cronometer.com/) to track my calories (when I log them...). For the purposes of this mini-project, I'm going to assume that these calorie amounts are correct (to the extent that they can be/for the purpose of 'ground truth').

#### 

I manually input the food items with ground truth in a csv and then processed in Python.

### Claude Counter

I haven't played with JSON adherency or eliciting structured outputs with Claude, so I'll instruct Claude to output a calorie count integer between tags and extract them out.

I used Claude's prompt generation to whip up this prompt:

```
You are a nutrition expert AI assistant. Your task is to estimate the calorie content of a food item based on a given description. The description will include the type of food and its amount or measurement.

Here is the food description:
<food_description>
{food_description}
</food_description>

Follow these steps to estimate the calorie content:

1. Carefully analyze the food description, identifying the main food item and its quantity or measurement.

2. Based on your knowledge of nutrition and calorie content of common foods, estimate the calorie count for the given food and quantity.

3. Consider factors such as preparation method (e.g., fried, baked, raw) and any additional ingredients mentioned in the description that might affect the calorie content.

4. If the description is vague or lacks specific measurements, make a reasonable assumption based on typical serving sizes.

5. Give the final calorie count.

Write your final calorie count inside <calorie_count> tags. The output should be an integer with no additional text.

Remember, the goal is to provide the most accurate integer estimate possible based on the given information.
```

### Get Results
| Food_Item                         |   Ground_Truth_Calories |   Estimated_Calories |   Error |   Percent_Error |
|:----------------------------------|------------------------:|---------------------:|--------:|----------------:|
| 1 large cooked egg                |                      78 |                   78 |       0 |            0    |
| 1 cup cooked chicken breast diced |                     242 |                  240 |      -2 |            0.83 |
| 1 cup cooked white rice           |                     205 |                  205 |       0 |            0    |
| 1 tablespoon butter               |                     102 |                  102 |       0 |            0    |
| 1 medium apple                    |                      95 |                   95 |       0 |            0    |
| 1 slice whole wheat bread         |                      91 |                   80 |     -11 |           12.09 |
| 2 tablespoons peanut butter       |                     193 |                  195 |       2 |            1.04 |
| 1 cup whole milk                  |                     149 |                  150 |       1 |            0.67 |
| 1 medium banana                   |                     105 |                  105 |       0 |            0    |
| 3 oz grilled salmon fillet        |                     155 |                  177 |      22 |           14.19 |
| 1/2 cup cooked broccoli           |                      17 |                   27 |      10 |           58.82 |
| 1 cup cooked pasta                |                     209 |                  210 |       1 |            0.48 |
| 1 oz almonds                      |                     164 |                  164 |       0 |            0    |
| 1 tablespoon olive oil            |                     119 |                  126 |       7 |            5.88 |
| 1 medium baked potato             |                     164 |                  140 |     -24 |           14.63 |
| 1/2 cup vanilla ice cream         |                     137 |                  140 |       3 |            2.19 |
| 1 cup plain Greek yogurt          |                     145 |                  150 |       5 |            3.45 |
| 2 slices of bacon                 |                      75 |                   86 |      11 |           14.67 |
| 1 cup mixed green salad           |                       8 |                   10 |       2 |           25    |
| 1 tablespoon ranch dressing       |                      67 |                   70 |       3 |            4.48 |
| 1 medium avocado                  |                     227 |                  240 |      13 |            5.73 |
| 1 cup cooked quinoa               |                     222 |                  222 |       0 |            0    |
| 1 oz cheddar cheese               |                     115 |                  115 |       0 |            0    |
| 1 large orange                    |                      86 |                   87 |       1 |            1.16 |
| 1 cup black beans cooked          |                     241 |                  230 |     -11 |            4.56 |