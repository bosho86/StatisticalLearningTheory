# Statistical Learning Theory: Coding Exercises

## Getting Started

### Cloning the repo

To clone the repository, you need to setup the [deploy key](slt2020) first. Make sure your file has a name `slt2020` without any extension. 

Copy the deploy-key to your `~/.ssh/` folder.
    
Sometimes, you need to explicitly add an entry in the `~/.ssh/config`:

```
    Host gitlab.ethz.ch
        IdentityFile ~/.ssh/slt2020
        IdentitiesOnly yes
```

Moreover, if you get permission errors, you should reset the permissions:

```
    chmod 640 ~/.ssh/config
    chmod 400 ~/.ssh/slt2020
```

Finally, clone the repository via ssh (not https!):

```
    git clone git@gitlab.ethz.ch:ccarlos/slt-coding-exercises-20.git
    cd slt-coding-exercises-20
```

### Creating the environment

Create the [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html) environment, which contains the basic packages:

```
    conda env create -n slt-ce -f environment.yml
```

Activate the environment, and start the notebook:

```
    source activate slt-ce
    jupyter notebook slt-ce-0.ipynb
```
A new browser window with the first exercise should open.

## Complete and submit an exercise

To get the latest exercise, simply pull from the remote repo:

```
    cd slt-coding-exercises-20
    git checkout master
    git pull origin master
```

Before you start working on an exercise, you should create a new branch:

```
    git checkout -b <your-gitlab-username>/slt-ce-0
```
    
The name of the branch should be your-gitlab-username/slt-ce-i, where i denotes the respective exercise. For example, in my case (gitlab username: ccarlos), it would be

```
    git checkout -b ccarlos/slt-ce-0
```

The instructions for each exercise can be found directly in the notebook.

Once you are done, `put your legi somewhere clearly at the beginning of the notebook.`

Then encrypt your notebook:

```
    ./encrypt.sh slt-ce-0.ipynb
    > File encrypted as slt-ce-0.ipynb.encr
```

Then commit and push the encrypted notebook:

```
    git add slt-ce-0.ipynb.encr
    git commit slt-ce-0.ipynb.encr -m "Submit slt-ce-0"
    git push origin <your-gitlab-username>/slt-ce-0
```

`You can only submit your notebook before the respective deadline.`

`We accept submissions only via git as described above.`

`Be aware that all information you push, including the name you give to github and the email you give, will be visible to your colleagues. For this reason, do not push notebooks which are not encrypted and do not use your real name and email address if you do not want them to be visible to your colleagues.`

`Do not push notebooks which are not encrypted.`


## Exercise grading

We offer 7 exercises. Each submitted exercise is graded between 4 and 6.

For admission to the written exam, you need to receive a grade of 4 in at least **four** exercises.

The exercise grade is computed as the average of your best four submissions.

The course grade is the weighted average of written exam and exercise (70%/30%). 

### Example 1

Exercise grades: 5.5, 5.0, 6.0, -, -, -, -

Failed course, submitted only three exercises!

### Example 2

Exercise grades: 5.0, 5.0, 4.0, 6.0, 6.0, -, -

Exercise grade = (5.0 + 5.0 + 6.0 + 6.0) / 4 = 5.5

Exam grade = 5.0

Course grade = round(0.3 * 5.5 + 0.7 * 5.0) = 5.25


## Exercise deadlines

Hand-Ins are due by **noon** of the respective hand-in day, and the hand-in period typically starts one week earlier.

`Exercises can not be handed in after the deadline, because the server is blocked!`

|   | Exercise                 | Release   |  Hand-In          | 
|---|--------------------------|-----------|-------------------|
| 1 | Sampling                 | Mar 2nd   | Mar 16th 11:59am  |
| 2 | Deterministic Annealing  | Mar 16th  | Mar 30th 11:59am  |
| 3 | Histogram Clustering     | Mar 30th  | Apr 13th 11:59am  |
| 4 | Constant Shift Embedding | Apr 20th  | May 4th  11:59am  |
| 5 | Pairwise Clustering      | May 4th   | May 18th 11:59am  |
| 6 | Mean Field approximation | May 18th  | Jun 1st  11:59am  |
| 7 | Validation               | Jun 1st   | Jun 15th 11:59am  |

