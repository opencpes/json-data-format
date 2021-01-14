# identity JSON format documentation

Example:

```
{
  "data_format": "STRING opencpes_identity mandatory",
  "data_format_version": "STRING 1.0 mandatory",
  "identity_guid": "STRING GUID mandatory",
  "identity_title": "STRING work/personal/company_name/etc mandatory",
  "email_current": "STRING email@address mandatory",
  "name_current": "STRING name optional",

  "email_history": [
    {
      "email": "STRING email@address mandatory",
      "valid_from": "STRING ISO8601 optional",
      "valid_to": "STRING ISO8601 optional"
    }
  ],
  "name_history": [
    {
      "name": "STRING name mandatory",
      "valid_from": "STRING ISO8601 optional",
      "valid_to": "STRING ISO8601 optional"
    }
  ]
}
```
## data_format

STRING: value is "opencpes_identity" and is mandatory

## data_format_versio

STRING: value is decimal number such as "1.0" and is mandatory

## identity_guid

STRING: value is a GUID and is mandatory

## identity_title

STRING: value is a nickname basically such as "personal" or "work" and is mandatory

## email_current

STRING: value is the users current preferred email address and is mandatory

## name_current

STRING: value is the users current preferred name and is optional

## email_history

FUTURE FEATURE

An array of previously and currently used email addresses, please note that the valid_from/valid_to may have overlaps with other records (e.g. people typically have more than one valid address at a time, with overlaps). Having entries in the array is of course optional, but if an entry exists than various parts of it are mandatory so that the record is complete.

### email

STRING: value is the users previous or alternate current email and is mandatory

### valid_from

STRING in ISO8601 format, the date from which the email address was valid for the user, if blank then assumed to be from the beginning of time thus it is optional

### valid_to

STRING in ISO8601 format, the date until which the email address was valid for the user, if blank then assumed to be currently valid thus it is optional

## name_history

FUTURE FEATURE

An array of previously and currently used names, please note that the valid_from/valid_to may have overlaps with other records (e.g. people can have more than one valid name at a time, with overlaps). Having entries in the array is of course optional, but if an entry exists than various parts of it are mandatory so that the record is complete.

### name

STRING: value is the users previous or alternate current name and is mandatory

### valid_from

STRING in ISO8601 format, the date from which the email address was valid for the user, if blank then assumed to be from the beginning of time thus it is optional

### valid_to

STRING in ISO8601 format, the date until which the email address was valid for the user, if blank then assumed to be currently valid thus it is optional
