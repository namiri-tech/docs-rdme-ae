---
title: Item attributes
excerpt: Peruse further details of attributes filled-in in `/items` endpoint
deprecated: false
hidden: false
metadata:
  robots: index
---
## Tax categories

| Code | Name                                                   | Description                                                                                                                     | Tax Rate | Has Rate |
| ---- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- | -------- | -------- |
| O    | Services outside the scope of tax / Not subject to tax | Code specifying that taxes are not applicable to the services and/or not subject to VAT                                         | 0        | true     |
| AE   | VAT Reverse Charge                                     | Code specifying that the standard VAT rate is levied from the invoicee.                                                         | -        | false    |
| Z    | Zero-rated                                             | Code specifying that the goods and/or services are at a zero rate.                                                              | 0        | true     |
| N    | Standard rate plus additional VAT                      | Standard VAT calculated for an additional taxable base when the additional taxable base is not included in the document totals. | -        | false    |
| S    | Standard rate                                          | Code specifying the standard rate.                                                                                              | 5%       | true     |
| E    | Exempt from tax                                        | Code specifying that taxes are not applicable.                                                                                  | 0        | true     |

## Countries based on ISO 3166-1 alpha-2 codes

NB — Norwegian Bokmål: the more common written form of Norwegian

NN — Norwegian Nynorsk: the second official written form of Norwegian

| Name                                                 | Alpha2 | Name (NB)     | Name (NN)     |
| ---------------------------------------------------- | ------ | ------------- | ------------- |
| Ethiopia                                             | ET     |               |               |
| Malawi                                               | MW     |               |               |
| Rwanda                                               | RW     |               |               |
| Cocos (Keeling) Islands                              | CC     |               |               |
| Guernsey                                             | GG     |               |               |
| Honduras                                             | HN     |               |               |
| Kiribati                                             | KI     |               |               |
| Paraguay                                             | PY     |               |               |
| Singapore                                            | SG     |               |               |
| El Salvador                                          | SV     |               |               |
| Nauru                                                | NR     |               |               |
| Qatar                                                | QA     |               |               |
| Zambia                                               | ZM     |               |               |
| Brunei Darussalam                                    | BN     |               |               |
| Greenland                                            | GL     |               |               |
| Italy                                                | IT     |               |               |
| Seychelles                                           | SC     |               |               |
| Marshall Islands                                     | MH     |               |               |
| Panama                                               | PA     |               |               |
| United States of America                             | US     |               |               |
| Cyprus                                               | CY     |               |               |
| Gabon                                                | GA     |               |               |
| Romania                                              | RO     |               |               |
| New Caledonia                                        | NC     |               |               |
| Nepal                                                | NP     |               |               |
| New Zealand                                          | NZ     |               |               |
| Suriname                                             | SR     |               |               |
| Denmark                                              | DK     | Danmark       | Danmark       |
| Liechtenstein                                        | LI     |               |               |
| Palestine, State of                                  | PS     |               |               |
| China                                                | CN     |               |               |
| Micronesia, Federated States of                      | FM     |               |               |
| Lithuania                                            | LT     |               |               |
| Macedonia, the former Yugoslav Republic of           | MK     |               |               |
| Oman                                                 | OM     |               |               |
| Sudan                                                | SD     |               |               |
| Uruguay                                              | UY     |               |               |
| Bonaire, Sint Eustatius and Saba                     | BQ     |               |               |
| Iraq                                                 | IQ     |               |               |
| Uganda                                               | UG     |               |               |
| Jersey                                               | JE     |               |               |
| Malaysia                                             | MY     |               |               |
| Togo                                                 | TG     |               |               |
| Cameroon                                             | CM     |               |               |
| Grenada                                              | GD     |               |               |
| Peru                                                 | PE     |               |               |
| French Polynesia                                     | PF     |               |               |
| Aruba                                                | AW     |               |               |
| Norway                                               | NO     | Norge         | Noreg         |
| Benin                                                | BJ     |               |               |
| Cabo Verde                                           | CV     |               |               |
| Ghana                                                | GH     |               |               |
| Namibia                                              | NA     |               |               |
| Sierra Leone                                         | SL     |               |               |
| Anguilla                                             | AI     |               |               |
| Azerbaijan                                           | AZ     |               |               |
| Myanmar                                              | MM     |               |               |
| Mauritania                                           | MR     |               |               |
| Montserrat                                           | MS     |               |               |
| Norfolk Island                                       | NF     |               |               |
| French Southern Territories                          | TF     |               |               |
| Afghanistan                                          | AF     |               |               |
| Australia                                            | AU     |               |               |
| Djibouti                                             | DJ     |               |               |
| Kuwait                                               | KW     |               |               |
| Niue                                                 | NU     |               |               |
| Russian Federation                                   | RU     |               |               |
| Turkey                                               | TR     |               |               |
| American Samoa                                       | AS     |               |               |
| Belize                                               | BZ     |               |               |
| Guadeloupe                                           | GP     |               |               |
| Congo, the Democratic Republic of the                | CD     |               |               |
| Mali                                                 | ML     |               |               |
| Northern Mariana Islands                             | MP     |               |               |
| Georgia                                              | GE     |               |               |
| Martinique                                           | MQ     |               |               |
| Virgin Islands, U.S.                                 | VI     |               |               |
| Albania                                              | AL     |               |               |
| Guinea-Bissau                                        | GW     |               |               |
| South Africa                                         | ZA     |               |               |
| Bhutan                                               | BT     |               |               |
| Curaçao                                              | CW     |               |               |
| Korea, Republic of                                   | KR     |               |               |
| Germany                                              | DE     | Tyskland      | Tyskland      |
| Ireland                                              | IE     |               |               |
| Latvia                                               | LV     |               |               |
| Mongolia                                             | MN     |               |               |
| Palau                                                | PW     |               |               |
| Estonia                                              | EE     |               |               |
| Hungary                                              | HU     |               |               |
| Sri Lanka                                            | LK     |               |               |
| Moldova, Republic of                                 | MD     |               |               |
| Samoa                                                | WS     |               |               |
| Bermuda                                              | BM     |               |               |
| Bahamas                                              | BS     |               |               |
| Colombia                                             | CO     |               |               |
| Western Sahara                                       | EH     |               |               |
| Faroe Islands                                        | FO     | Færøyene      | Færøyene      |
| Mexico                                               | MX     |               |               |
| Slovenia                                             | SI     |               |               |
| Falkland Islands (Malvinas)                          | FK     |               |               |
| Malta                                                | MT     |               |               |
| Turkmenistan                                         | TM     |               |               |
| Ecuador                                              | EC     |               |               |
| Israel                                               | IL     |               |               |
| Jordan                                               | JO     |               |               |
| Kazakhstan                                           | KZ     |               |               |
| Madagascar                                           | MG     |               |               |
| Armenia                                              | AM     |               |               |
| Fiji                                                 | FJ     |               |               |
| Greece                                               | GR     |               |               |
| Nicaragua                                            | NI     |               |               |
| Saint Pierre and Miquelon                            | PM     |               |               |
| Yemen                                                | YE     |               |               |
| Réunion                                              | RE     |               |               |
| Saint Vincent and the Grenadines                     | VC     |               |               |
| Canada                                               | CA     |               |               |
| Costa Rica                                           | CR     |               |               |
| Macao                                                | MO     |               |               |
| Pitcairn                                             | PN     |               |               |
| Cook Islands                                         | CK     |               |               |
| Isle of Man                                          | IM     |               |               |
| Kyrgyzstan                                           | KG     |               |               |
| Poland                                               | PL     |               |               |
| Timor-Leste                                          | TL     |               |               |
| Dominica                                             | DM     |               |               |
| Guam                                                 | GU     |               |               |
| Lao People's Democratic Republic                     | LA     |               |               |
| Solomon Islands                                      | SB     |               |               |
| Syrian Arab Republic                                 | SY     |               |               |
| Taiwan, Province of China                            | TW     |               |               |
| Saint Lucia                                          | LC     |               |               |
| Niger                                                | NE     |               |               |
| Tuvalu                                               | TV     |               |               |
| Mayotte                                              | YT     |               |               |
| Morocco                                              | MA     |               |               |
| Montenegro                                           | ME     |               |               |
| Tonga                                                | TO     |               |               |
| Trinidad and Tobago                                  | TT     |               |               |
| Gambia                                               | GM     |               |               |
| Heard Island and McDonald Islands                    | HM     |               |               |
| Puerto Rico                                          | PR     |               |               |
| San Marino                                           | SM     |               |               |
| South Sudan                                          | SS     |               |               |
| Turks and Caicos Islands                             | TC     |               |               |
| Ukraine                                              | UA     |               |               |
| Vanuatu                                              | VU     |               |               |
| Bangladesh                                           | BD     |               |               |
| Cayman Islands                                       | KY     |               |               |
| Haiti                                                | HT     |               |               |
| Lebanon                                              | LB     |               |               |
| Barbados                                             | BB     |               |               |
| Central African Republic                             | CF     |               |               |
| French Guiana                                        | GF     |               |               |
| Andorra                                              | AD     |               |               |
| Equatorial Guinea                                    | GQ     |               |               |
| Comoros                                              | KM     |               |               |
| Belarus                                              | BY     |               |               |
| Christmas Island                                     | CX     |               |               |
| Dominican Republic                                   | DO     |               |               |
| Iran, Islamic Republic of                            | IR     |               |               |
| Pakistan                                             | PK     |               |               |
| Tanzania, United Republic of                         | TZ     |               |               |
| Venezuela, Bolivarian Republic of                    | VE     |               |               |
| Côte d'Ivoire                                        | CI     |               |               |
| Saint Kitts and Nevis                                | KN     |               |               |
| Portugal                                             | PT     |               |               |
| Sao Tome and Principe                                | ST     |               |               |
| Zimbabwe                                             | ZW     |               |               |
| Guatemala                                            | GT     |               |               |
| Serbia                                               | RS     |               |               |
| Wallis and Futuna                                    | WF     |               |               |
| Angola                                               | AO     |               |               |
| Åland Islands                                        | AX     |               |               |
| Bouvet Island                                        | BV     |               |               |
| South Georgia and the South Sandwich Islands         | GS     |               |               |
| Nigeria                                              | NG     |               |               |
| Somalia                                              | SO     |               |               |
| Tunisia                                              | TN     |               |               |
| Virgin Islands, British                              | VG     |               |               |
| Egypt                                                | EG     |               |               |
| Saint Helena, Ascension and Tristan da Cunha         | SH     |               |               |
| Viet Nam                                             | VN     |               |               |
| Switzerland                                          | CH     |               |               |
| Mozambique                                           | MZ     |               |               |
| Saudi Arabia                                         | SA     |               |               |
| Austria                                              | AT     |               |               |
| Bolivia, Plurinational State of                      | BO     |               |               |
| United Arab Emirates                                 | AE     |               |               |
| Bahrain                                              | BH     |               |               |
| Algeria                                              | DZ     |               |               |
| Argentina                                            | AR     |               |               |
| Bosnia and Herzegovina                               | BA     |               |               |
| Guinea                                               | GN     |               |               |
| India                                                | IN     |               |               |
| Swaziland                                            | SZ     |               |               |
| Saint Martin (French part)                           | MF     |               |               |
| Maldives                                             | MV     |               |               |
| Svalbard and Jan Mayen                               | SJ     |               |               |
| Tajikistan                                           | TJ     |               |               |
| United Kingdom of Great Britain and Northern Ireland | GB     | Storbritannia | Storbritannia |
| Guyana                                               | GY     |               |               |
| Tokelau                                              | TK     |               |               |
| Antigua and Barbuda                                  | AG     |               |               |
| Antarctica                                           | AQ     |               |               |
| Eritrea                                              | ER     |               |               |
| Japan                                                | JP     |               |               |
| Cambodia                                             | KH     |               |               |
| Monaco                                               | MC     |               |               |
| Mauritius                                            | MU     |               |               |
| Netherlands                                          | NL     |               |               |
| Cuba                                                 | CU     |               |               |
| British Indian Ocean Territory                       | IO     |               |               |
| Sint Maarten (Dutch part)                            | SX     |               |               |
| United States Minor Outlying Islands                 | UM     |               |               |
| Croatia                                              | HR     |               |               |
| Lesotho                                              | LS     |               |               |
| United Kingdom (Northern Ireland)                    | XI     |               |               |
| Liberia                                              | LR     |               |               |
| Libya                                                | LY     |               |               |
| Slovakia                                             | SK     |               |               |
| Czechia                                              | CZ     |               |               |
| Hong Kong                                            | HK     |               |               |
| Uzbekistan                                           | UZ     |               |               |
| Burundi                                              | BI     |               |               |
| Finland                                              | FI     |               |               |
| Kenya                                                | KE     |               |               |
| Sweden                                               | SE     | Sverige       | Sverige       |
| Chad                                                 | TD     |               |               |
| Belgium                                              | BE     |               |               |
| Saint Barthélemy                                     | BL     |               |               |
| Congo                                                | CG     |               |               |
| Korea, Democratic People's Republic of               | KP     |               |               |
| Philippines                                          | PH     |               |               |
| Brazil                                               | BR     |               |               |
| Botswana                                             | BW     |               |               |
| Indonesia                                            | ID     |               |               |
| Jamaica                                              | JM     |               |               |
| Bulgaria                                             | BG     |               |               |
| Gibraltar                                            | GI     |               |               |
| Iceland                                              | IS     | Island        | Island        |
| Senegal                                              | SN     |               |               |
| Chile                                                | CL     |               |               |
| France                                               | FR     | Frankrike     | Frankrike     |
| Luxembourg                                           | LU     |               |               |
| Papua New Guinea                                     | PG     |               |               |
| Holy See                                             | VA     |               |               |
| Kosovo                                               | 1A     |               |               |
| Burkina Faso                                         | BF     |               |               |
| Spain                                                | ES     |               |               |
| Thailand                                             | TH     |               |               |

## Currencies

| Code | Name                                                      |
| ---- | --------------------------------------------------------- |
| BTN  | Ngultrum                                                  |
| DJF  | Djibouti Franc                                            |
| GHS  | Ghana Cedi                                                |
| GNF  | Guinean Franc                                             |
| KZT  | Tenge                                                     |
| SEK  | Swedish Krona                                             |
| ZAR  | Rand                                                      |
| KES  | Kenyan Shilling                                           |
| KWD  | Kuwaiti Dinar                                             |
| OMR  | Rial Omani                                                |
| PGK  | Kina                                                      |
| SHP  | Saint Helena Pound                                        |
| UYU  | Peso Uruguayo                                             |
| CVE  | Cabo Verde Escudo                                         |
| ERN  | Nakfa                                                     |
| GBP  | Pound Sterling                                            |
| IRR  | Iranian Rial                                              |
| ISK  | Iceland Krona                                             |
| JMD  | Jamaican Dollar                                           |
| UAH  | Hryvnia                                                   |
| XBA  | Bond Markets Unit European Composite Unit (EURCO)         |
| CHE  | WIR Euro                                                  |
| CUC  | Peso Convertible                                          |
| SBD  | Solomon Islands Dollar                                    |
| SYP  | Syrian Pound                                              |
| UYW  | Unidad Previsional                                        |
| FKP  | Falkland Islands Pound                                    |
| PAB  | Balboa                                                    |
| SDG  | Sudanese Pound                                            |
| WST  | Tala                                                      |
| XAG  | Silver                                                    |
| YER  | Yemeni Rial                                               |
| LBP  | Lebanese Pound                                            |
| NOK  | Norwegian Krone                                           |
| AZN  | Azerbaijan Manat                                          |
| CLP  | Chilean Peso                                              |
| CUP  | Cuban Peso                                                |
| ETB  | Ethiopian Birr                                            |
| HKD  | Hong Kong Dollar                                          |
| MUR  | Mauritius Rupee                                           |
| MWK  | Malawi Kwacha                                             |
| NZD  | New Zealand Dollar                                        |
| GTQ  | Quetzal                                                   |
| LYD  | Libyan Dinar                                              |
| MRU  | Ouguiya                                                   |
| PEN  | Sol                                                       |
| QAR  | Qatari Rial                                               |
| SCR  | Seychelles Rupee                                          |
| UYI  | Uruguay Peso en Unidades Indexadas (URUIURUI)             |
| UZS  | Uzbekistan Sum                                            |
| BHD  | Bahraini Dinar                                            |
| BMD  | Bermudian Dollar                                          |
| COP  | Colombian Peso                                            |
| JPY  | Yen                                                       |
| RUB  | Russian Ruble                                             |
| SLE  | Sierra Leone (new valuation 2022)                         |
| SRD  | Surinam Dollar                                            |
| VUV  | Vatu                                                      |
| ALL  | Lek                                                       |
| EGP  | Egyptian Pound                                            |
| MVR  | Rufiyaa                                                   |
| XTS  | Codes specifically reserved for testing purposes          |
| BRL  | Brazilian Real                                            |
| KPW  | North Korean Won                                          |
| MAD  | Moroccan Dirham                                           |
| TMT  | Turkmenistan New Manat                                    |
| UGX  | Uganda Shilling                                           |
| VED  | Bolívar Soberano, new valuation                           |
| XCD  | East Caribbean Dollar                                     |
| AWG  | Aruban Florin                                             |
| CRC  | Costa Rican Colon                                         |
| FJD  | Fiji Dollar                                               |
| KHR  | Riel                                                      |
| XBB  | Bond Markets Unit European Monetary Unit (E.M.U.-6)       |
| XDR  | SDR (Special Drawing Right)                               |
| ZWG  | Zimbabwe Gold                                             |
| ANG  | Netherlands Antillean Guilder                             |
| GEL  | Lari                                                      |
| HUF  | Forint                                                    |
| KMF  | Comorian Franc                                            |
| LKR  | Sri Lanka Rupee                                           |
| RWF  | Rwanda Franc                                              |
| SOS  | Somali Shilling                                           |
| AED  | UAE Dirham                                                |
| HTG  | Gourde                                                    |
| NAD  | Namibia Dollar                                            |
| RSD  | Serbian Dinar                                             |
| SZL  | Lilangeni                                                 |
| USN  | US Dollar (Next day)                                      |
| VES  | Bolívar Soberano                                          |
| ARS  | Argentine Peso                                            |
| BSD  | Bahamian Dollar                                           |
| CZK  | Czech Koruna                                              |
| LSL  | Loti                                                      |
| BOB  | Boliviano                                                 |
| BOV  | Mvdol                                                     |
| MNT  | Tugrik                                                    |
| MYR  | Malaysian Ringgit                                         |
| XAU  | Gold                                                      |
| ZMW  | Zambian Kwacha                                            |
| BWP  | Pula                                                      |
| BYN  | Belarusian Ruble                                          |
| HNL  | Lempira                                                   |
| LRD  | Liberian Dollar                                           |
| XPT  | Platinum                                                  |
| PHP  | Philippine Piso                                           |
| TJS  | Somoni                                                    |
| BZD  | Belize Dollar                                             |
| MDL  | Moldovan Leu                                              |
| MXV  | Mexican Unidad de Inversion (UDI)                         |
| SGD  | Singapore Dollar                                          |
| USD  | US Dollar                                                 |
| XOF  | CFA Franc BCEAO                                           |
| AFN  | Afghani                                                   |
| CHF  | Swiss Franc                                               |
| CHW  | WIR Franc                                                 |
| DKK  | Danish Krone                                              |
| JOD  | Jordanian Dinar                                           |
| KYD  | Cayman Islands Dollar                                     |
| BBD  | Barbados Dollar                                           |
| BND  | Brunei Dollar                                             |
| COU  | Unidad de Valor Real                                      |
| STN  | Dobra                                                     |
| SVC  | El Salvador Colon                                         |
| TRY  | Turkish Lira                                              |
| XBC  | Bond Markets Unit European Unit of Account 9 (E.U.A.-9)   |
| XPF  | CFP Franc                                                 |
| EUR  | Euro                                                      |
| MOP  | Pataca                                                    |
| XUA  | ADB Unit of Account                                       |
| MMK  | Kyat                                                      |
| NGN  | Naira                                                     |
| CAD  | Canadian Dollar                                           |
| GYD  | Guyana Dollar                                             |
| ILS  | New Israeli Sheqel                                        |
| KGS  | Som                                                       |
| MXN  | Mexican Peso                                              |
| MZN  | Mozambique Metical                                        |
| NIO  | Cordoba Oro                                               |
| TTD  | Trinidad and Tobago Dollar                                |
| BAM  | Convertible Mark                                          |
| BDT  | Taka                                                      |
| LAK  | Lao Kip                                                   |
| MGA  | Malagasy Ariary                                           |
| PKR  | Pakistan Rupee                                            |
| PLN  | Zloty                                                     |
| SSP  | South Sudanese Pound                                      |
| GIP  | Gibraltar Pound                                           |
| PYG  | Guarani                                                   |
| XPD  | Palladium                                                 |
| AUD  | Australian Dollar                                         |
| BGN  | Bulgarian Lev                                             |
| BIF  | Burundi Franc                                             |
| CDF  | Congolese Franc                                           |
| CNY  | Yuan Renminbi                                             |
| DZD  | Algerian Dinar                                            |
| IDR  | Rupiah                                                    |
| INR  | Indian Rupee                                              |
| AOA  | Kwanza                                                    |
| IQD  | Iraqi Dinar                                               |
| RON  | Romanian Leu                                              |
| TOP  | Pa'anga                                                   |
| TWD  | New Taiwan Dollar                                         |
| TZS  | Tanzanian Shilling                                        |
| XAF  | CFA Franc BEAC                                            |
| XBD  | Bond Markets Unit European Unit of Account 17 (E.U.A.-17) |
| DOP  | Dominican Peso                                            |
| KRW  | Won                                                       |
| SAR  | Saudi Riyal                                               |
| VND  | Dong                                                      |
| XSU  | Sucre                                                     |
| AMD  | Armenian Dram                                             |
| CLF  | Unidad de Fomento                                         |
| TND  | Tunisian Dinar                                            |
| GMD  | Dalasi                                                    |
| MKD  | Denar                                                     |
| NPR  | Nepalese Rupee                                            |
| THB  | Baht                                                      |

## Commodity types

| Code | Name     |
| ---- | -------- |
| G    | Goods    |
| S    | Services |
| B    | Both     |