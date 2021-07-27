# :back: [Validações](../../README.md#salesforce)

## Common REGEX Validation
https://help.salesforce.com/articleView?id=000334073&type=1&mode=1


## CPF
```s
OR(
    OR(
        CPFTxt__c = '00000000000',
        CPFTxt__c = '11111111111',
        CPFTxt__c = '22222222222',
        CPFTxt__c = '33333333333',
        CPFTxt__c = '44444444444',
        CPFTxt__c = '55555555555',
        CPFTxt__c = '66666666666',
        CPFTxt__c = '77777777777',
        CPFTxt__c = '88888888888',
        CPFTxt__c = '99999999999'
    ),
    AND(
        NOT(
            OR(
                LEN(CPFTxt__c) = 0,  #isso permite que o campo esteja vazio
                AND(
                    MOD(
                        MOD(11 - MOD(
                                VALUE(MID(CPFTxt__c, 1, 1)) * 10 +
                                VALUE(MID(CPFTxt__c, 2, 1)) * 9 +
                                VALUE(MID(CPFTxt__c, 3, 1)) * 8 +
                                VALUE(MID(CPFTxt__c, 5, 1)) * 7 +
                                VALUE(MID(CPFTxt__c, 6, 1)) * 6 +
                                VALUE(MID(CPFTxt__c, 7, 1)) * 5 +
                                VALUE(MID(CPFTxt__c, 9, 1)) * 4 +
                                VALUE(MID(CPFTxt__c, 10, 1)) * 3 +
                                VALUE(MID(CPFTxt__c, 11, 1)) * 2 , 11
                            ), 11
                        ), 10
                    ) = VALUE(MID(CPFTxt__c,13,1)),
                    MOD(
                        MOD(11-MOD(
                            VALUE(MID(CPFTxt__c, 1, 1)) * 11 +
                            VALUE(MID(CPFTxt__c, 2, 1)) * 10 +
                            VALUE(MID(CPFTxt__c, 3, 1)) * 9 +
                            VALUE(MID(CPFTxt__c, 5, 1)) * 8 +
                            VALUE(MID(CPFTxt__c, 6, 1)) * 7 +
                            VALUE(MID(CPFTxt__c, 7, 1)) * 6 +
                            VALUE(MID(CPFTxt__c, 9, 1)) * 5 +
                            VALUE(MID(CPFTxt__c, 10, 1)) * 4 +
                            VALUE(MID(CPFTxt__c, 11, 1)) * 3 +
                            VALUE(MID(CPFTxt__c, 13, 1)) * 2, 11
                            ), 11 
                        ), 10
                    ) = VALUE(MID(CPFTxt__c, 14, 1))
                )
            )
        ),
        NOT(
            OR(
                LEN(CPFTxt__c) = 0, #isso permite que o campo esteja vazio
                AND(
                    MOD(
                        MOD(11-MOD(
                                VALUE(MID(CPFTxt__c,1,1)) * 10 +
                                VALUE(MID(CPFTxt__c,2,1)) * 9 +
                                VALUE(MID(CPFTxt__c,3,1)) * 8 +
                                VALUE(MID(CPFTxt__c,4,1)) * 7 +
                                VALUE(MID(CPFTxt__c,5,1)) * 6 +
                                VALUE(MID(CPFTxt__c,6,1)) * 5 +
                                VALUE(MID(CPFTxt__c,7,1)) * 4 +
                                VALUE(MID(CPFTxt__c,8,1)) * 3 +
                                VALUE(MID(CPFTxt__c,9,1)) * 2, 11
                            ), 11
                        ), 10
                    ) = VALUE(MID(CPFTxt__c,10,1)),
                    MOD(
                        MOD(11-MOD(
                                VALUE(MID(CPFTxt__c,1,1)) * 11 +
                                VALUE(MID(CPFTxt__c,2,1)) * 10 +
                                VALUE(MID(CPFTxt__c,3,1)) * 9 +
                                VALUE(MID(CPFTxt__c,4,1)) * 8 +
                                VALUE(MID(CPFTxt__c,5,1)) * 7 +
                                VALUE(MID(CPFTxt__c,6,1)) * 6 +
                                VALUE(MID(CPFTxt__c,7,1)) * 5 +
                                VALUE(MID(CPFTxt__c,8,1)) * 4 +
                                VALUE(MID(CPFTxt__c,9,1)) * 3 +
                                VALUE(MID(CPFTxt__c,10,1)) * 2, 11
                            ), 11
                        ), 10
                    ) = VALUE(MID(CPFTxt__c,11,1))
                )
            )
        )
    )
)
```

## Celular (Telefone móvel)
```s
NOT(
    REGEX(MobilePhone, '^[5]{2}(1[1-9]|2[12]|24|2[78]|3[1-5]|3[78]|4[1-9]|51|5[3-5]|6[1-9]|71|7[3-5]|77|79|8[1-9]|9[1-9])9?[0-9]{8}$')
)
```

Abaixo um objeto JSON com Estados Brasileiros por DDD e lista de DDDs por Estados.
```json
{
  "estadoPorDdd": {
    "11": "SP",
    "12": "SP",
    "13": "SP",
    "14": "SP",
    "15": "SP",
    "16": "SP",
    "17": "SP",
    "18": "SP",
    "19": "SP",
    "21": "RJ",
    "22": "RJ",
    "24": "RJ",
    "27": "ES",
    "28": "ES",
    "31": "MG",
    "32": "MG",
    "33": "MG",
    "34": "MG",
    "35": "MG",
    "37": "MG",
    "38": "MG",
    "41": "PR",
    "42": "PR",
    "43": "PR",
    "44": "PR",
    "45": "PR",
    "46": "PR",
    "47": "SC",
    "48": "SC",
    "49": "SC",
    "51": "RS",
    "53": "RS",
    "54": "RS",
    "55": "RS",
    "61": "DF",
    "62": "GO",
    "63": "TO",
    "64": "GO",
    "65": "MT",
    "66": "MT",
    "67": "MS",
    "68": "AC",
    "69": "RO",
    "71": "BA",
    "73": "BA",
    "74": "BA",
    "75": "BA",
    "77": "BA",
    "79": "SE",
    "81": "PE",
    "82": "AL",
    "83": "PB",
    "84": "RN",
    "85": "CE",
    "86": "PI",
    "87": "PE",
    "88": "CE",
    "89": "PI",
    "91": "PA",
    "92": "AM",
    "93": "PA",
    "94": "PA",
    "95": "RR",
    "96": "AP",
    "97": "AM",
    "98": "MA",
    "99": "MA"
  },

  "dddsPorEstado": {
    "AC": ["68"],
    "AL": ["82"],
    "AM": ["92", "97"],
    "AP": ["96"],
    "BA": ["71", "73", "74", "75", "77"],
    "CE": ["85", "88"],
    "DF": ["61"],
    "ES": ["27", "28"],
    "GO": ["62", "64"],
    "MA": ["98", "99"],
    "MG": ["31", "32", "33", "34", "35", "37", "38"],
    "MS": ["67"],
    "MT": ["65", "66"],
    "PA": ["91", "93", "94"],
    "PB": ["83"],
    "PE": ["81", "87"],
    "PI": ["86", "89"],
    "PR": ["41", "42", "43", "44", "45", "46"],
    "RJ": ["21", "22", "24"],
    "RN": ["84"],
    "RO": ["69"],
    "RR": ["95"],
    "RS": ["51", "53", "54", "55"],
    "SC": ["47", "48", "49"],
    "SE": ["79"],
    "SP": ["11", "12", "13", "14", "15", "16", "17", "18", "19"],
    "TO": ["63"]
  }
}
```

## CEP
```s
NOT(
    REGEX(PostalCode, '^[0-9]{8}$')
)
```

## Estado (sígla)
```s
NOT(
    AND(
        LEN(State) = 2,
        # O trecho abaixo pode ser feito utilizando a função CONTAIN do próprio Salesforce.
        REGEX(State, '^[aA][cC]$|^[aA][lL]$|^[aA][pP]$|^[aA][mM]$|^[bB][aA]$|^[cC][eE]$|^[dD][fF]$|^[eE][sS]$|^[gG][oO]$|^[mM][aA]$|^[mM][tT]$|^[mM][sS]$|^[mM][gG]$|^[pP][aA]$|^[pP][bB]$|^[pP][rR]$|^[pP][eE]$|^[pP][iI]$|^[rR][jJ]$|^[rR][nN]$|^[rR][sS]$|^[rR][oO]$|^[rR][rR]$|^[sS][cC]$|^[sS][pP]$|^[sS][eE]$|^[tT][oO]$')
    )
)
```

## Data de nascimento / Maior de idade / Dias existentes / Meses existentes
```s
NOT(
    AND(
        TODAY() >= ADDMONTHS(DataNascimentoDte__c,216),
        DataNascimentoDte__c <= TODAY(),
        DAY(DataNascimentoDte__c) >= 1,
        DAY(DataNascimentoDte__c) <= 31,
        MONTH(DataNascimentoDte__c) >= 1,
        MONTH(DataNascimentoDte__c) <= 12
    )
)
```

## Email
```s
NOT(
    REGEX( 
        Email ,'^([a-zA-Z0-9_\\-\\.]+)@((\\[a-z]{1,3}\\.[a-z]{1,3}\\.[a-z]{1,3}\\.)|(([a-zA-Z0-9\\-]+\\.)+))([a-zA-Z]{2,4}|[0-9]{1,3})$'
    )
)
```