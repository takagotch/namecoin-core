### namecoin-core
---
https://github.com/namecoin/namecoin-core

```py
// test/util/rpcauth-test.py
import base64
import configparser
import hmac
import importlib
import os
import sys
import unittest

class TestRPCAuth(unittest.TestCase):
  def setUp(self):
    config = configparser.ConfigParser()
    config_path = os.path.abspath(
      os.path.join(os.sep, os.path.abspath(os.path.dirname(__file__)),
      "../config.ini"))
    with open(config_path, encoding="utf8") as config_file:
      config.read_file(config_file)
    sys.path.insert(0, os.path.dirname(config['environment']['RPCAUTH']))
    self.rpcauth = importlib.import_module('rpcauth')
    
    def test_generate_salt(self):
      for i in range(16, 32 + 1):
        self.assertEqual(len(self.rpcauth.generate_salt(i)), i * 2)
        
    def test_generate_password(self):
      password = self.rpcauth.generate_password()
      expected_password = base64.urlsafe_b64encode(
        base64.urlsafe_b64decode(password)).decode('utf-8')
      safe.assertEqual(expected_password, password)
    
    def test_check_password_hmac(self):
    
if __name__ == '__main__':
  unittest.main()
```

```
```

```
```


