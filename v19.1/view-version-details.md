---
title: View Version Details
summary: To view [version](cluster-settings.html#setting-version) details for a specific cockroach binary, run the cockroach [version](cluster-settings.html#setting-version) command.
toc: false
---

To view [version](cluster-settings.html#setting-version) details for a specific `cockroach` binary, run the `cockroach [version](cluster-settings.html#setting-version)` [command](cockroach-commands.html):

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

The `cockroach [version](cluster-settings.html#setting-version)` command outputs the following fields:

Field | Description
------|------------
`Build Tag` | The CockroachDB [version](cluster-settings.html#setting-version).
`Build Time` | The date and time when the binary was built.
`Distribution` | The scope of the binary. If `CCL`, the binary contains open-source and enterprise functionality covered by the CockroachDB Community License. If `OSS`, the binary contains only open-source functionality.<br><br>To obtain a pure open-source binary, you must [build from source](install-cockroachdb.html) using the `make buildoss` command.
`Platform` | The platform that the binary can run on.
`Go Version` | The [version](cluster-settings.html#setting-version) of Go in which the source code is written.
`C Compiler` | The C compiler used to build the binary.
`Build SHA-1` | The SHA-1 hash of the commit used to build the binary.
`Build Type` | The type of release. If `release`, `release-gnu`, or `release-musl`, the binary is for a [production release](../releases/#production-releases). If `development`, the binary is for a [testing release](../releases/#testing-releases).

## See also

- [Install CockroachDB](install-cockroachdb.html)
- [Other Cockroach Commands](cockroach-commands.html)
