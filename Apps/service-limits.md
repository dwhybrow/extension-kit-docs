This section lists the recommended service limits for App Studio based on practical, real-world testing using a PC with the following specifications:

-   Operating system Windows 10 Enterprise, version 21H2, OSbuild 19044.2604
-   Processor: Intel(R) Core(TM) i7-8650U @ 1.90GHz 2.11GHz
-   Installed RAM: 16.0 GB (15.9 GB usable)

## Functional limits

The following table describes the functional limits.

|Limit|Details|
|---|---|
|Number of complex components (Select, Grid) in an App|Select: 100
Grid non-editable: 10|
|Number of simple components (Text input, Text, Checkbox, Switch etc.)|500|
|Number of grid rows|200000 with 6 columns|
|Number of grid columns|30|
|Number of tabs in a tab panel|10|
|Number of steps in a wizard|7|
|Number of HTTP requests|25|
|Size of the content definition|1000000|
|Size of the schema|Not defined|
|Number of actions in launch event (run in parallel)|25|
|Number of nodes in Logic flow|50|
|Number of components with Logic flow|10|
|Number of actions in a click event (run in parallel)|25|
|Max number of buttons in the footer|10|
|Max number of characters in Expand property|2000|

## Technical limits

The following table describes the technical limits.

|Limit|Details|
|---|---|
|Maximum size of Base64 images|500kb|
|Number of options in a Select component|10000|
|Number of options in a Typeahead component|10000|
|Number of HTTP requests|25|
|Number of headers in a resource|10|
|Max size of a plain object|25000 characters|
|Max size of content definition|1000000|
|Max size of schema|Not defined|
|Number of action nodes in Logic flow|50|
|Number of actions in a click event (run in parallel)|25|
|Metadata max size|2MB|
|App/bundle size|5MB|
