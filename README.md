# Assign Task With SCOP

# Motivation

[SCOP](http://logopt.com/scop.htm) is the solver for constraint optimization problem.

I would like to solve the constraint optimization problem below.

Q. You assign task three works 0, 1, 2 to three workers A, B, C.The cost table of each works/workers is following.

|  | 0 | 1 | 2 |
----|----|----|----|
|A | 15 | 20 | 30 |
|B | 7 | 15 | 12 |
|C | 25 | 10 | 13 |

What is the task assignment that minimizes the total cost?

# Requirement

* Ubuntu 16.04
* Python 3.6(Anaconda virtual environment which named py36)
* [SCOP for Linux](http://logopt.com/scop.htm)

# Usage

## 1. Install SCOP

Download SCOP for Linux [here](http://logopt.com/scop/SCOPtrialVersionLinux.zip).

Extract zip and copy scop and scop.py files and paste the Python3.6 installation directory.

```:Terminal
cd /home/(Username)/anaconda3/envs/py36/lib/python3.6
sudo chmod u+x scop
```

```
sudo vi /home/(Username)/anaconda3/envs/py36/lib/python3.6/scop.py
```

```:scop.py
if platform.system()=="Windows":
    scop ="scop"
else:
    #scop = "./scop"
    scop = '/home/(Username)/anaconda3/envs/py36/lib/python3.6/scop'
```

## 2. Execute ipynb

Start jupyter notebook and open [ipynb](https://github.com/arkB/AssignTaskWithSCOP/blob/master/task_assign.ipynb) and execute it.

Output is:

```｀
Model: 
number of variables = 3  
number of constraints= 2  
variable A:['0', '1', '2'] = 0 
variable B:['0', '1', '2'] = 2 
variable C:['0', '1', '2'] = 1 
all_diff_constraint: weight= inf type=alldiff  C B A ;  :LHS =0  
linear_constraint: weight= 1 type=linear 15(A,0) 20(A,1) 30(A,2) 7(B,0) 15(B,1) 12(B,2) 25(C,0) 10(C,1) 13(C,2) <=0 :LHS =37 
```

Which means **optimized worker A's task is 0, B's task is 2, C's task is 1.**
