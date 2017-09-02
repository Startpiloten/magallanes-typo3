# magallanes-typo3

## Preparation:

1. Install magallanes into your composer porject:
    * `composer require andres-montanez/magallanes`
2. Add the `.mage.yml` in the project root
3. Add your data to the `.mage.yml` file (host, user etc.)

### Preperation of Server
As you can see in the `.mage.yml` the folders like `fileadmin` and `uploads` are not inside a release but symlinks because they are some kind of shared folders between the releases as they contain user-generated-content. 
Mage will release into the folder `releases` and create a symlink to the latest release called `current`. 
The folderstructure will finally look like this:

- fileadmin
- uploads
- typo3temp
- releases
  - release01
  - release02
  - release03
- current --> releases/release03 (symlink to latest release)
  - current/vendor
  - current/web
  - current/web/fileadmin --> (symlink to fileadmin in root)
  - current/web/uploads --> (symlink to uploads in root)
  - current/web/typo3temp --> (symlink to typo3temp in root)

Therefor you need to create the following folders in root (rest will be created and managed by mage):

- fileadmin 
- uploads 
- typo3temp

Configure your domain to point to `current/web/` so it will directly point to the latest release of your TYPO3 install.

## How to use

List all Magallanes configured Environments:   
`php ./mage config:environments`

Show all releases on develop server:   
`php ./mage releases:list develop`

Deploy to develop server:   
`php ./mage deploy develop`
