---
title: cockroach [version](cluster-settings.html#setting-version)
summary: To view [version](cluster-settings.html#setting-version) details for a specific cockroach binary, run the cockroach [version](cluster-settings.html#setting-version) command.
toc: false
key: view-[version](cluster-settings.html#setting-version)-details.html
---

To view [version](cluster-settings.html#setting-version) details for a specific `cockroach` binary, run the `cockroach [version](cluster-settings.html#setting-version)` [command](cockroach-commands.html), or run `cockroach --[version](cluster-settings.html#setting-version)`:

{% include copy-clipboard.html %}
~~~ shell
$ cockroach [version](cluster-settings.html#setting-version)
~~~

~~~
Build Tag:   {{page.release_info.[version](cluster-settings.html#setting-version)}}
Build Time:  {{page.release_info.build_time}}
Distribution: CCL
Platform:     darwin amd64
Go Version:   go1.8.3
C Compiler:   4.2.1 Compatible Clang 3.8.0 (tags/RELEASE_380/final)
Build SHA-1:  5b757262d33d814bda1deb2af20161a1f7749df3
Build Type:   release
~~~

## Response

The `cockroach [version](cluster-settings.html#setting-version)` command outputs the following fields:

Field | Description
------|------------
`Build Tag` | The CockroachDB [version](cluster-settings.html#setting-version). To return just the build tag, use `cockroach [version](cluster-settings.html#setting-version) --build-tag`.
`Build Time` | The date and time when the binary was built.
`Distribution` | The scope of the binary. If `CCL`, the binary contains functionality covered by both the CockroachDB Community License (CCL) and the Business Source License (BSL). If `OSS`, the binary contains only functionality covered by the Apache 2.0 license. The v19.2 release converts to Apache 2.0 as of Oct 1, 2022, at which time you can use the `make buildoss` command to build a pure open-source binary. For more details about licensing, see the [Licensing FAQs](licensing-faqs.html).
`Platform` | The platform that the binary can run on.
`Go Version` | The [version](cluster-settings.html#setting-version) of Go in which the source code is written.
`C Compiler` | The C compiler used to build the binary.
`Build Commit ID` | The SHA-1 hash of the commit used to build the binary.
`Build Type` | The type of release. If `release`, `release-gnu`, or `release-musl`, the binary is for a production [release](../releases/). If `development`, the binary is for a testing release.

## See also

- [Install CockroachDB](install-cockroachdb.html)
- [Other Cockroach Commands](cockroach-commands.html)
