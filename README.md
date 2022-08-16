#  Google AutoML Endoscopy

The scripts in this repository can be used to parse the provided annotation files from the [Sun Dataset](http://sundatabase.org/) to create import files that will allow you to create CADe and CADx models using Google AutoML.  Please choose the script which best fits your use case described below.

# CADe Scripts

- [**generate_import_file_object_detection_binary**](https://github.com/nealmahajan/Google-AutoML-Endoscopy/blob/main/generate_import_file_object_detection_binary.ipynb)

	> Create a model which **detects** polyps within an image and returns a bounding box that frames the polyp. 
- [**generate_import_file_object_detection_multiclass**](https://github.com/nealmahajan/Google-AutoML-Endoscopy/blob/main/generate_import_file_object_detection_multiclass.ipynb)

	> Create a model that **detects** polyps within an image and returns a bounding box that frames the polyp and simultaneously **classifies** the polyp as belonging to one of the following pathology categories: hyperplastic polyp, sessile serrated lesion, adenoma, serrated adenoma, invasive carcinoma.

# CADx Scripts

Please choose the script below that fits your use case.

- [**generate_import_file_binary_polyp_classification**](https://github.com/nealmahajan/Google-AutoML-Endoscopy/blob/main/generate_import_file_binary_polyp_classification.ipynb)

	> Create a model which **classifies** an image as either having a polyp or not having a polyp. 
- [**generate_import_file_multiclass_pathology_polyp_classification**](https://github.com/nealmahajan/Google-AutoML-Endoscopy/blob/main/generate_import_file_multiclass_pathology_polyp_classification.ipynb)

	> Create a model which **classifies** an image as  not having a polyp or any of the following pathology categories: hyperplastic polyp, sessile serrated lesion, adenoma, serrated adenoma, invasive carcinoma.

# Usage
[Create and download your Google Cloud API credentials](https://cloud.google.com/docs/authentication/getting-started#setting_the_environment_variable) to your local machine. Paste the path to the credentials json in the following line of code at the end of the first block in every script.
```python
os.environ['GOOGLE_APPLICATION_CREDENTIALS']=''
```

Additionally, replace the bucket_name variable in the third code block with the name of your Google Cloud Storage Bucket. 
```python
storage_client = storage.Client()
bucket_name = 'sun-data-cloud' # replace 'sun-data-cloud' with the name of your Google storage bucket
bucket = storage_client.bucket(bucket_name)
```

## License
[CC0](https://github.com/nealmahajan/Google-AutoML-Endoscopy/blob/main/LICENSE)
