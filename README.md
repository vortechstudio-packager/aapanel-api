# AAPanel API 7.0.21 or Higher
API Client AAPanel with PHP Version min 8++

# aaPanel API PHP Client

A PHP client library for interacting with the aaPanel API.


# Features
- Fetch logs from the API.
- Add a new site.
- Update a run path site.
- Add a subdomain.
- Delete a subdomain.
- Fetch list of FTP accounts.
- Add a new FTP account.
- Delete an FTP account.
- Import SQL file into a database.
- Apply SSL certificate to a domain.
- Renew SSL certificate for a domain.
- Upload Cert SSL for a domain.
- Get SSL details for a domain and return the 'cert, key, other information' value.
- Enable HTTPS redirection for a site.
- Disable a site.
- Enable a site.


## Installation

Install the library using Composer:

```bash
composer require alfikripayakumbuh/aapanel-api
```

### Usage

Initialize the Client

```php
require_once 'vendor/autoload.php';

use AlfikriPayakumbuh\AAPanelAPI\aaPanelApiClient;

$apiKey = 'your_api_key'; // get the api key from the settings aapanel
$baseUrl = 'https://example.com:8888'; // Replace with your aaPanel API base URL
$pathCookie = './'; // want save cookie file
$client = new aaPanelApiClient($apiKey, $baseUrl, $pathCookie);
```


# Functionality
## Fetch Logs
### Fetches logs from the API.

```php
$logs = $client->fetchLogs();
var_dump($logs);
```


## Add a New Site
### Adds a new site to aaPanel.

```php
$response = $client->addSite(domain: 'example.com', path: '/home/project', runPath='/public', ssl: 1);
var_dump($response);
```

## Update a run path site
### Update a run path site domain.

```php
$response = $client->updateRunPath(id: '123', runPath='/public');
var_dump($response);
```


## Add a Subdomain
### Adds a subdomain to an existing domain.

```php
$response = $client->addSubdomain('subdomain', 'example.com', '192.168.1.1');
var_dump($response);
```


## Delete a Subdomain
### Deletes a subdomain from an existing domain.

```php
$response = $client->deleteSubdomain('subdomain', 'example.com', '192.168.1.1');
var_dump($response);
```


## Fetch FTP Accounts
### Fetches a list of FTP accounts.

```php
$ftpAccounts = $client->fetchFtpAccounts();
var_dump($ftpAccounts);
```


## Add FTP Account
### Adds a new FTP account.

```php
$response = $client->addFtpAccount('ftpuser', 'ftppassword');
var_dump($response);
```


## Delete FTP Account
### Deletes an FTP account.

```php
$response = $client->deleteFtpAccount('ftpuser');
var_dump($response);
```

## Apply SSL Certificate
### Applies an SSL certificate to a domain.

```php
$response = $client->applySslCertificate('example.com', 1, 0);
var_dump($response);
```

## Renew SSL Certificate
### Renews an SSL certificate for a domain.

```php
$response = $client->renewCert('example.com');
var_dump($response);
```

## Get Hash Domain
### Gets hash for a domain.

```php
$hash = $client->getHashValue('example.com');
var_dump($hash);
```

## Get SSL Details
### Gets SSL details for a domain.

```php
$response = $client->getSSLDetails('example.com');
var_dump($response);
```

## Upload key cert SSL
### Upload key and cert SSL certificate for a domain if available from your computer.

```php
$response = $client->uploadCert('example.com', 'key', 'cert');
var_dump($response);
```

## Enable HTTPS Redirection
### Enables HTTPS redirection for a site.

```php
$response = $client->enableHttpsRedirection('example.com');
var_dump($response);
```

## Disable Site
### Disables a site.

```php
$response = $client->disableSite(1, 'example.com');
var_dump($response);
```


## Enable Site
### Enables a site.

```php
$response = $client->enableSite(1, 'example.com');
var_dump($response);
```


## Get FTP Account Details
### Retrieves details of a specific FTP account.

```php
$details = $client->getFtpAccountDetails('ftpuser');
var_dump($details);
```


## Set Server Config
### Sets server configuration parameters.

```php
$config = [
    'param1' => 'value1',
    'param2' => 'value2'
];
$response = $client->setServerConfig($config);
var_dump($response);
```


## Get Server Config
### Gets server configuration parameters.

```php
$config = $client->getServerConfig();
var_dump($config);
```


# License
## This project is licensed under the MIT License - see the LICENSE file for details.


# MIT License
### Copyright (c) 2025 Alfikri

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
