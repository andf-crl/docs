1. As the `root` user, open the [built-in SQL client](cockroach-sql.html):

    {% include_cached copy-clipboard.html %}
    ~~~ shell
    $ cockroach sql --insecure
    ~~~

1. Set your organization name and [{{ site.data.products.enterprise }} license](enterprise-licensing.html) key that you received via email:

    {% include_cached copy-clipboard.html %}
    ~~~ sql
    > SET CLUSTER SETTING [cluster.organization](cluster-settings.html#setting-cluster-organization) = '<organization name>';
    ~~~

    {% include_cached copy-clipboard.html %}
    ~~~ sql
    > SET CLUSTER SETTING [enterprise.license](cluster-settings.html#setting-enterprise-license) = '<secret>';
    ~~~

1. Enable the `[kv.rangefeed.enabled](cluster-settings.html#setting-kv-rangefeed-enabled)` [cluster setting](cluster-settings.html):

    {% include_cached copy-clipboard.html %}
    ~~~ sql
    > SET CLUSTER SETTING [kv.rangefeed.enabled](cluster-settings.html#setting-kv-rangefeed-enabled) = true;
    ~~~
