---
title: Unsupported Features in CockroachDB Serverless
summary: Summary of CockroachDB features that are not supported in CockroachDB Serverless 
toc: true
docs_area: reference
---

{{ site.data.products.serverless }} is a [managed multi-tenant deployment of CockroachDB](architecture.html#cockroachdb-serverless) that automatically scales up and down based on the load on the cluster. {{ site.data.products.serverless }} works with almost all workloads that CockroachDB supports, but there are feature differences between {{ site.data.products.core }} or {{ site.data.products.dedicated }} clusters and {{ site.data.products.serverless }} clusters. This topic describes the features that are either unsupported or partially supported in {{ site.data.products.serverless }} clusters. Cockroach Labs intends to eliminate these feature gaps in future releases of {{ site.data.products.serverless }}.

## Change data capture

[Distributed SQL (DistSQL)](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/architecture/sql-layer.html#distsql) is not supported, which improves the performance of changefeeds.

You can't collect [metrics per changefeed](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/monitor-and-debug-changefeeds.html#using-changefeed-metrics-labels).

You can't configure [alerts on changefeeds](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/monitoring-and-alerting.html#changefeed-is-experiencing-high-latency).

## Backups

{{ site.data.products.serverless }} only support automated full backups. Automated [incremental](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/take-full-and-incremental-backups.html) and [revision history](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/take-backups-with-revision-history-and-restore-from-a-point-in-time.html) backups are not supported. However, [user managed incremental and revision history backups](run-bulk-operations.html#backup-and-restore-data) using user provided storage locations are supported.

Automated database and table level backups are not supported in {{ site.data.products.serverless }}. However, [user managed database and table level backups](run-bulk-operations.html#backup-and-restore-data) using user provided storage locations are supported.

Both {{ site.data.products.serverless }} and {{ site.data.products.dedicated }} clusters do not support automated [locality-aware backups](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/take-and-restore-locality-aware-backups.html). However, user managed locality-aware backups using user provided storage locations are supported in {{ site.data.products.serverless }}, {{ site.data.products.dedicated }}, and {{ site.data.products.core }} clusters. That is, you need to configure and manage your own locality-aware backups.

## Performance

[Distributed SQL (DistSQL)](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/architecture/sql-layer.html#distsql) is not supported in {{ site.data.products.serverless }} clusters, so users do not benefit from the improved query performance that DistSQL offers, especially for online analytical processing (OLAP) queries and bulk operations like [`IMPORT`](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/import.html).

## Multi-region clusters

{{ site.data.products.serverless }} is only supported in a single region, and does not support [multi-region](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/multiregion-overview.html) features.

## Follower reads

[Follower reads](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/follower-reads.html) are not supported in {{ site.data.products.serverless }} clusters.

## Range management

The [`ALTER TABLE ... SPLIT AT`](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/split-at.html) and [`ALTER RANGE ... RELOCATE`](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/alter-range-relocate.html) statements are not supported in {{ site.data.products.serverless }}.

## Query cancellation using pgwire

[Canceling queries from client drivers/ORMs using the PostgreSQL wire protocol (pgwire)](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/cancel-query.html#considerations) is not supported in {{ site.data.products.serverless }}.

## Self service upgrades

{{ site.data.products.serverless }} is a fully managed multi-tenant deployment of CockroachDB. Major and minor upgrades of CockroachDB are handled by Cockroach Labs, and [can't be initiated by users](serverless-faqs.html#can-i-upgrade-the-[version](cluster-settings.html#setting-version)-of-cockroachdb-my-cockroachdb-serverless-beta-cluster-is-running-on).

## Monitoring workloads and cluster health

The [DB Console](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/ui-overview.html) is not supported in {{ site.data.products.serverless }}. The CockroachDB [Cloud Console](cluster-overview-page.html) provides metrics and graphs to monitor the health, performance, and state of your cluster.

The Cloud Console provides a subset of observability information from the DB Console including **SQL Metrics**, **SQL Activity**, and **Databases** information. The Cloud Console does not include information from the following DB Console pages:

- Non-SQL metrics
- Network Latency
- Hot ranges
- Jobs
- Advanced Debug

{{ site.data.products.serverless }} clusters do not expose [Prometheus endpoints](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/monitor-cockroachdb-with-prometheus.html).

## Audit logs

There is no self-service way of accessing [audit logs](sql-audit-logging.html) for {{ site.data.products.serverless }} clusters. If you are running production workloads and need access to audit logs, contact [Cockroach Labs Support](https://support.cockroachlabs.com).

## Encryption

[Encryption at rest](../{{site.[version](cluster-settings.html#setting-version)s["stable"]}}/security-reference/encryption.html#encryption-at-rest) is not supported in {{ site.data.products.serverless }} clusters.

[Customer-managed encryption keys](managing-cmek.html) (CMEK) are not supported in {{ site.data.products.serverless }} clusters.