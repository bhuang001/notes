FastText
===========

* Download binary files from https://fasttext.cc/docs/en/crawl-vectors.html
* Load FastText binary model

```python
from gensim.models import FastText
bin_path = "Your_Path/cc.en.300.bin"

model = FastText.load_fasttext_format(bin_path)
```

* Dump the model object
```python
# directly use pickle to dump the model object encountered OS error
import pickle
import os.path
file_path = "fastText_model_file.pkl"
max_bytes = 2**31 - 1

## write
bytes_out = pickle.dumps(model)
with open(file_path, 'wb') as f:
    for idx in range(0, len(bytes_out), max_bytes):
        f.write(bytes_out[idx:idx+max_bytes])
# running time is < 1min
```
* load the model object
```python
bytes_in = bytearray(0)
input_size = os.path.getsize(file_path)
with open(file_path, 'rb') as f_in:
    for _ in range(0, input_size, max_bytes):
        bytes_in += f_in.read(max_bytes)
model1 = pickle.loads(bytes_in)
# running time is < 1min
```

* check whether write & read procedure is equivalent to dump & load procedure (use model as a dict)
```python
print(model['new york'])
print(model1['new york']) 
```
