---
title: Global Administration

contributors: [nakata5321, Fingerling42]
translated: true
---

**This article will show you how to set up a new user to your Home Assistant.**

You cannot use previously created accounts because `SUB_OWNER` and `SUB_CONTROLLER` provide security, and the first user you created when you first started Home Assistant does not have a Robonomics Parachain account.

Start with creating an account on Robonomics parachain, as you did in the [previous article](/docs/sub-activate/).

Add this account to the subscription in the [dapp](https://dapp.robonomics.network/#/subscription/devices). Now there should be three addresses in the access list: `SUB_OWNER`, `SUB_CONTROLLER` and `USER`.

<robo-wiki-picture src="home-assistant/user.jpg" />

Go to the dapp service called [Home Assistant Account](https://dapp.robonomics.network/#/home-assistant). Choose the account you've just created at the right sidebar (check that you have chosen the intended account by pressing the profile icon).

Enter the `USER` seed in the required field. Add `SUB_OWNER` and `SUB_CONTROLLER` addresses in the administrator credits fields.

<robo-wiki-picture src="home-assistant/acc-pass.jpg" />

If everything is correct, you will see verification status `VERIFIED`.

Create a password for a new user which you have just registered and then confirm the transaction, that will now be without fee due to the subscription. Later you can restore the password in the Restore tab.

<robo-wiki-picture src="home-assistant/password.jpg" />

After the registration process, log in to Home Assistant with your user address as login and a newly-created password.

<robo-wiki-picture src="home-assistant/acc-login.jpg" />

Now you can use the dapp to control your home through Robonomics, check [**"Get Smart Home Telemetry"**](/docs/smart-home-telemetry/) article.