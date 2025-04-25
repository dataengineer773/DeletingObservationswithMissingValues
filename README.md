WE need to delete observations containing missing values, Deleting observations with missing values is easy with a clever line of NumPy, Alternatively, we can drop missing observations using pandas,Most machine learning algorithms cannot handle any missing values in the target and feature arrays. For
this reason, we cannot ignore missing values in our data and must address the issue during
preprocessing.
The simplest solution is to delete every observation that contains one or more missing values, a task
quickly and easily accomplished using NumPy or pandas.
That said, we should be very reluctant to delete observations with missing values. Deleting them is the
nuclear option, since our algorithm loses access to the information contained in the observation’s nonmissing values.
Just as important, depending on the cause of the missing values, deleting observations can introduce
bias into our data. There are three types of missing data:
Missing Completely At Random (MCAR)
The probability that a value is missing is independent of everything. For example, a survey
respondent rolls a die before answering a question: if she rolls a six, she skips that question.
Missing At Random (MAR)
The probability that a value is missing is not completely random, but depends on the information
captured in other features. For example, a survey asks about gender identity and annual salary and
women are more likely to skip the salary question; however, their nonresponse depends only on
information we have captured in our gender identity feature.
Missing Not At Random (MNAR)
The probability that a value is missing is not random and depends on information not captured in
our features. For example, a survey asks about gender identity and women are more likely to skip
the salary question, and we do not have a gender identity feature in our data.
It is sometimes acceptable to delete observations if they are MCAR or MAR. However, if the value is
MNAR, the fact that a value is missing is itself information. Deleting MNAR observations can inject
bias into our data because we are removing observations produced by some unobserved systematic
effect
