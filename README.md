# Workshop #1: Data Engineer <img src="https://github.com/user-attachments/assets/e50b269a-fd97-4ec3-a1e9-e9629cef94ae" alt="Data Icon" width="30px"/>

Realized by **Martín García** ([@mitgar14](https://github.com/mitgar14)).

## Overview ✨

In this workshop we use randomly generated data on candidates stored in a CSV. With this data we run loading, cleaning and transformation processes to find interesting insights using the following tools:

* Python 3.12 ➜ [Download site](https://www.python.org/downloads/)
* Jupyter Notebook ➜ [VS Code tool for using notebooks](https://youtu.be/ZYat1is07VI?si=BMHUgk7XrJQksTkt)
* PostgreSQL ➜ [Download site](https://www.postgresql.org/download/)
* Power BI (Desktop version) ➜ [Download site](https://www.microsoft.com/es-es/power-platform/products/power-bi/desktop)

The libraries needed for Python are

* Pandas
* Matplotlib
* Seaborn
* SQLAlchemy
* Dotenv

These libraries are included in the Poetry project config file (*pyproject.toml*). The step-by-step installation will be described later.

## Dataset Information <img src="https://github.com/user-attachments/assets/5fa5298c-e359-4ef1-976d-b6132e8bda9a" alt="Dataset" width="30px"/>


The dataset used (*candidates.csv*) has 50,000 rows and 10 columns describing each candidate registered for the recruitment process. 
This dataset is further transformed to be better processed by the visual analysis tool.
Initially, the column names of the dataset and their respective Dtype are:

* First Name ➜ Object
* Last Name ➜ Object
* Email ➜ Object
* Country ➜ Object
* Application Date ➜ Object
* YOE (years of experience) ➜ Integer
* Seniority ➜ Object
* Technology ➜ Object
* Code Challenge Score ➜ Integer
* Technical Interview Score ➜ Integer

## Run the project <img src="https://github.com/user-attachments/assets/99bffef1-2692-4cb8-ba13-d6c8c987c6dd" alt="Running code" width="30px"/>

> Although in this case the example is done with Ubuntu using WSL, this process can be done for any operating system (OS).

### Clone the repository

Execute the following command to clone the repository:

```bash
  git clone https://github.com/mitgar14/etl-workshop-1.git
```

#### Demonstration of the process

![Git Clone](https://github.com/user-attachments/assets/0885fcdd-d4d8-4774-98bc-ac34914d9a94)


### Enviromental variables

> From now on, the steps will be done in VS Code.

To establish the connection to the database, we use a module called *connection.py*. In this Python script we call a file where our environment variables are stored, this is how we will create this file:

1. We create a directory named ***env*** inside our cloned repository.

2. There we create a file called ***.env***.

3. In that file we declare 6 enviromental variables. Remember that the variables in this case go without double quotes, i.e. the string notation (`"`):
   ```python
    PG_HOST = # host address, e.g. localhost or 127.0.0.1
    PG_PORT = # PostgreSQL port, e.g. 5432

    PG_USER = # your PostgreSQL user
    PG_PASSWORD = # your user password
    
    PG_DRIVER = postgresql+psycopg2
    PG_DATABASE = # your database name, e.g. postgres
   ```

#### Demonstration of the process

![Env Variables](https://github.com/user-attachments/assets/9e756e5e-db1a-4953-8d7c-1fa0a92d0500)


### Installing the dependencies with *Poetry*

> To install Poetry follow [this link](https://elcuaderno.notion.site/Poetry-8f7b23a0f9f340318bbba4ef36023d60?pvs=4).


1. Enter the Poetry shell with `poetry shell`.

2. Once the virtual environment is created, execute `poetry install` to install the dependencies. In some case of error with the *.lock* file, just execute `poetry lock` to fix it.

3. Now you can execute the notebooks!

#### Demonstration of the process

![Poetry](https://github.com/user-attachments/assets/3e683921-df9d-4e85-bb3f-c3761a8e3c73)


### Running the notebooks

We execute the 3 notebooks following the next order. You can run it just pressing the "Execute All" button:

   1. *001_rawDataLoad.ipynb*
   2. *002_candidatesEDA.ipynb*
   3. *003_cleanDataLoad.ipynb*

![image](https://github.com/user-attachments/assets/7599de5a-3330-4d1d-ac08-ced17639c320)
  
Remember to choose **the right Python kernel** at the time of running the notebook and **install the *ipykernel*** to support Jupyter notebooks in VS Code.

### Connecting the database with Power BI

1. Open Power BI Desktop and create a new dashboard. Select the *Get data* option - be sure you choose the "PostgreSQL Database" option.

![Power BI](https://github.com/user-attachments/assets/a53ef992-d5b9-468e-b227-94e72179a591)


2. Insert the PostgreSQL Server and Database Name.

![image](https://github.com/user-attachments/assets/ebe02754-44e8-498c-891f-e1a0038d351d)


3. Fill in the following fields with your credentials.

![image](https://github.com/user-attachments/assets/18748b7f-7d5c-4c21-891a-70e77dd21d69)


4. If you manage to connect to the database the following tables will appear:

![image](https://github.com/user-attachments/assets/2b4aa913-5fa3-4dc3-8704-1d56a4354a89)


5. Choose the candidates_hired table and start making your own visualizations!

![image](https://github.com/user-attachments/assets/4cdff11e-215f-4387-8a2f-ab383dbe436d)


## Thank you! 💕🐍

Thanks for visiting my project. Any suggestion or contribution is always welcome 👄.
