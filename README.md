# Vehicle Project - MLOps Pipeline

Welcome to the Vehicle MLOps Project! This repository covers the end-to-end machine learning pipeline, from data ingestion to model evaluation and deployment. It incorporates best practices for working with AWS services, MongoDB Atlas, and CI/CD processes. Below is a step-by-step guide to setting up and using the project. Let’s dive into it!

## Table of Contents

1. [Project Setup](#project-setup)
2. [MongoDB Setup](#mongodb-setup)
3. [Logging, Exception Handling, and Notebooks](#logging-exception-and-notebooks)
4. [Data Ingestion](#data-ingestion)
5. [Data Validation, Transformation & Model Trainer](#data-validation-transformation--model-trainer)
6. [AWS Setup](#aws-setup)
7. [Prediction Pipeline and Model Pusher](#prediction-pipeline-and-model-pusher)
8. [CI-CD Process](#ci-cd-process)
9. [EC2 Setup](#ec2-setup)

---

## Project Setup

### Step 1: Create Project Template
- Execute the `template.py` file to create the project template.

### Step 2: Configure `setup.py` and `pyproject.toml`
- Add the code to `setup.py` and `pyproject.toml` files to import local packages.
- **Find more about "setup.py and pyproject.toml" at** `crashcourse.txt`.

### Step 3: Set up Virtual Environment
- Create and activate the virtual environment.
    ```bash
    conda create -n vehicle python=3.10 -y
    conda activate vehicle
    ```
- Install the necessary dependencies from `requirements.txt`.
    ```bash
    pip install -r requirements.txt
    ```

### Step 4: Verify Installation
- Run `pip list` to ensure local packages are installed correctly.

---

## MongoDB Setup

### Step 5: Create MongoDB Atlas Account
- Sign up for MongoDB Atlas and create a new project.

### Step 6: Create Cluster
- On the "Create a cluster" screen, select **M0 service** and hit "Create Deployment".

### Step 7: Set up Database User
- Set a username and password, then create a DB user.

### Step 8: Network Access
- Add the IP address `0.0.0.0/0` to allow connections from anywhere.

### Step 9: Get Connection String
- Go to the **Project > Get Connection String**, select **Python Driver (version 3.6 or later)**, and save the connection string (replace the password).

### Step 10: Setup Jupyter Notebook
- Create the folder `notebook` and the file `mongoDB_demo.ipynb` to work with the MongoDB connection.

### Step 11: Push Data to MongoDB
- Push the dataset to MongoDB using the notebook.

---

## Logging, Exception Handling, and Notebooks

### Step 12: Logger Implementation
- Write the logger file and test it with `demo.py`.

### Step 13: Exception Handling
- Write the exception handler and test it with `demo.py`.

### Step 14: Exploratory Data Analysis (EDA) and Feature Engineering
- Add an EDA and feature engineering notebook.

---

## Data Ingestion

### Step 15: Declare Variables
- Define necessary variables in `constants.__init__.py`.

### Step 16: Configure MongoDB Connection
- Add code to `configuration.mongo_db_connections.py` to establish a connection to MongoDB.

### Step 17: Fetch and Transform Data
- Inside `data_access`, add code in `proj1_data` to fetch data from MongoDB, transform it into a DataFrame, and add it to the respective `entity` files for ingestion.

### Step 18: Set MongoDB URL
- Set up the MongoDB connection URL in your environment variables (bash or PowerShell).

---

## Data Validation, Transformation & Model Trainer

### Step 19: Data Validation
- Complete the data validation setup in `utils.main_utils.py` and `config.schema.yaml`.

### Step 20: Data Transformation
- Implement the data transformation code in the `data_transformation` module.

### Step 21: Model Training
- Develop the model training component and add the class to `estimator.py`.

---

## AWS Setup

### Step 22: AWS IAM Setup
- Log into the AWS console and create a new IAM user `firstproj` with **AdministratorAccess**.

### Step 23: Configure AWS CLI
- Set up the AWS CLI with the newly created IAM credentials in your terminal.

### Step 24: S3 Bucket Setup
- Create an S3 bucket `my-model-mlopsproj` in the **us-east-1** region for storing models.

### Step 25: AWS S3 Storage
- Write the code in `aws_storage` to pull and push models from the S3 bucket.

---

## Prediction Pipeline and Model Pusher

### Step 26: Setup Prediction Pipeline
- Create the structure for the **Prediction Pipeline** and set up `app.py`.

### Step 27: Add Static and Template Directories
- Create the `static` and `template` directories for the web app.

---

## CI-CD Process

### Step 28: Setup Docker
- Create `Dockerfile` and `.dockerignore` to build the project container.
- Set up CI/CD pipeline with GitHub Actions.

### Step 29: Create ECR Repository
- Create an **Elastic Container Registry (ECR)** repository on AWS to store Docker images.

### Step 30: EC2 Setup
- Set up an **EC2 instance** with **Ubuntu** for hosting the app.

---

## EC2 Setup

### Step 31: Install Docker on EC2
- Follow the steps to install Docker on the EC2 instance.

### Step 32: Connect GitHub with EC2
- Connect GitHub with EC2 by setting up a self-hosted runner on GitHub and configuring the EC2 instance.

### Step 33: Activate EC2 Port
- Open port `5000` on EC2 to make the app accessible.

### Step 34: Launch the App
- Access the app by navigating to the public IP address with port `5000` in your browser.

---

## Conclusion

This project offers a complete machine learning pipeline, from setting up a virtual environment to deploying a model using AWS and EC2. By following the steps outlined in this README, you’ll gain hands-on experience with the latest cloud technologies, including AWS, Docker, and MongoDB, while applying them to build robust ML systems. 

---

Feel free to **star** the project and contribute if you find it useful! 🚀