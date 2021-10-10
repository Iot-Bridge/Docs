# Things Stack Credentials

These are api keys allowing IotBridge to fetch/insert/update resources from your account on The Things Stack network.

Credentials can be found by navigating to the manage account page. Select the 'Manage Account' button on the account dropdown, which can be found by clicking your name on the top right.

![Account Drop Down](/images/AccountDropDown.jpg)

You can then select 'Things Stack' from the menu on the left

![Manage Account](/images/ManageAccount.jpg)

## Setting up Api Access on Things Stack

In a new tab, navigate to https://eu1.cloud.thethings.network/console (based on your Things Stack region) and login with your personal credentials.

![Things Stack Login](/images/ThingsStackLogin.jpg)

After logging in, click on the 'Organizations' menu item at the top of the page

![Things Stack Landing](/images/ThingsStackHome.jpg)

Select the organization you would like to add an api key for. Please keep the Id of the organization on hand to configure on IotBridge.

![Things Stack Organizations](/images/ThingsStackOrganizations.jpg)

On the menu on the left, select 'Api keys'

![Things Stack Organization](/images/ThingsStackOrganization.jpg)

On the top right of the page, click the 'Add API key' button

![Things Stack Api Keys](/images/ThingsStackApiKeys.jpg)

You will then land on the API key creation page

![Things Stack Api Key Creation](/images/ThingsStackAddApiKey.jpg)

#### Name field

You will need to provide a user friendly name for your api key.

#### Rights field

Select the appropriate access for this api key by clicking on the necessary items in the list.

Once created, a popup will appear showing you your api key, copy this value somewhere and keep it on hand to configure on IotBridge.

![Things Stack Api Key Popup](/images/ThingsStackApiKeyPopUp.jpg)

After you have dismissed the popup you will see your newly created api key. You will need the 'Key ID' as well to configure on IotBridge.

## Adding Credentials

After selecting Things Stack from the credential menu on the left, you can now click the 'Add a things stack organization' button on the top right of the page

![Things Stack List](/images/ThingsStackLanding.jpg)

Once clicked a fly-out will appear

![Things Stack Add](/images/AddThingsStack.jpg)

#### Organization Id field

You will need to provide the id of the organization that you would like to access on Things stack network.

#### Key Id field

You will need to provide a key id for your api that you would've setup on Things stack network.

#### Key Secret field

You will need to provide the api key for your api that you would've setup on Things stack network.