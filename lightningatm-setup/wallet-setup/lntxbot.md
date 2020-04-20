---
description: >-
  This part of the guide will show you how to setup Lntxbot, a Biitcoin
  Lightning Wallet in your Telegram messenger on your mobile phone.
---

# Lntxbot

## A word of caution

{% hint style="warning" %}
The Lightning Wallet is a "Custodial Bitcoin Wallet". This means, you are trusting those who run the software behind this wallet with Satoshis. Be careful and don't keep too many Satoshis on there.
{% endhint %}

## Updating your current installation

Before you continue, make sure you are on the latest version of the ATM software. For this we go into the `LightningATM` folder and execute one git command:

```text
cd ~/LightningATM
git pull
```

You should now hace the latest changes and therefore the laste version of the LightningATM software on your Raspberry Pi.

## Installing Lntxbot

Install the mobile application "Telegram" on your phone and after you have created your account, go into the search bar and type `Lntxbot`

![Searching Lntxbot](../../.gitbook/assets/searching_lntxbot.jpg)

You should now be able to talk to the Lntxbot. If you type `/help` you will get a list of commands that are available.

![Hello Lntxbot](../../.gitbook/assets/hello_lntxbot.jpg)

You can inspect all the different commands that are available for you on this mobile Lightning Wallet.

![Commands Lntxbot](../../.gitbook/assets/commands_lntxbot.jpg)

## Funding the Lntxbot

In order for this Lightning Wallet to work with our ATM, we need to fund it and have some Satoshis on there. Type `/invoice <amount>` into the message box and replace `<amount>` by a certain amount of Satoshis you want to fund it with.

Now, you will have to pay this invoice with another wallet in order for your Lntxbot to receive them and later be available at your ATM.

After you payed this invoice check your balance with `/balance` to make sure it all worked out.

## Connecting the Lntxbot to the ATM

We will now connect the Lntxbot to your ATM. For this we access our ATM again through SSH, change into the `LightningATM` directory and start the software with:

```text
cd ~/LightningATM
./app
```

This will again start the ATM software and we get to see `Welcome to the LightningATM` on our screen.

Next, we will generate a QR code with our Lntxbot credentials inside out bot in Telegram. Go the message box in Lntxbot and type `/lightningatm`. This will generate a QR code with the credentials that we need.

We'll now have to put our ATM into the "credentials scanning" mode. This can be done by pushing the button 3 times.

After you pushed the button three times your display should say `Please scan your wallet credentials`. Now take your mobile phone with the Lntxbot and show the previously generated QR code with your credentials to the camera.

It will now scan your credentials and safe it to the configuration of the ATM. I've you've been successful, your screen will say `Successful` and show you the current balance of your Lntxbot.