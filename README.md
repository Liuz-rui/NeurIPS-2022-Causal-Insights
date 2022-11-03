# NeurIPS-2022-Causal-Insights
This code is our solution for task2.

First of all, the file storage method is the same as that provided by the competition sponsor.

The data of task1 is stored in 'Task_1_data_private/Task_1_data_private_csv/' and the data of task2 is stored in 'Task_2_data_private/Task_2_data_private/'.<br>
NeurIPS2022/<br>
--Task_1_data_private<br>
----Task_1_data_private_csv<br>
------dataset_0\/train.csv<br>
------dataset_1\/train.csv<br>
------dataset_2\/train.csv<br>
------dataset_3\/train.csv<br>
------dataset_4\/train.csv<br>
--Task_2_data_private<br>
----Task_2_data_private<br>
------intervention_0.json<br>
------intervention_0.txt<br>
------intervention_1.json<br>
------intervention_1.txt<br>
------intervention_2.json<br>
------intervention_2.txt<br>
------intervention_3.json<br>
------intervention_3.txt<br>
------intervention_4.json<br>
------intervention_4.txt<br>
--task2_private.ipynb<br>

Our main idea is to code constructs to represent the differences among them. At the same time, in terms of specific operations, we will intercept a sequence with a length of 100 from the task1 dataset, and train the model by predicting the state of the next step. Since the definition of CATE is to calculate the difference between the two steps after applying different constructs, we use the trained model to predict twice consecutively, and then calculate the difference of the results to obtain our predicted CATE value.

The model input consists of three parts. The first part is the value of each construct in the sequence, with a total of 50 values. The second part is the ID of the imposed construct, and the last part is the value corresponding to the imposed construct.
