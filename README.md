# magallanes-typo3

## Preparation:

1. Install magallanes into your composer porject:
    * `composer require andres-montanez/magallanes`
2. Add the .mage.yml in the project root

## How to use

List all Magallanes configured Environments:   
`php ./mage config:environments`

Show all releases on develop server:   
`php ./mage releases:list develop`

Deploy to develop server:   
`php ./mage deploy develop`
