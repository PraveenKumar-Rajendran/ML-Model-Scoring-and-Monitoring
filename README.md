### Execution Guide

#### Configuration
1. Update `config.json` with your desired settings. This file will be used across all scripts and processes.

#### Running Individual Scripts
Execute the following commands to run the individual scripts:
```sh
python ingestion.py
python training.py
python scoring.py
python deployment.py 
python diagnostics.py 
python reporting.py 
```

#### Testing Endpoints Manually
1. Start the Flask application in a separate terminal session:
    ```sh
    python app.py
    ```
2. Use the following `curl` commands in another terminal session to test the endpoints:
    ```sh
    curl 127.0.0.1:8000/
    curl 127.0.0.1:8000/prediction
    curl 127.0.0.1:8000/prediction?filename=testdata/testdata.csv
    curl 127.0.0.1:8000/scoring
    curl 127.0.0.1:8000/summarystats
    curl 127.0.0.1:8000/diagnostics
    ```

#### Automated API Calls
To make automated API calls and store the combined outputs, run:
```sh
python apicalls.py
```

#### Automated Model Scoring and Monitoring
To initiate the automated model scoring and monitoring process, run:
```sh
python fullprocess.py
```

#### Setting Up Automation with Crontab
To automate the process with `crontab`:
1. Open the crontab editor:
    ```sh
    crontab -e
    ```
2. Add the following line to schedule the script (ensure you replace with your Python path and script path):
    ```sh
    */10 * * * * /usr/bin/env python3 /path/to/fullprocess.py
    ```

Make sure to replace the Python path and `fullprocess.py` script path with the correct paths for your environment.