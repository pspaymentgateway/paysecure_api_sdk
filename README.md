# Paysecure API SDK

## Installation for java 21

### 1. Install SDK from the root folder
```bash
mvn install:install-file -Dfile=paysecure-sdk-1.0.jar -DgroupId=com.paysecure.sdk -DartifactId=paysecure-sdk -Dversion=1.0 -Dpackaging=jar
```

### 2. Add Dependency
Add to your project's `pom.xml`:
```xml
<dependency>
    <groupId>com.paysecure.sdk</groupId>
    <artifactId>paysecure-sdk</artifactId>
    <version>1.0</version>
</dependency>
```

### 3. Configuration
Set environment variables:
```bash
export PAYSECURE_API_BASE_URL=https://api.paysecure.com
export PAYSECURE_API_KEY=your-api-key-here
export PAYSECURE_DEBUG=true/false
```

## Usage for java
```java
public Object purchase() {
    try {
        String jsonRequest = """
                {
                    "client": {
                        "email": "prithviraj******@paysecure.co",
                        "country": "CA",
                        "city": "London",
                        "stateCode": "QLD",
                        "street_address": "******",
                        "zip_code": "*****",
                        "date_of_birth": "2004-11-04",
                        "phone": "05*****",
                        "tax_number": "+44*****",
                        "full_name": "****",
                        "network_type": "MTN",
                        "bankAccountNumber": "*******",
                        "gender": "male"
                    },
                    "purchase": {
                        "currency": "EUR",
                        "products": [
                            {
                                "name": "gaming cards",
                                "price": 1
                            }
                        ]
                    },
                    "extraParam": {
                        "IsCryptoPurchase": "no"
                    },
                    "platform": "*****",
                    "status": "",
                    "brand_id": "555c458b-*******",
                    "send_receipt": false,
                    "skip_capture": false,
                    "success_redirect": "https://mydomain.com",
                    "failure_redirect": "https://mydomain.com",
                    "success_callback": "https://mydomain.com",
                    "failure_callback": "https://mydomain.com",
                    "paymentMethod": "VISA"
                }
                """;

        ApiResponse<Object> response = PaysecureSdkApi.purchase(jsonRequest, Object.class);
        return response;
    } catch (Exception e) {
        log.error("error", e);
        return e.getMessage();
    }

}
```

