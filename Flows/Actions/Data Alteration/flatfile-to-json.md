# Flat file to JSON

## Description

**Flatfile to JSON** allows parsing and conversion of CSV and fixed-width flat files to JSON format.

## Usage

**Flat file to JSON** is used to convert CSV and fixed-width flat file data into JSON output. The source data must be provided in the _Content_ field, where the column headers are defined. This can be a reference to the flat file data inline, as shown above or provided from a previous step as shown below.

*   _Delimiter_: the delimiter is one character used to split the file into columns using the selected delimiter which can be comma-separated, tab-separated or custom. A backslash escapes special characters such as /t {tabular}.
*   _Quote_: can be set to single or double quotes.
*   _Use first row as column names_: ignore or take into account the first row, it will be used for column names.

### CSV example

![Image 8: Flat file to JSON content definition](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/flat-to-json-01.png)

### Flat file example

![Image 9: Flat file to JSON content definition](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/flat-to-json-04.png)![Image 10: Flat file to JSON content definition](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/flat-to-json-05.png)

### Using content from a previous step

![Image 11: Flat file to JSON content previous step](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/flat-to-json-02.png)

### Advanced configuration: Flatpack PzMap Schema

Camel Flatpack schema can be used to define the column lengths for flat file data or define the column names for CSV & flat files, as shown in the Flatpack schema example below:

![Image 12: Flatpack schema](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/flat-to-json-03.png)

Also it can be used to define the column names for CSV data:

![Image 13: Flatpack schema](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/flat-to-json-06.png)

For more details, see the [Flatpack header and trailer records documentation](https://camel.apache.org/components/3.18.x/flatpack-component.html#_header_and_trailer_records).

For more details on using Flatpack, see the [Camel Flatpack documentation](https://camel.apache.org/components/3.18.x/flatpack-component.html#_flatpack_dataformat).
