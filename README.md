# Day 1 — AWS Lab Preparation

This is a learning project. Day 1 documents what I checked and did in my AWS account before starting any lab work.

**Date and time checked:** 3 November 2026, 20:16

## Objective

The goals I set for Day 1:

- Find my AWS account's Free Tier information
- Check current usage and available credits
- Choose a Region for the project
- Explain what I have verified and what is still unknown
- Save my Day 1 work on GitHub

## Cloud Environment and Services Used

- **Cloud provider:** AWS
- **AWS Management Console pages used:** Billing and Cost Management (Billing home, Free Tier, Credits, Billing preferences), the Account page while signed in as the root user, and Unified Settings (Default Region)
- **Sign-ins used:** my IAM user, and the root user (temporarily, to change one billing setting)
- **Region chosen:** United States (N. Virginia) us-east-1

### What I recorded

| Item | What I recorded |
|---|---|
| Account plan | Not shown |
| Current month cost or usage amount | Not shown |
| Remaining credits | Unclear |
| Credits expiry date | 25 August 2027 (from my notes; not verified by a screenshot) |
| Usage warnings | None were issued (from my notes; not shown in a screenshot) |
| Cost alert status | Delivered (as shown in Fig 6) |
| Region and reason | us-east-1, chosen so that I could access my account's billing information |

## Practical Work Performed

**1. Signed in to the AWS console.** This is the Console Home page I saw after signing in with my IAM user.

![AWS Console Home page showing the Recently visited list](evidence/01-console-home.png)

**2. Opened Billing and Cost Management.** I searched for Billing and Cost Management in the console search bar and opened the Billing home page. I do not have a screenshot of this page.

**3. Opened the Free Tier page.** Because I was working with a free tier account, I opened Free Tier from the sidebar to see the services I was using that fall under the Free Tier.

![Free Tier page summary showing a banner about free plan accounts and 2 service offers in use](evidence/02-free-tier-summary.png)

![Free Tier offers in use table listing AmazonCloudWatch and AWS Glue](evidence/03-free-tier-offers-in-use.png)

**4. Opened the Credits page.** I opened Credits from the sidebar to check the credit amount. At this point it showed $0.

![Credits page showing $0.00 in the summary and 0 active credits](evidence/04-credits-page-before-iam-access.png)

**5. Opened Billing preferences to check cost alerts.** I selected Billing preferences in the left sidebar and got an error saying I needed permissions to view the page.

![Billing and Cost Management page showing a You need permissions error](evidence/05-billing-preferences-permission-error.png)

**6. Changed the billing access setting as the root user.** To let my IAM user view billing information, I signed out of the IAM user and signed in as the root user. In the root user's account menu I opened Account and looked at "IAM User and Role Access to Billing Information". I clicked Edit, selected "Activate IAM Access", and saved. I do not have a screenshot of this step.

**7. Checked again as my IAM user.** I signed out of the root account and signed back in to my IAM user. The Billing preferences page then showed details, and the Credits page showed credits.

![Billing preferences page showing alert preferences for AWS Free Tier alerts and CloudWatch billing alerts as Delivered](evidence/06-billing-preferences-after-iam-access.png)

![Credits page summary showing credit amounts after IAM access was activated](evidence/07-credits-page-after-iam-access.png)

**8. Chose my Region.** I went back to my home page, searched for "Region" in the search bar, and selected "Default Region" under Features.

![Search results for region with Default Region listed under Features](evidence/08-search-default-region.png)

On the Default Region page I chose United States (N. Virginia) us-east-1, because in this Region I will be able to access my account's billing information. I then saved the settings.

![Edit localization and default Region page with United States (N. Virginia) us-east-1 selected](evidence/09-default-region-us-east-1.png)

## Challenges and Troubleshooting

**Challenge:** My IAM user did not have access to billing information. The Billing preferences page showed a permissions error (Fig 5), and the Credits page showed $0 (Fig 4).

**What I did:** I signed in as the root user, opened the "IAM User and Role Access to Billing Information" setting on the Account page, selected "Activate IAM Access", and saved. I did not record whether that setting was enabled or disabled before I changed it.

**Result:** After signing back in as my IAM user, the Billing preferences page showed details (Fig 6) and the Credits page showed credits (Fig 7).

### My Part 2 answers before and after the change

| Item | Before the change | After the change |
|---|---|---|
| Account plan | Not shown | Not shown |
| Current month cost or usage amount | Not shown | Not shown |
| Credits | $0 shown on the Credits page | Credits shown on the Credits page; amount Unclear |
| Credits expiry date | Not seen | 25 August 2027 (not verified by a screenshot) |
| Usage warnings | None issued | None issued |

## Verified Results

These results are supported by my screenshots:

- The Free Tier page opened and listed 2 Free Tier offers in use: AmazonCloudWatch and AWS Glue (Fig 2 and 3).
- The Credits page first showed $0.00 and 0 active credits (Fig 4).
- The Billing preferences page first returned a permissions error (Fig 5).
- After I activated IAM access and signed back in as my IAM user, the Billing preferences page loaded and showed AWS Free Tier alerts and CloudWatch billing alerts as Delivered (Fig 6).
- After the same change, the Credits page showed credit figures (Fig 7). I have recorded the remaining credit amount as Unclear.
- The Default Region page showed United States (N. Virginia) us-east-1 selected (Fig 9). I saved this setting.

## Evidence

| File | What it shows |
|---|---|
| `evidence/01-console-home.png` | Console Home page after signing in |
| `evidence/02-free-tier-summary.png` | Top of the Free Tier page |
| `evidence/03-free-tier-offers-in-use.png` | Free Tier offers in use (AmazonCloudWatch, AWS Glue) |
| `evidence/04-credits-page-before-iam-access.png` | Credits page before the billing access change |
| `evidence/05-billing-preferences-permission-error.png` | Permissions error on Billing preferences |
| `evidence/06-billing-preferences-after-iam-access.png` | Billing preferences page after the change |
| `evidence/07-credits-page-after-iam-access.png` | Credits page after the change |
| `evidence/08-search-default-region.png` | Searching for Default Region |
| `evidence/09-default-region-us-east-1.png` | Default Region page with us-east-1 selected |

## Lessons Learned

- I need permissions to access certain resources. I did not have permission to view billing information until IAM access to billing was enabled.
- I should check my cost status before deploying any resources.
- The Region matters. My understanding is that some capabilities are restricted by Region, and I chose us-east-1 so that I could view billing information. My screenshots do not verify the general point about Regions.

### My reflections on what I found

- My understanding is that a free tier account can run certain services, not all, and that usage is covered by the free credits, not by my own money. The banner in Fig 2 says credits cover free plan costs, but I did not test which services are covered.
- I understand the displayed amount to be my credit balance, showing how many credits I still have to work with.
- I should check costs before deploying resources, because free tier credits are limited and I want to manage them across future resources. I see cost management as an important skill for a cloud engineer.
- If I noticed unexpected usage of a resource or my free credits, I would investigate what it is and try to shut it down. This is what I would do; it did not happen on Day 1.

## Limitations and What Was Not Verified

- The account plan was not shown to me.
- The current month cost or usage amount was not shown to me.
- The remaining credit amount is Unclear. My screenshots do not all show the same figures, and I have not reconciled them.
- The credits expiry date (25 August 2027) comes from my notes. No screenshot shows it.
- I have no screenshot of the Billing home page, of the root user change to "IAM User and Role Access to Billing Information", or of the Region setting after I saved it.
- I did not record whether the IAM access setting was enabled or disabled before I changed it.
- "No usage warnings" comes from my notes and is not shown in a screenshot.
- I do not know whether any information is missing.

## Next Steps

- Save my Day 1 work on GitHub (not yet done).
