# CHARITY

 This repository describes Charity API

## User stories

1. As an user, I want to create a list of benefactors so that I can to save the following data:
2. As an user, I want to create a list of beneficiaries so that I can to save the following data:
3. As an user, I want to select benefactors with with some data so as to attach with the list of beneficiaries:
4. As an user, I want to look a list beneficiaries so that I could sort the list.

## Term

- A beneficiary is a natural person or other legal entity who receives money or other benefits from a benefactor.
- A benefactor is a person who gives some form of help to benefit a person, group or organization (the beneficiary).

## HTTP API

- **PUT** /api/benefactors: => 201 Return with list of benefactors
- **PUT** /api/benefactor/{benefactorID}: BODY=benefactor detail Returns 204 No Content / 400 Bad Request

>
    {
        "registrationDate": "01.09.2022",
        "name": "ICAC",
        "fullName": "International Charitable Aid Committee",
        "contact":  
        {
            "representativeName": "Someone's name",
            "url": "https://www.icac.org/en/contact",
            "phoneNumber": "+11234567890",
            "adress": "24, Some kind of street, 7890, Some region, Some country",
            "email": "info@icаc.org"
        }
    }

- **PUT** /api/beneficiaries: => 201 Return with list of beneficiaries
- **PUT** /api/beneficiary/{beneficiaryID}: BODY=beneficiary detail Returns 204 No Content / 400 Bad Request

>
    {
        "registrationDate": "03.09.2022",
        "fullName":
        {
            "firstName": "Ivan",
            "lastName": "Ivanov",
            "patronymic": "Ivanovych"
        },
        "passport":
        {
            "series": "AA",
            "number": "987654"
        },
        "RNTAC_RNOKPP": "01233456789",
        "registration":
        {
            "cuntry": "Ukraine",
            "region": "Donetsk",
            "city": "Amvrosiivka",
            "street": "Peremogu",
            "house": "7A",
            "apartment": "113"
        },
        "residence":
        {
            "cuntry": "Ukraine",
            "region": "Donetsk",
            "city": "Amvrosiivka",
            "street": "Peremogu",
            "house": "7A",
            "apartment": "113"
        },
        "family": 5,
        "children3": 1,
        "children18": 2,
        "helplist": "helplistID",
        "phoneNumber": "+41227346001"
    }

- **GET** /api/beneficiaries/{beneficiaryID or passport or RNTAC_RNOKPP or phoneNumber} -> Return 200 OK / 404 Not Found

## Models

### class Benefactor
>
    - registrationDate
    - name
    - fullName
    - contactID

### class Contact
>
    - representativeName
    - url
    - phoneNumber
    - adressID
    - email

### class Beneficiary
>
    - registrationDate
    - fullNameID
    - passportID
    - RNTAC_RNOKPP
    - registrationID
    - residenceID
    - family
    - children3
    - children18
    - helplist
    - phoneNumber

### class Adress
>
    - cuntry
    - region
    - city
    - street
    - house
    - apartment

### class FullName
>
    - firstName
    - lastName
    - patronymic

### class Passport
>
    - series
    - number
