# False-Alarm-Cases
Flask Application Setup: The system is implemented using Flask, a lightweight web framework for Python, allowing for easy deployment and integration with web services.

Training Model: The system provides an endpoint /train_model to train the logistic regression model using data from an Excel file named "False Alarm Cases.xlsx". The model is trained to predict the spuriousness index (0 or 1) based on various features.

Model Persistence: After training, the model is saved using joblib's dump function into a pickle file named "train.pkl" for future use.

Testing Model: The system offers an endpoint /test_model to test the trained model. Test data in JSON format is sent via POST method containing features like Ambient Temperature, Calibration, Unwanted substance deposition, Humidity, H2S Content, and the detector used for detection.

Prediction: The model loaded from the pickle file predicts whether the given test data indicates a false alarm or not. If the prediction is 1, it indicates a false alarm with the message "False Alarm, No Danger"; otherwise, it indicates a true alarm with the message "True Alarm, Danger".

Error Handling: The system handles errors gracefully, responding with appropriate messages in case of any issues during training or testing.

Deployment: The Flask application is run on port 5000, making it accessible for testing and integration with other systems.





