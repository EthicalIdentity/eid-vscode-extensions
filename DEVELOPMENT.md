## Build Instructions

* The instructions on how to build this Extension Pack can be found here: <https://code.visualstudio.com/blogs/2017/03/07/extension-pack-roundup>

1. First install Node.js and npm <https://nodejs.org/en/>

2. Install Yeoman and VS Code Extension Generator `npm install -g yo generator-code`

3. Run the Yeoman VSCode Generator `yo code`

4. Once menu pops up, scroll down using arrow keys to `>New Extension Pack` and press enter

5. Follow through the steps to generate the Extension Pack. One of the options allow you to add all your currently installed VSCode extensions to the Extension Pack. This is the easiest way to generate a brand new VSCode Extension Pack.

6. Once finished, you will have a folder with a package.json file. We will be using this file to publish the Extension Pack.

## Publish Instructions

* The instructions on how to publish an extension pack can be found here: 
<https://code.visualstudio.com/api/working-with-extensions/publishing-extension>

1. If you haven't already, install Node.js and npm <https://node.js.org/en/>

2. Install vsce, "Visual Studio Code Extensions" `npm install -g vsce`

3. We need to generate both a publisher and a Personal Access token to be able to publish an extension pack.

4. Go to <https://azure.microsoft.com/services/devops/> to create a publisher. Create an account using an email address, organization, and project that will be used and remembered by the entire organization.

5. Once logged in, click the account icon in the top right corner, and in the dropdown menu, select Security.

6. In the new section, click on "Personal access tokens", then click "New Token" on the new section that pops up.

7. Set organization to "All accessible organizations"

8. Set expiration date 1 year from today

9. Under "Scopes", click "Custom defined", then "Show all scopes". For Marketplace, check both the "Acquire" and "Manage" selections. Then click Create.

10. On the screen that comes up, a "Personal Access Token" will appear, copy it somewhere safe as the moment you close the window, the token disappears.

11. To create a publisher, open up terminal and run the following command: `vsce create-publisher (publisher name)`

12. You will need to use the "Personal Access Token" that you just made to be able to create the publisher.

13. Edit your packages.json file and add a field that follows the following convention:
`"publisher": "(publisher name)",`

14.	Login to vsce using your publisher name: `vsce login (publisher name)`

15.	Publish the extension pack: `vsce publish`

16.	A URL will be generated with your extension pack on the VSCode Marketplace. Wait a few minutes for it to propagate.