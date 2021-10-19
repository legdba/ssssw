# SSSSW

This is a wrapper for Linux's `ssss` utility, automatically spliting an
combining files with Shamir's Secret Sharing Scheme shares in a safe and easy to
share way.

## Usage

Do `ssssw help` for getting help.

`ssssw split 7 5 somefile` will generate 7 files. Each contains the input file
base-64 encrypted and a Shamir's Secret Sharing Scheme share. Each file can
safely be shared/stored anywhere without risk for the encrypted data to be
compromised (it's PBKDF2 encrypted). 5 such files are needed to recover
the initial data.

`ssssw combine somefile.share01 somefile.share02 ...` will recombine 5 files into
the initial data, automatically extracting Shamir's Secret Sharing Scheme share,
recombining the AES key used for encrypting the intial data and decrypting 
that data back.

All data is base64 encoding; i.e. both binary data and email sharing are safe.


## License

This software is under Apache 2.0 license.
```
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
```
