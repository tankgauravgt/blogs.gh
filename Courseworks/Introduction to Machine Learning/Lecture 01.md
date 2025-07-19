---
title: "Lecture 01: Introduction to Machine Learning"
---
# Lecture 01: Introduction to Machine Learning

## Course Logistics

- **Course Name**: Introduction to Machine Learning – CS771.
- This course is intended to be a **first introduction** to the subject.
- Lectures are delivered as **three videos every week**, hosted on mooKIT. These are designed to mimic a traditional Mon/Wed/Fri classroom setting.
- The **mooKIT URL** is `https://hello.iitk.ac.in/cs771a/` and requires a CC id and password for login.
- An **additional discussion session** is held every Monday from 6 pm-7 pm via YouTube Live.
- **All course material** will be posted on the mooKIT page.
- **Q/A and announcements** will be handled on Piazza, and students are advised to sign up.

## Course Team

The course team includes:

- Piyush Rai (piyush@cse.iitk.ac.in)
- Soumya Banerjee (soumyab@cse.iitk.ac.in)
- Shivam Bansal (sbansal@cse.iitk.ac.in)
- Dhanajit Brahma (dhanajit@cse.iitk.ac.in)
- Amit Chandak (amitch@cse.iitk.ac.in)
- Neeraj Matiyali (neermat@cse.iitk.ac.in)
- Pratik Mazumder (pratikm@cse.iitk.ac.in)
- Avik Pal (avikpal@cse.iitk.ac.in)
- Niravkumar Panchal (nirav@cse.iitk.ac.in)
- Hemant Sadana (soumyab@cse.iitk.ac.in)
- Rahul Sharma (rsharma@cse.iitk.ac.in)

## Workload and Grading Policy

- **4 homework assignments** (theory + programming) account for **50% of the grade**.
    - **Theory part**: Involves derivations and analysis.
    - **Programming part**: Requires implementing or using ML algorithms and analyzing results. All programming must be done in **Python**.
    - Submissions must be **typeset in LaTeX**.
    - Assignments are to be submitted via Gradescope, with login details provided later.
- **Quizzes and exams** (mid-semester and end-semester) account for the **remaining 50% of the grade**. These will be held online, with details announced later.
- The **exact break-up** of individual components will be announced soon.

## Textbook and References

- No single textbook is "required," but **many excellent texts** are available.
- Different books may vary in topics covered, flavor (e.g., classical statistics, deep learning, probabilistic/Bayesian, theory), and terminology/notation.
- **Reading material** from relevant sources will be provided by the course.
- Resources for learning Python and LaTeX are provided:
    - **Python**: `https://www.geeksforgeeks.org/python-programming-language/`
    - **LaTeX**: `www.sharelatex.com/blog/latex-guides/beginners-tutorial.html` and `www.overleaf.com/learn/latex/Tutorials`

## Course Goals

The course aims to:

- Introduce the **foundations of machine learning models and algorithms**.
- Develop the ability to:
    - **Understand the underlying principles** behind ML models and algorithms.
    - **Understand how to implement and evaluate them**.
    - **Understand/develop intuition on choosing the right ML model/algorithm** for a given problem.
- (Hopefully) **inspire students to work on and learn more about ML**.
- **It is not an introduction to popular software frameworks and libraries** like scikit-learn, PyTorch, or Tensorflow. These can be explored once a foundational understanding of various ML techniques is established.

## Introduction to Machine Learning (ML)

- **ML** is defined as **designing algorithms that ingest data and learn a model of that data**.
- The learned model can be used to:
    - **Detect patterns, structures, themes, or trends** in the data.
    - **Make predictions** about future data and decisions.
- Modern ML algorithms are **heavily "data-driven"**. This means:
    - There is **no need to pre-define and hard-code all the rules** (which would be infeasible or impossible anyway).
    - The rules are **not static**; they can adapt as the ML algorithm ingests more and more data.
- ML enables intelligent systems to be **data-driven rather than rule-driven**. This is achieved by supplying **training data and building statistical models of data**.
- **Overfitting is considered "bad ML"**.
    - Performing perfectly on training data is not sufficient.
    - A good ML model **must generalize well on unseen (test) data**.
    - **Simpler models should be preferred over more complex ones**.

## Key Enablers for Modern ML

The success of modern ML is attributed to:

- The **availability of large amounts of data** to train ML models.
- **Increased computing power** (e.g., GPUs).

## ML Applications and Ethical Considerations

ML applications are abundant, including examples like:

- Automatic Program Correction.
- ML-based colorimetry for water quality assessment. This involves training an ML model to predict concentration levels of compounds based on color changes in test strips images captured by a phone camera. Good ML systems must also be **fair and unbiased**, not just focused on high accuracies. There is a lot of recent focus on fairness and transparency in ML systems to avoid issues like:
- Image captioning systems always assuming a specific gender.
- Self-driving cars being more likely to hit certain demographic groups.
- Predictive policing systems using facial features for criminality prediction.

## Next Class

The next lecture will cover:

- Various **flavors of ML problems**.
- **Data and features**.
- **Basic mathematical operations** on data and features.