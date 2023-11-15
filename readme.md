https://github.com/abdulsamad3775/bengaluru-house-price-prediction/blob/master/website.png


# House Price Prediction Project
-----------------------------------------------------------------
This data science project series walks through the step-by-step process of building a real estate price prediction website.

## Project Overview

1. **Model Building:**
   - Build a model using `sklearn` and linear regression with the Bangalore home prices dataset from Kaggle.
   - Cover various data science concepts such as EDA, data loading and cleaning, outlier detection and removal, feature engineering, dimensionality reduction, gridsearchcv for hyperparameter tuning, and k-fold cross-validation.

2. **Components:**
   - Write a Python Flask server using the saved model to serve HTTP requests.
   - Develop a website using HTML, CSS, and JavaScript.
   - Allow users to input home details and call the Flask server to retrieve the predicted price.

3. **Technologies and Tools:**
   - Python
   - Numpy and Pandas for data cleaning
   - Matplotlib for data visualization
   - Sklearn for model building
   - Jupyter Notebook, Visual Studio Code, and PyCharm as IDE
   - Python Flask for HTTP server
   - HTML/CSS/JavaScript for UI

## Deploy to AWS EC2

Follow these steps to deploy the app to an AWS EC2 instance:

1. **Create EC2 Instance:**
   - Create an EC2 instance using the Amazon console. Add a rule in the security group to allow incoming HTTP traffic.

2. **Connect to Instance:**
   - Connect to your instance using a command like this:
     ```bash
     ssh -i "C:\Users\abdulsamad\.ssh\Banglore.pem" ubuntu@ec2-3-133-88-210.us-east-2.compute.amazonaws.com
     ```

3. **Nginx Setup:**
   - Install Nginx on the EC2 instance:
     ```bash
     sudo apt-get update
     sudo apt-get install nginx
     ```
   - Check the status of Nginx:
     ```bash
     sudo service nginx status
     ```
   - Start/stop/restart Nginx:
     ```bash
     sudo service nginx start
     sudo service nginx stop
     sudo service nginx restart
     ```

4. **Copy Code to EC2:**
   - Copy all code files to the EC2 instance using tools like WinSCP.

5. **Nginx Configuration:**
   - Create the file `/etc/nginx/sites-available/bhp.conf` with the provided content.
   - Create a symlink in `/etc/nginx/sites-enabled` and remove the symlink for the default file:
     ```bash
     sudo ln -v -s /etc/nginx/sites-available/bhp.conf
     sudo unlink default
     ```
   - Restart Nginx:
     ```bash
     sudo service nginx restart
     ```

6. **Install Python Packages and Start Flask Server:**
   ```bash
   sudo apt-get install python3-pip
   sudo pip3 install -r /home/ubuntu/BangloreHomePrices/server/requirements.txt
   python3 /home/ubuntu/BangloreHomePrices/client/server.py
   ```

7. **Load the Website:**
   - Load your cloud URL in a browser, and the website will be fully functional in a production cloud environment.

---
