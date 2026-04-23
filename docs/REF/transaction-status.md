---
title: Transaction status
deprecated: false
hidden: false
metadata:
  robots: index
---
## DigiTax Queueing system

DigiTax provides the following:

* Asynchronous functionality that automatically retries eTIMS
* Get notifications on transaction statuses via [Callback URLs](https://ke.docs.digitax.tech/docs/callback-urls#/)
* Throttling traffic between the businesses throughput and eTIMS

These features are possible due to the DigiTax Queueing system.

> 📘 You don't run the risk of double-entry
>
> Every transaction that interacts with eTIMS is first off entered into the DigiTax Queueing system to **mitigate against possible eTIMS intermittency and downtime** or slow response rate.

## The different transaction statuses and what they mean

Since transactions are first off entered into the DigiTax Queueing system, we give you the following statuses - **Pending**, **Failed**, **Submitted** (not applicable for items) and **Completed**. Below is a table explaining what they mean and your next actions.

### Transaction statuses

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Status
      </th>

      <th>
        Meaning
      </th>

      <th>
        Action
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Pending
      </td>

      <td>
        The transaction has been queued in the DigiTax Queueing system.
        This is the initial status before eTIMS responds to our attempt to sync with their system.
      </td>

      <td>
        Check in later.
        If you set up [Callback URLs](https://ke.docs.digitax.tech/docs/callback-urls#/), we'll post to your system when the eTIMS sync is done. Expect a status of either **Failed** or **Completed**.
      </td>
    </tr>

    <tr>
      <td>
        Failed
      </td>

      <td>
        eTIMS sync is complete.
        eTIMS rejected the transaction.
      </td>

      <td>
        Please initiate another transaction.
        If this persists for several transactions, kindly initiate an email/ chat with us for DigiTax support team to intervene.
        (**DigiTax chat** is at the bottom right of any page)
      </td>
    </tr>

    <tr>
      <td>
        Completed
      </td>

      <td>
        eTIMS sync is complete.
        eTIMS has accepted the transaction, and we have the final data in DigiTax accessible via Dashboard, Apps, or API.
      </td>

      <td>
        For ITEM: You can now create a sale with this item\\
        For SALE: You now have the `etims_url`, and invoice metadata (`signature` and `internal_data`)
      </td>
    </tr>

    <tr>
      <td>
        Submitted
        (Only applies to Sales and Credit Notes)
      </td>

      <td>
        *This status is rare*
        eTIMS sync is complete.
        However, we do not have the final data from their system.
      </td>

      <td>
        Kindly initiate an email/ chat with us for DigiTax support team to intervene.
        (**DigiTax chat** is at the bottom right of any page)
      </td>
    </tr>
  </tbody>
</Table>