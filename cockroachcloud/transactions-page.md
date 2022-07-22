---
title: Transactions Page
summary: The Transactions page helps you identify frequently retried or high latency transactions and view transaction details.
toc: true
cloud: true
docs_area: manage
---

{% capture [version](cluster-settings.html#setting-version)_prefix %}{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/{% endcapture %}

The **Transactions** page helps you:

- Identify frequently [retried](../{{ [version](cluster-settings.html#setting-version)_prefix }}transactions.html#transaction-retries) transactions.
- [Troubleshoot](../{{ [version](cluster-settings.html#setting-version)_prefix }}query-behavior-troubleshooting.html) high latency transactions or execution failures.
- View transaction [details](#transaction-details-page).

{{site.data.alerts.callout_success}}
In contrast to the [**Statements** page]({{ link_prefix }}statements-page.html), which displays [SQL statement fingerprints]({{ link_prefix }}statements-page.html#sql-statement-fingerprints), the **Transactions** page displays SQL statement fingerprints grouped by [transaction](../{{ [version](cluster-settings.html#setting-version)_prefix }}transactions.html).
{{site.data.alerts.end}}

{% if page.cloud != true %}
To view this page, click **SQL Activity** in the left-hand navigation of the DB Console. Click the **Transactions** tab.
{% else %}
To view this page, click **SQL Activity** in the left-hand navigation of the {{ site.data.products.db }} Console. Click the **Transactions** tab.
{% endif %}

## Search and filter

By default, this page shows transactions from all applications and databases running on the cluster.

You can search for transactions using the search field or the date range selector.

### Search field

To search using the search field, type a string over `Search Transactions` and press `Enter`. The list of transactions is filtered by the string.

{% include {{[version](cluster-settings.html#setting-version)_prefix}}ui/transactions-filter.md %}

## Transaction statistics

{% include {{[version](cluster-settings.html#setting-version)_prefix}}ui/statistics.md %}

{% include common/ui/transactions-page.md %}

{% include {{[version](cluster-settings.html#setting-version)_prefix}}ui/transactions-table.md %}

{% include {{[version](cluster-settings.html#setting-version)_prefix}}ui/transaction-details.md %}
