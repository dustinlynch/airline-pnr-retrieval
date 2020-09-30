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
* All encrypted examples of the PNR are 11 characters followed by a URL encoded "=".
* Removing the encoded `=` does break the URL, but having a regular `=` is fine.
    * `eN3Ubhvx8Js%3d` is the same as `eN3Ubhvx8Js=`
    * Encrypted string should be URL encoded before being used.
* Case **DOES** matter
    * `eN3Ubhvx8Js%3d` is not the same as `EN3Ubhvx8Js%3d`

`FLN` - Assumed to stand for **F**ull **L**ast **N**ame
* Removing the encoded `=` does break the URL, but having a regular `=` is fine.
    * `eN3Ubhvx8Js%3d` is the same as `eN3Ubhvx8Js=`
    * Encrypted string should be URL encoded before being used.
* Case **DOES** matter
    * `eN3Ubhvx8Js%3d` is not the same as `EN3Ubhvx8Js%3d`
* If a valid encryption string has been provided for the `FLN` but the reservation doesn't exist the UA page will not pre-fill the fields.

## Translated Values
Encrypted String (Length w/o =) | Unencrypted String (Length) | Parameter | Confirmed
------------ | ------------- | ------------- | -------------
`eN3Ubhvx8Js=` (11) | NQN044 (6) | CN | @DustinLynch
`EijNfVzKGjU=` (11) | NQE21F (6) | CN | @DustinLynch
`3vqu3NHsyjI=` (11) | NP2K4P (6) | CN | @DustinLynch
`VrHC15tW/Vk=` (11) | Lynch (5) | FLN | @DustinLynch
`TYAcO5IA7pw=` (11) | Smith (5) | FLN | @DustinLynch
`J5J9q4ZdqX8=` (11) | C4Y8N3 (6) | CN | @DustinLynch
`QqyNBK+3GEo=` (11) | CELEBI (6) | FLN | @DustinLynch
