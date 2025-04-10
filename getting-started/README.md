---
description: Code4rena registration and account management
---

# Account setup and management

To register, follow these steps:

1. Go to [code4rena.com/register](https://code4rena.com/register/account).
2. Fill in your information. You can choose to connect a web3 wallet for authorization or use only a username and password.
   * Note: You can update any of your details at any time after signup, **except for your username.**
3. **Wardens:** Provide your Polygon wallet payment address for audit rewards.

## Account setup process

After registration, complete the following steps to set up your account:

1. You'll be directed to [code4rena.com/account](https://code4rena.com/account) for verification.
2. Discord verification is required:
   * Click 'Join Discord Server' to join the Code4rena Discord server.
   * Click 'Verify Discord' to confirm your membership and verify your account.
3. Email verification is also necessary:
   * Check your inbox for an email from noreply@code4rena.com.
   * Click the verification link to confirm your email address.
4. Once both verifications are complete, your account setup will finalize, granting you access to Code4rena's platform!

## Warden teams

### Registering a team

To register a team, you must first login to your Warden account, and then register your team [here](https://code4rena.com/register/team/).

Once a team is created, you have the ability to add/remove members and update your payment address while logged in to the Code4rena website.

All team registrations and updates will create pull requests that are flagged for the C4 team to review and approve. Please allow 24-48 business hours for processing.

❗️**Important note: Team awards are sent as a single payment to _one_ wallet.** We strongly recommend using a multisig wallet, or a tool like [PaymentSplitter](https://docs.openzeppelin.com/contracts/4.x/api/finance#PaymentSplitter), to distribute awards among your team members. Note that C4 does not track which team member submitted each finding; your team is responsible for keeping track of that information, and distributing awards. The team structure at C4 is designed so that you submit as a team and get paid as a team.

### Participating as a team 
Once individual team members are authenticated, and your team has been registered, each team member will be able to submit findings as either an individual participant, or on behalf of the team. These options are shown on the submission form.

***

## FAQ / troubleshooting

### Can't find email verification message

If you can't find the email verification message:

1. Log in and go to [code4rena.com/account](https://code4rena.com/account).
2. Navigate to the 'Account Verification' section and select 'Re-send Email'.
3. Check your inbox for the new email and click the link to confirm your email address.

### Discord verification

If you can't see most channels in the Code4rena Discord server, your Discord verification may be incomplete. The `warden` role in Discord is automatically assigned when the verification process is successfully completed. To troubleshoot:

1. **Check** [**discord.com**](https://discord.com) **in your web browser.** You may be logged into a different Discord account in your web browser, and if so, that Discord account has received the warden role instead.
2. Log out of Discord.
3. **Perform the Discord verification again:** Log into the account you want associated with your C4 user account, in the same browser you are using to interact with code4rena.com. Next, head to your account settings and perform the Discord verification again.

### Github verification (optional)

Certified and SR wardens should verify their Github accounts in order to access private repos.

**Note:** Ensure that you are logged in to the correct GitHub account before starting the verification process.

To verify your GitHub account on Code4rena, follow these steps:

1. Log in to your Code4rena account.
2. Go to the [**Account Settings**](https://code4rena.com/account) page.
3. Look for the section labeled **User Information**.
4. Check if your GitHub account is verified.
5. If not verified, click the **Verify** link next to "Please verify your GitHub account."
6. You will be redirected to GitHub for authorization.
7. On the GitHub authorization page, click **Authorize**.
8. You will be redirected back to Code4rena, and you should see "✓ GitHub verified" if successful.

Your GitHub account is now successfully linked and verified on Code4rena!

### Wallet connect issues

If you encounter issues with wallet connection:

* Ensure your wallet is unlocked and connected to your device/browser.
* Make sure the Polygon network is selected in your wallet settings.

### Forgot password

To reset your password:

1. Go to [code4rena.com/login](https://code4rena.com/login) and select "Forgot Password".
2. Enter your email address and click 'Reset Password'.
3. Check your email for a link to reset your password.

### Change email address

To update your email address:

1. Go to [code4rena.com/account](https://code4rena.com/account) and locate the 'Email Address' field.
2. Click 'Edit' and enter your new email address.
3. Follow the email instructions to confirm your new email address.

### Add/remove web3 wallets for authorization

To manage your web3 wallets for login authorization:

1. Visit [code4rena.com/account](https://code4rena.com/account) and find 'Login Addresses'.
2. To remove a login address:
   * Locate it in the table and select "Remove".
   * Follow the onscreen instructions to confirm removal.
3. To add a new wallet for authorization:
   * Select "Link New Address".
   * Follow the prompts to connect your wallet and sign a message.

### Edit payment address

To edit your payment address:

1. Audits typically pay rewards on the Polygon network.
2. Your payment address can differ from your login authentication address.
3. Go to [code4rena.com/account](https://code4rena.com/account) and find 'Payment Information'.
4. Click 'Edit' and enter your desired payment address. Note: for each contest, C4 distributes awards to the payment address on file _at the time of award calculation_.

### Tax reporting information

As a US-based entity, Code4rena is legally bound to comply with US tax law and OFAC sanctions. Therefore we collect tax information prior to distributing all award payments.

You can [complete your tax information here](https://code4rena.com/tax-info) or update it anytime from your [account settings](https://code4rena.com/account).

We take being entrusted with your privacy and personal information very seriously. As such:

* This info is submitted via an end-to-end encrypted transmission to isolated data storage separate from other Code4rena APIs.
* There is extremely restricted access to the key. During the course of its day-to-day operations, Code4rena does not have access to names, addresses or tax identification numbers.
* The sole use of provided information is to ensure OFAC compliance and enable accountants (under NDA) to submit annual tax reports.
* The only other cases data could be accessed would be under legal subpoena or due to justified inquiries based on compelling evidence of grave ethical violations.

***

### My problem is not solved!

Feel free to reach out and [submit a Help Desk request](https://code4rena.com/help/).
