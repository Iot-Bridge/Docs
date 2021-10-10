# Sigfox Credentials

These are api keys allowing IotBridge to fetch/insert/update resources from your account on Sigfox Backend.

Credentials can be found by navigating to the manage account page. Select the 'Manage Account' button on the account dropdown, which can be found by clicking your name on the top right.

![Account Drop Down](/images/AccountDropDown.jpg)

You can then select 'Sigfox' from the menu on the left

![Manage Account](/images/ManageAccount.jpg)

## Setting up a Api Access on Sigfox

In a new tab, navigate to https://backend.sigfox.com/auth/login and login with your personal credentials.

![Sigfox Backend Login](/images/SigfoxBackendLogin.jpg)

After logging in, click on the 'Group' menu item

![Sigfox Backend Landing](/images/SigfoxBackendLanding.jpg)

Select the group you would like to add a login for

![Sigfox Backend Groups](/images/SigfoxBackendGroups.jpg)

On the menu on the left, select 'Api Access'

![Sigfox Backend Group](/images/SigfoxBackendGroup.jpg)

On the top right of the page, click the 'New' button

![Sigfox Backend Api Access](/images/SigfoxBackendApiAccess.jpg)

You will then land on the Api Access creation page

![Sigfox Backend Api Access Create](/images/SigfoxBackendAddApiKey.jpg)

#### Name field

You will need to provide a user friendly name for your login.

#### Timezone field

You can either select a specific timezone or leave the default.

#### Profiles field

Select the appropriate access for this login by clicking on the necessary items in the list.

Once created you will see the 'Login' and 'Password' values, keep these on hand to configure on IotBridge.

## Adding Credentials

After selecting Sigfox from the credential menu on the left, you can now click the 'Add a Sigfox group' button on the top right of the page

![Sigfox List](/images/SigfoxLanding.jpg)

Once clicked a fly-out will appear

![Sigfox Create](/images/AddSigfox.jpg) 

#### Login field

You will need to provide the login for the api that you created on Sigfox Backend.

#### Password field

You will need to provide the password for the api that you created on Sigfox Backend.

> Note: The Login and Password fields are not your personal credentials that you use to login to the Sigfox Backend