# License Generating

## License Expired
Each iApply application will have a license. Once license is expired, the system will switch to ReadOnly mode. 

User cannot save & update information in their iApply UI. Including create/update applications and create/update operations in workbench. But they can still view data. 

## How to generate license
 * Open .net project in `~\Source\Server\.Tools\LicenseGeneratorTools`
 * Replace information in `LicenseInfo.json`
   - If we want to check oranisation Id for this license
        ```json
        {
            "organisationId": "YOUR BASE ORGANISATION ID",
            "expiredDate": "EXPIRED DATE e.g. 2026-01-01",
            "orgIdCheck": true
        }
        ```
   - If we want to bypass oranisation Id check or we don't know orgId for this license
        ```json
        {
            "organisationId": "",
            "expiredDate": "EXPIRED DATE e.g. 2026-01-01",
            "orgIdCheck": false
        }
        ```
  * Run the application in Visual Studio and it will show a console App
  * Type 1 and press enter to generate the license file
  * find License.lic in `Source\Server\.Tools\LicenseGeneratorTools\LicenseGeneratorTools\bin\Debug\` folder
  * copy License.lic file to `Source\Server\iSolutions.iApply.Config`
  * If it is in your local environment, please stop & start the application in IIS for reloading the license

