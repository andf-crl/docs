---
title: Sessions Page
summary: The Sessions page provides details of all open sessions in the cluster.
toc: true
cloud: true
docs_area: manage
---

{% capture [version](cluster-settings.html#setting-version)_prefix %}{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/{% endcapture %}

The **Sessions** page of the {{ site.data.products.db }} Console provides details of all open sessions in the cluster.

To view this page, click **SQL Activity** in the left-hand navigation of the {{ site.data.products.db }} Console. Click the **Sessions** tab.

{% include common/ui/sessions-page.md %}

{% include {{[version](cluster-settings.html#setting-version)_prefix}}ui/sessions.md %}
