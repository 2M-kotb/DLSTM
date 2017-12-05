# DLSTM
python code to implement Deep Long-Short Term Memory
-------------------------------------------------------

There are two folders, namely:

1- case_study_1(chinese oil).

2- case_study_2(indian oil).

each folder contains two subfolders, namely:

1- DLSTM

2- ARIMA

First, DLSTM folder contains the python code used to evaluate our model, and this folder contains three files, namely:

1- oil_staic.py ---> python code used in static scenario

2- oil_dynamic.py ---> python code used in dynamic scenario

3- oil_production.csv ---> data set used

Second, ARIMA folder contains python code used to evaluate ARIMA model, and this folder contains one file, namely:

1- ARIMA.ipynb ---> notebook file 


****************************************************************************************************************************

 --------------------                    
| Required Libraries |
 --------------------

 The following libraries are needed to run the python codes:

1- pandas (0.19.2)

2- sklearn (0.18.1)

3- keras (2.0.2)

4- statsmodels (0.8.0)

5- warnings

6- itertools

7- datetime

8- numpy (1.12.1)

9- scipy (0.17.0)

10- matplotlib (1.5.1)


Note: In keras, use Theano backend
-----------------------------------

*********************************************************************************************************************

 -----------------------
| How to run DLSTM code |
 -----------------------

There are four parameters that needs to be set up ( as shown in the results tables in our paper):

1- No. of LSTM layer

2- No. of hidden units in each layer

3- No. of Epochs

4- length (number of time steps used to predict the next time step)


First, in order to set up the number of LSTM layers, go to "fit_lstm" method in the code and add the layers by using keras LSTM layer

for example, to add say two lstm layers:

model.add(LSTM()) -----> 1st layer
model.add(LSTM()) -----> 2nd layer

Note: don't add "return_squences" parameter in the last layer.


second, the remaining three parameters, go to "run" method and set them up:

 ---> look_back: is the length parameter

 ---> n_epoch: is the no, of epochs

 ---> neurons: is the no. of hidden units in each layer, it is a list [ hidden_1, hidden_2,....]


****************************************************************************************************************************

 ---------------
| One Last Note |
 ---------------

In dynamic scenario, there is an extra parameter that needs to be set up, which is :

The number of times, we refit or update the forecasting model each time step when new observation from testing data are inserted.

in the paper, we mentioned that, we don't go over three epochs.

In order to set this parameter up, we named it "updates" in "run" method.

Now, we will give the values of this parameter that used in the dynamic scenario experiments:

 ---> for case study 1 (chinese oilfield) in table 2 the values are 1,3,2 for the three entries, respectively.

 ---> for case study 2 (indian oilfield) in table 5 the values are 3,2,2 for the three entries, respectively.












