# Phone Number Management

You can parse, format, and normalize phone numbers. The Tizen.PhonenumberUtils namespace is implemented with the libphonenumber open source library.

The main features of the Tizen.PhonenumberUtils namespace include:

-   Retrieving location information

    You can [get the location](#getting) based on the phone number, region, and language.

-   Formatting phone numbers

    You can [format the phone number string based on the region](#formatting) using the dash ("-") and space (" ") characters.

-   Normalizing phone numbers

    You can [normalize the phone number](#normalizing).

## Prerequisites

To enable your application to use the phone number management functionality, follow these steps:

1.  To use the `GetNormalizedNumber()` method of the [Tizen.PhonenumberUtils.PhonenumberUtils](/application/dotnet/api/TizenFX/latest/api/Tizen.PhonenumberUtils.PhonenumberUtils.html) class, the application has to request permission by adding the following privilege to the `tizen-manifest.xml` file:

    ```XML
    <privileges>
       <privilege>http://tizen.org/privilege/telephony</privilege>
    </privileges>
    ```

2.  To use the methods and properties of the [Tizen.PhonenumberUtils](/application/dotnet/api/TizenFX/latest/api/Tizen.PhonenumberUtils.html) namespace, include it in your application:

    ```csharp
    using Tizen.PhonenumberUtils;
    ```

<a name="getting"></a>
## Retrieve location information

To retrieve the location from a phone number, use the `GetLocationFromNumber()` method of the [Tizen.PhonenumberUtils.PhonenumberUtils](/application/dotnet/api/TizenFX/latest/api/Tizen.PhonenumberUtils.PhonenumberUtils.html) class. Provide the region of the phone number and the language of the returned location string as parameters, using the values defined in the [Tizen.PhonenumberUtils.Region](/application/dotnet/api/TizenFX/latest/api/Tizen.PhonenumberUtils.Region.html) and [Tizen.PhonenumberUtils.Language](/application/dotnet/api/TizenFX/latest/api/Tizen.PhonenumberUtils.Language.html) enumerations, respectively:

```csharp
var utils = new PhonenumberUtils();
var location = utils.GetLocationFromNumber("0222550114", Region.Korea, Language.English);
/// Method returns the location string "Seoul"
```

<a name="formatting"></a>
## Format phone numbers

To format a phone number to use region-specific separators, use the `GetFormattedNumber()` method of the [Tizen.PhonenumberUtils.PhonenumberUtils](/application/dotnet/api/TizenFX/latest/api/Tizen.PhonenumberUtils.PhonenumberUtils.html) class, which takes the region parameter as a value of the [Tizen.PhonenumberUtils.Region](/application/dotnet/api/TizenFX/latest/api/Tizen.PhonenumberUtils.Region.html) enumeration:

```csharp
var utils = new PhonenumberUtils();
var formattedNumber = utils.GetFormattedNumber("0222550114", Region.Korea);
/// Method returns the formatted number string "02-2255-0114"
```

<a name="normalizing"></a>
## Normal phone numbers

To retrieve a phone number in a normalized format, use the `GetNormalizedNumber()` method of the [Tizen.PhonenumberUtils.PhonenumberUtils](/application/dotnet/api/TizenFX/latest/api/Tizen.PhonenumberUtils.PhonenumberUtils.html) class:

```csharp
var utils = new PhonenumberUtils();
var normalizedNumber = utils.GetNormalizedNumber("0222550114");
/// Method returns the normalized number string "+821022550114"
```

## Related information
* Dependencies
  -   Tizen 4.0 and Higher
