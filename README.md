## Directory
- Application: For application-related code.
- Server
  - Hand_Sign_Classification: Code used for segmenting and classifying videos related to sign language.
  - Vietnamese_SignLanguage_Conversion: Code used for converting between sign language and Vietnamese.
- Models: For model weights.
- Others: For prompts used in converting between sign language and Vietnamese.
- Documents: For related documents.

## Running the Code
- Download weights for the sign language video classification model:
  - If gdown is not installed: `pip install gdown`
  - `cd Models`
  - `gdown 1S9OOxt39vxk_ncZg9GAhUrx8FwFALcmm`

- Download mmdeploy source:
  - `cd Server/Hand_Sign_Classification`
  - `git clone https://github.com/open-mmlab/mmdeploy.git`

- Download PhoNLP source:
  - `cd Server/Vietnamese_SignLanguage_Conversion`
  - `git clone https://github.com/VinAIResearch/PhoNLP.git`

- Run the API for sign language video classification:
  - `cd Server/Vietnamese_SignLanguage_Conversion`
  - `gunicorn fastAPI:app --bind 0.0.0.0:9091 --worker-class uvicorn.workers.UvicornWorker --timeout 300`

- Run the API for converting sign language to Vietnamese:
  - `cd Server/Vietnamese_SignLanguage_Conversion`
  - `python3 main.py`

- Run the app.