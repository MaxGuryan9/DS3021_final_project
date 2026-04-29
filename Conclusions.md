# Conclusions

## Answering the Question

Our question was: *what student lifestyle factors are most strongly 
associated with high academic performance?* Based on the full modeling process, 
the becomes apparent. The behaviors that most strongly predict a higher Final_Score 
are the number of hours studied per week, class attendance rate, and the number 
of tutoring sessions attended. These three variables produced the largest positive 
coefficients in our best model. This means that an increas in any one of them is 
associated with a meaningful increase in final exam score. On the flip side, 
stress level and exam anxiety score had the strongest negative associations. 
Students with higher reported stress and anxiety are shown to perform worse, 
even when they had their study habits under control. 

This ultimately confirms our original hypotheses. We predicted that hours studied, 
attendance, and exam anxiety would show up as the top predictors of exam score, 
and the data is now here to support that. Another strong predictor was previous GPA, 
which if you think intuitively, does make sense. Those who have pre-existing academic habits, 
can more easily apply them as they progress through school. 

## What the Categorical Variables Tell Us

One of the more surprising findings was how little the categorical lifestyle 
variables, like study method (online/offline/hybrid), part-time job status, 
internet quality, diet quality, and extracurricular participation, actually contributed 
to predicting Final_Score. A model that was built on categorical variables alone produced 
an R² of just 0.006, which means it explained less than 1% of the variance in exam 
scores. Even diet quality, which showed the widest group mean difference (~4 points 
between Good and Poor), added very little to the predictions once the numeric variables were included. 
This suggests that *how much* a student studies and *how stressed* they are while doing so matters 
far more than *how* they study or what else they do with their time.


## Model Performance and Limitations

Our best model was a linear regression model with combined numeric and categorical 
features, as well as 2nd degree polynomial terms. It achieved a Test R² of 0.73 and 
an RMSE of 6.61 points on the held-out test set. What this means is that the model 
explains about 73% of the variance in Final_Score, and predicts scores to within 6-7 
points, on average. For a linear model tasked with predicting a complex outcome like 
academic performance, we feel this is quite a strong result.

Although a strong model, it is important and necessary to acknowledge the limitations:

**1. 27% of variance is unexplained.** Our features do not capture everything that 
influences exam performance. Some things like teaching quality, course difficulty, 
test-day circumstances, and natural smarts are absent from the dataset. A more 
complete model would need richer data for a stronger conclusion.


**2. Correlation is not causation.** This is onlu observational data. We can say that 
studying more hours is *associated* with higher scores, but we cannot claim that 
studying more *causes* higher scores. A student who is naturally more motivated 
may both study more and score higher, and motivation itself is an underlying 
factor that we cannot document nor track.


**3. The model struggles with low performers.** Because Final_Score is left-skewed 
(most students score above 80), students in the failing range of 40-60 are underrepresented 
in the training data. The predicted vs. actual plot showed that the model is 
less reliable for these students with those types of test scores, which unfortunately is the 
group where accurate prediction would matter most for intervention purposes. They are outliers 
in the dataset and can be considered anomolies in the classroom as people, which makes it hard to 
identify the causes early. We hope this is just the first step in helping those who need academic 
intervention in finding the right guidance.

**4. Polynomial features reduce interpretability.** While 2nd degree polynomial 
terms improved predictive performance, they create interaction features (like
Hours_Studied with Attendance) whose individual meanings are harder to explain. 
A simpler linear model would be more interpretable if the goal were to give 
direct guidance to the actual students or advisors.

## Final Thoughts

If a student or academic advisor is looking for the highest-impact lifestyle 
changes to improve exam performance, the data in this project points to three 
things. study for longer, show up in the classroom, and learn ways to manage 
stress and anxiety. These variables dominated the model across every iteration.
Whether it was the simple baseline, to the best polynomial model, these factors 
showed up every time. The categorical choices students make (how they study, 
whether they work part-time, what they eat) appear to matter far less than the quantitative 
commitments they make to their own preparation and mental readiness. Hit the books and stay in school, kids!
