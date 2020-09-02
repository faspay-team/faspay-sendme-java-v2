[![N|Solid](https://faspay.co.id/docs/sendme/images/sendMe-new.png)](https://faspay.co.id/docs/index-sendme.html#faspay-sendme) 
## Welcome To Faspay SendMe

This package provides Faspay SendMe 1.1 support for the JAVA Language.

## Requirements

The following versions of JAVA JDK are supported.

* JDK 1.8

To use this package, it will be necessary to have a credential. These are referred to as 
* virtual_account
* faspay_key
* faspay_secret
* app_key
* app_secret
* client_key
* client_secret
* iv

Added new file SendmeConfig.properties (get file from dir "src") to root directory project for setting host and credential or 
Existing in the SendMe.CredentialData.Credential.class. 

Credential will sent to your email from faspay.
Please contact Administrator Faspay to create the required credentials.

## Installation

To install:

Import SendMeLib.jar to use the functions, sample use netbeans

```sh
1. right click on java project -> Library
2. Add JAR/Folder
3. browse SendMeLib.jar
4. finish
```

Import 2 libraries for Java, to use JSON

```sh
1. right click on java project -> Library
2. Add JAR/Folder
3. browse commons-lang3-3.8.1.jar & json.jar
4. finish
```

## Usage

### Register Flow

First Step
Import SendMeAPI.jar Class Library And HashMap Class Library
Ex:
```java
    import SendMe.Services;
	import org.json.JSONObject;
	import java.util.HashMap;
```

Second Step
```java
	Services serv = new Services();
	
	HashMap<String, String> array = new HashMap<String, String>();
	array.put("virtual_account", "9920017573");
	array.put("beneficiary_account", "10200061379");
	array.put("beneficiary_account_name", "Faspay Dev 5");
	array.put("beneficiary_va_name", "Faspay Dev 5");
	array.put("beneficiary_bank_code", "008");
	array.put("beneficiary_bank_branch", "CIMB Pusat");
	array.put("beneficiary_region_code", "0102");
	array.put("beneficiary_country_code", "ID");
	array.put("beneficiary_purpose_code", "1");
	
	
	String rsp = serv.Register(array);
```

### Balance Inquiry

First Step
Import SendMeAPI.jar Class Library And HashMap Class Library
Ex:
```java
    import SendMe.Services;
	import org.json.JSONObject;
	import java.util.HashMap;
```

Second Step
```java
	HashMap<String, String> array = new HashMap<String, String>();
	array.put("virtual_account", "9920017573");
	String rsp = serv.BalanceInquiry(array);
```
the parameter refer to Faspay SendMe [Documentation](https://faspay.co.id/docs/index-en-sendme.html#faspay-sendme).

### Environment Production
To use environment production must be call this method like as :

```java
Services serv = new Services();
serv.toProduction();
```

#### Available Methods

The `Faspay SendMe` provide has the following [method]:

- 'Register()' to use register your customer bank account
- 'RegisterConfirm()' to use confirm your customer bank account after register method
- 'Transfer()' to use transfer balance to customer bank account registered
- 'BalanceInquiry()' to use check your balance 
- 'InquiryName()' to use check your customer bank account detail
- 'Mutasi()' to use get your transaction history
- 'InquiryStatus()' to use check the latest status transfer

## FAQ

#### 1. If you get error "Java Security: Illegal key size or default parameters"

please refer to : 
- https://stackoverflow.com/questions/6481627/java-security-illegal-key-size-or-default-parameters/23255246
- https://github.com/EliteAndroidApps/WhatsApp-Crypt12-Decrypter/issues/3
