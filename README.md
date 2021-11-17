# Medical predictions (diabetes case)
This application converts a sequence of numbers into states. The states are arranged in a transition matrix and the transition probabilities are calculated for each element. The transition matrix is further used for a prediction in a Markov chain. For example, the application takes the following sequence of numbers:
```
159,82,187,194,179,115,197,102,105,104,95,126,74,143,143,127,98,70,92,170,168,182,149,85,137,100,170,180,61,177,86,195,198,182,150,197,103,103,186,100,96,196
```

The above sequence represents the glycemic values from a single individual who does not have diabetes, but a family predisposition for diabetes. Each number in the sequence represents a day. Thus, the sequence contains observations that extend over 42 days.

# Diabetes prediction prototype
The application “Diabetes prediction prototype” is an experimental software intended as a method of prediction for type II diabetes. Examples for this program are related to glycemic values. Note that these glycemic values are not binding. Other numeric values (integers originating from any type of biochemical data) can also be used in different contexts.

# Software sections
The program includes the following sections:

a)	<kbd>Patient blood sugar for a period of time (days)</kbd>
Info: the main input of the program.

b)	<kbd>Processes k steps</kbd>
Info: the period of time for which the prediction is made. If the series of blood glucose levels from the input is composed of blood glucose values measured once a day, then the predictions are made on days. If, for instance, the input consists of blood glucose values measured once a week, then the predictions are made on weeks.

c)	<kbd>Step by step</kbd>
Info: this section aims to present the calculations and the current state (L or H) for each day as an animation shown at different speeds. The purpose of this section is the slow motion observation of the prediction process.

d)	<kbd>Probability values of the last vector</kbd>
Info: is a graph showing the probabilities for low or high blood sugar in the distant future. The graph shows these probabilities as bars (low in blue and high in red). The y axis represents the probability of these low or  high events and the x axis shows the number of states (bars).

e)	<kbd>Prediction of behavior</kbd>
Info: is a graph showing the day-by-day probabilities for low or high blood sugar. The y axis represents the probability of low or high glycemic events and the x axis shows the number of days for which the prediction is made.

f)	<kbd>Vector components - probability plot</kbd>
Info: Both axis represent probability values. The x coordinate of a circle from the graph is represented by the low probability value and the y coordinate of a circle is represented by the high probability value.

<kbd><img src="https://github.com/Gagniuc/Diabetes-prediction-V2.0/blob/main/screenshot/Medical%20prediction%20on%20diabetes.gif" /></kbd>


# How to use
a)	a series of blood glucose levels (data sets) from the same patient are inserted in the input text box. Preferably the measurements should be made at fixed time intervals. For instance, this set of measurements from below belongs to a single patient. The set of measurements is composed of glycemic values taken each morning for a period of 31 days. Other data sets (for specific experiments) may contain two measurements per day (or more). Another approach would be the use of data sets consisting of blood glucose measurements taken each week in an experiment of, for instance, tens of weeks.

b)	a threshold is inserted. This threshold represents the expected blood sugar level for a normal individual. In this case, 108 mg/dL has been chosen as the expected blood sugar level for a normal individual. Different situations in clinical practice (or a particular experimental setup) may require a variation of this threshold value.

<kbd><img src="https://github.com/Gagniuc/Diabetes-prediction-V2.0/blob/main/screenshot/legend%20(1).png" /></kbd>

<kbd><img src="https://github.com/Gagniuc/Diabetes-prediction-V2.0/blob/main/screenshot/legend%20(2).png" /></kbd>


# Results
The main results are presented in various forms. However, those results of major interest are shown in the middle of the window and in the lower right:

<kbd><img src="https://github.com/Gagniuc/Diabetes-prediction-V2.0/blob/main/screenshot/Medical%20prediction%20on%20diabetes.png" /></kbd>

The following sequence of blood glucose levels has been analyzed for illustration:
```
137,154,126,120,115,102,113,107,107,108,111,109,118,124,114,111,103,117,108,114,104,112,115,109,114,118,118,120,130,126,104
```
For the above sequence of blood glucose levels the software shows the results in an explicit manner, such as: <i>The threshold glucose level was set at 108 mg/dL (representing the normal level of blood sugar). Elevated levels or low levels of blood sugar are considered according to this threshold (108 mg/dL). Therefore, in the future the patient will have a LOW blood sugar (under 108 mg/dL) about 27.63% of the time, and a HIGH blood sugar (above 108 mg/dL) about 72.37% of the time. Patient's glycemic events indicate the following observations: if the patient has a high blood sugar it returns to a high blood sugar 72.73% of the time, and if it has a low blood sugar it returns to a low blood sugar level 28.57% of the time. If the patient has a HIGH blood sugar it moves to a LOW blood sugar level 27.27% of the time, and if it has a LOW blood sugar it moves to a HIGH blood sugar level 71.43% of the time.</i> Nevertheless, in the first instance the application shows a series of numbers as follows:

<kbd>H[1] = [0.272727272727 - 0.727272727273]</kbd>

<kbd>H[2] = [0.27626918536 - 0.72373081464]</kbd>

<kbd>H[3] = [0.276315184225 - 0.723684815775]</kbd>

<kbd>H[4] = [0.276315781613 - 0.723684218387]</kbd>

<kbd>H[5] = [0.276315789372 - 0.723684210628]</kbd>

<kbd>H[6] = [0.276315789472 - 0.723684210528]</kbd>

<kbd>H[7] = [0.276315789474 - 0.723684210526]</kbd>

<kbd>H[8] = [0.276315789474 - 0.723684210526]</kbd>

<kbd>H[9] = [0.276315789474 - 0.723684210526]</kbd>

Steady state vector at [9] !

<kbd><img src="https://github.com/Gagniuc/Diabetes-prediction-V2.0/blob/main/screenshot/How%20to%201.png" /></kbd>

These numbers represent predictions (in this case) of the blood sugar level each day in the future. Day 1 is the next day after the last measurement was taken. The steady state vector represents the probability for low or high blood sugar in the distant future (all times).

<kbd><img src="https://github.com/Gagniuc/Diabetes-prediction-V2.0/blob/main/screenshot/How%20to%202.png" /></kbd>

The significance of the colors on the above prediction meter is as follows: red indicates diabetes in the near future, orange indicates prediabetes in the near future, yellow indicates normal blood sugar in the near future, and light or dark green color indicates hypoglycemia in the near future.

<kbd><img src="https://github.com/Gagniuc/Diabetes-prediction-V2.0/blob/main/screenshot/info.png" /></kbd>

# References

<i>Paul A. Gagniuc. Markov chains: from theory to implementation and experimentation. Hoboken, NJ,  John Wiley & Sons, USA, 2017, ISBN: 978-1-119-38755-8.</i>
