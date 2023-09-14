# bulkemailverifier Python API

This Python client allows you to interact with the client.bulkemailverifier.com API for email verification. The client supports the following features:

1. Single email verification
2. Bulk email verification from a CSV file
3. Fetching verification results for a file

## Installation

Clone this repository to your local machine:

```bash
git clone https://github.com/BulkEmailVerifier/bulkemailverifier-py.git
```

## Usage

Import the necessary classes from the `emailverify` module:

```python
from emailverify import bulkemailverifierOne, bulkemailverifierBulk
```

### Single Email Verification

Use the `bulkemailverifierOne` class to verify a single email. You will need to provide your API key and the email you wish to verify:

```python
def verify_single_email():
    # Replace 'YOUR_KEY' with your actual API key
    # Replace 'test@email.com' with the actual email you want to verify
    bulkemailverifier_one = bulkemailverifierOne('YOUR_KEY', 'test@email.com')
    response = bulkemailverifier_one.control()
    print(response)
```

### Bulk Email Verification

Use the `bulkemailverifierBulk` class to verify a bulk of emails from a CSV file. Provide your API key and the path to the CSV file:

```python
def verify_bulk_emails():
    # Replace 'YOUR_KEY' with your actual API key
    # Replace 'path/to/file.csv' with the actual path to your CSV file
    bulkemailverifier_bulk = bulkemailverifierBulk('YOUR_KEY', 'path/to/file.csv')
    bulkemailverifier_bulk.upload()
```

### Fetching Verification Results

After a bulk upload, fetch the verification results using the `get_info()` method from the `bulkemailverifierBulk` class. This method can also be used independently by providing the ID of a previously uploaded file:

```python
def get_bulk_info():
    # Replace 'YOUR_KEY' with your actual API key
    # Replace 'FILE_ID' with the actual ID of your uploaded file
    bulkemailverifier_bulk = bulkemailverifierBulk('YOUR_KEY', 'FILE_ID')
    response = bulkemailverifier_bulk.get_info()
    print(response)
```

Finally, call these functions in your main script:

```python
if __name__ == '__main__':
    verify_single_email()
    verify_bulk_emails()
    get_bulk_info()
```

## License

This project is licensed under the terms of the MIT license.
