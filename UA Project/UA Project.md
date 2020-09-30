# United Airlines - PNR Retrieval Project
The purpose of this sub-folder/sub-project is to collect information on UA's encrypted PNR URL.

## Example URL and Structure
#### Full URL
https://www.united.com/web/en-US/apps/reservation/main.aspx?CN=eN3Ubhvx8Js%3d&FLN=eN3Ubhvx8Js%3d
#### Structure
Base URL: `https://www.united.com/web/en-US/apps/reservation/main.aspx`

Parameters: `CN=eN3Ubhvx8Js%3d&FLN=eN3Ubhvx8Js%3d`
#### Parameter Break Down 
`CN` - **C**onfirmation **N**umber 
* Confirmation numbers or PNRs are always 6 alpha-numerical characters
* All encrypted examples of the PNR are 11 alpha-numerical followed by a URL encoded "=".
* Removing the encoded `=` does break the URL, but having a regular `=` is fine.
    * `eN3Ubhvx8Js%3d` is the same as `eN3Ubhvx8Js=`
* Case **DOES** matter
    * `eN3Ubhvx8Js%3d` is not the same as `EN3Ubhvx8Js%3d`

`FLN` - Assumed to stand for **F**ull **L**ast **N**ame
* Removing the encoded `=` does break the URL, but having a regular `=` is fine.
    * `eN3Ubhvx8Js%3d` is the same as `eN3Ubhvx8Js=`
* Case **DOES** matter
    * `eN3Ubhvx8Js%3d` is not the same as `EN3Ubhvx8Js%3d`
* If a valid encryption string has been provided for the `FLN` but the reservation doesn't exist the UA page will not pre-fill the fields.

#### Examples
Encrypted String | Unencrypted String | Parameter | Confirmed 
------------ | ------------- | ------------- | -------------
`eN3Ubhvx8Js%3d` | NQN044 | CN | @DustinLynch