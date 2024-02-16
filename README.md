# Mass Shooting research

### Introduction ###

The present analysis on mass shootings is based on a dataset curated by the Violence Prevention Project. The dataset is comprised of a number of variables, spanning from psychological to sociological to medical factors. However, the present analysis focuses on sociological factors. In particular, the aim of the project is to identify relevant predictors in determining the severity of a mass shooting (which is defined as the number of victims), train and evaluate various models for regression on the number of victims killed in these episodes.

We believe that people who resort to mass violence actually nurture a deep desire to be seen, and are willing to commit mass murder to become a momentary "star". Therefore, it is not unusual for these individuals to communicate their intentions, as a means to attract attention upon themselves. This is oftentimes paired with the idea that making as many victims as possible will make the news "bigger". By extension, our hypothesis is that killers who treat the shooting like a performance (ie. filming themselves) purposely aim to having as many victims as possible.
We thus aim to find an answer to the following questions.
- Is a higher death toll correlated to certain motivations behind the shooting?
- Is a higher death toll correlated to the leakage of a killer's intentions?

---

### Methodology ###

In order to investigate the relationship among these variables, we follow this approach:
- We start with an exploratory analysis, where we visualize the data and uncover relations between continuous and categorical variables.
The variables considered are:
  - Day.of.Week
  - Month
  - Year (1966-2023)
  - State
  - Urban.Suburban.Rural (place in which the shooting took place): Urban = 0, Suburban = 1, Rural = 2
  - Location: School = 0, College/university = 1,	Government building / place of civic importance = 2,	House of worship = 3,	Retail = 4,	Restaurant/bar/nightclub = 5,	Office = 6,	    Place of residence = 7,	Outdoors = 8,	Warehouse/factory = 9,	Post office = 10
  - Insider.or.Outsider: whether the shooter had a previous relationship with the location where the shooting took place
  - Multiple.Locations: No = 0, Yes = 1
  - Armed.Person.on.Scene: whether an armed person was present on the shooting scene
  - Number.Killed: number of victims
  - Number.Injured: injured people
  - Age: age of the shooter
  - Gender: Male = 0,	Female = 1,	Transgender = 2
  - Race: White = 0,	Black = 1,	Latinx = 2,	Asian = 3,	Middle Eastern = 4,	Native American = 5
  - Immigrant
  - Military.Service
  - Criminal.Record
  - Bully
  - Bullied
  - Signs.of.Being.in.Crisis
  - Motive..Racism.Xenophobia
  - Motive..Religious.Hate
  - Motive..Misogyny
  - Motive..Homophobia
  - Motive..Employment.Issue
  - Motive..Economic.Issue
  - Motive..Legal.Issue
  - Motive..Relationship.Issue
  - Motive..Interpersonal.Conflict.
  - Motive..Fame.Seeking
  - Leakage.: Communication to a third party of an intent to do harm
  - Interest.in.Past.Mass.Violence
  - Relationship.with.Other.Shooting.s.
  - Planning
  - Performance: e.g. filmed, costume
 
By plotting continuous variables on boxplots based on levels of the categorical variables, we notice that some variables, such as Leakage, Interest in other shootings, relationship with other shootings, planning and interest in violence actually do determine two different levels of mortality in the shootings.

- We thus perform an inferential analysis through the Wilcoxon test, since the data doesn't show a normal distribution. The tests suggest that there is enough evidence to reeject the hypothesis that, in the presence of leakage, the average number of people killed is the same as in the lack of leakage. Furthermore, it suggests that whether the killer considered the shooting as a performance actually determined its severity. Finally, fame-seeking motivations also determine on average more victims.
- By building a series of machine learning models (linear regression, decision trees, random forests and boosted trees), we aim at predicting the severity of future shootings. The variables which are considered to be more informative by the models are oftentimes the same, once again consistent with the initial hypotheses. The best-performing model, random forest, suggests that informative predictors are Bullied, Race, Performance and Leakage.
We can thus conclude that the data suggests a relation between the need for visibility of shooters and the number of victims.

---

### Requirements to run the project ###
A jupyter environment with:

- R kernel
- the possibility to install the libraries mentioned in the .ipynb files
- In order to use the dataset, one should request it to the Violence Prevention Project, as it is not available for public display. Additional information can be found on their website: https://www.theviolenceproject.org
  
