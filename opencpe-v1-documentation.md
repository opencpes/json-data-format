# opencpe JSON format documentation

Example:

```
{
  "data_format": "STRING opencpes_claim mandatory",
  "data_format_version": "STRING 1.0 mandatory",

  "opencpe_guid": "STRING GUID mandatory",
  "opencpe_createdon": "STRING ISO8601 mandatory",
  "opencpe_issuedby": "STRING email/url/name mandatory",

  "opencpe_recipient": "STRING email, optional",

  "opencpe_claimedby": "STRING email, optional",
  "opencpe_claimedon": "STRING ISO8601 optional",

  "opencpe_type": "STRING typelist mandatory",
  "opencpe_title": "STRING title mandatory",
  "opencpe_artifact_name": "STRING name of artifact optional",
  "opencpe_description": "STRING description optional",
  "opencpe_location": "STRING location optional",
  "opencpe_url": "STRING URL optional",
  "opencpe_cpe_hours": "NUMBER",
  "opencpe_valid_from": "STRING ISO8601 optional",
  "opencpe_valid_to": "STRING ISO8601 optional"
}
```

## data_format

STRING: value is "opencpes_claim" and is mandatory

## data_format_versio

STRING: value is decimal number such as "1.0" and is mandatory

## identity_guid

STRING: value is a GUID and is mandatory

## opencpe_createdon": "STRING ISO8601 mandatory",

STRING in ISO8601 format, the date and time the opencpe was created on, mandatory

## opencpe_issuedby

STRING of the issuer, can be an email, url, name and is mandatory.

longer term this may reference a separate record type, that is a FUTURE FEATURE

## opencpe_recipient

STRING an email address optional

If the CPE is created and pre-assigned to someone (e.g. a CSA Chapter meeting creates CPEs for everyone who registered and signed in for the meeting) then this field would be used to identify the recipient, and since it is email to also aid in delivery of the CPE claim to the user.

This field would be blank if someone is making a CPE claim for people to use, for example a training class where a CPE claim is shown at the end via QR code with no opencpe_recipient set, allowing anyone with the QR code to claim it.

## opencpe_claimedby

STRING email address, if the CPE is claimed in the wallet (as opposed to simply imported and not interacted with beyond that) then the user can assign the email address (referring to an identity) that is actually used to claim this. For example I may attend a CSA chapter meeting registered as kseifried@cloudsecurityalliance.org, but when I receive the CPE claim I may prefer to assign it to my personal identity kurt@seifried.org, this field is optional, but needed if the user wants to claim the CPE.

## opencpe_claimedon

STRING ISO8601, set by the client when the CPE is claimed (e.g. the opencpe_claimedby is set), this field is optional, but needed if the user wants to claim the CPE.

## opencpe_type

STRING from a list of options (to be provided here soon), it is mandatory

## opencpe_title

STRING title of the CPE claim such as "CSA Edmonton chapter meeting" and is mandatory

## opencpe_artifact_name

STRING the name of artifact if one was created, read, etc. examples would be the name of the book read or the name of the paper the user helped author, optional

## opencpe_description

STRING a text description of the CPE, strongly recommended but optional, for example if reading a book the opencpe_artifact_name would be sufficient

## opencpe_location

STRING a location such as city or address where the CPE took place, optional

## opencpe_url

STRING URL of the CPE activity or linking to information about the CPE, optional",

## opencpe_cpe_hour

NUMBER a decimal number of the amount of CPE hours being claimed

## opencpe_valid_from

STRING in ISO8601 format, the date from which the CPE was valid, if blank then assumed to be from the beginning of time thus it is optional

## opencpe_valid_to

STRING in ISO8601 format, the date until which theCPE is valid, if blank then assumed to be currently valid thus it is optional
