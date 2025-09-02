- Where to collect data
	- Kaggle
	- UCI Machine learning repository
	- Google Dataset Search
- API- allows two applications to communicate with each other
- import data from kraggle
```py
#upload kraggle json.file

!mkdir -p ~/.kaggle
!cp kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json

# unzip the main file

from zipfile import ZipFile
dataset='/content/LANL-Earthquake-Prediction.zip'
with ZipFile(dataset,'r') as zip:
  zip.extractall()
  print('The dataset is extracted')
```
