# Translate a book with Google Cloud Translate API 
## Overview:

This script takes a text file input and by a specified delimiter (ex: ‘.’ and ‘\n’) sends the text to Google Cloud Translate API, stores translated text in memory and after the text file has been completed assembles the translated text file into an output file.

[Tqdm](https://pypi.python.org/pypi/tqdm) is used to display the progress of the translation job.

Before attempting this aware of the following:
- [5000 characters per request limit for the Translate API](https://cloud.google.com/translate/faq)
- [Service quotas per user/day for Translate API within Google Cloud Platform quotas](https://cloud.google.com/translate/quotas)

## Requirements:

- Python3
- Google Cloud pip package
- Google Cloud Platform [Service Account](https://cloud.google.com/iam/docs/creating-managing-service-account-keys) key in json
- Input file must be in .txt, so if your source is in pdf you'll need to convert

## Configure your environment:

Download [service account credentials](https://console.cloud.google.com/apis/credentials?project=_) and rename project-name-xxxxxx.json file to creds.json in same folder as translate-client.py.

`sudo python -m pip install google-cloud --ignore-installed`

[Language Codes](https://cloud.google.com/translate/docs/languages)

## To run:
`python3 translate-client.py input.txt output.txt`

```
$ python3 translate-client.py book.txt book-translated-2.txt
Input Text Loop: |####------| 415/1029  40% [elapsed: 08:09 left: 12:04,  0.85 iters/sec]
```


Special thanks to [Ashish](https://github.com/AshuIX) for assisting with the code.
