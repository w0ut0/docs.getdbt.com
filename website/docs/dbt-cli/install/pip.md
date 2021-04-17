---
title: "pip"
---

dbt is a Python module distributed on [PyPi](https://pypi.org/project/dbt/), and can be installed via `pip`. We recommend using virtual environments when installing with `pip`.

<FAQ src="install-pip-os-prereqs" />
<FAQ src="install-python-compatibility" />
<FAQ src="install-pip-best-practices" />

### Standard Installation

To install the standard dbt distribution, including the four most popular adapter plugins:

```shell
pip install dbt
```

Check your installation with `dbt --version`:
```shell
$ dbt --version
installed version: 0.19.1
   latest version: 0.19.1

Up to date!

Plugins:
  - bigquery: 0.19.1
  - snowflake: 0.19.1
  - redshift: 0.19.1
  - postgres: 0.19.1
```

### Install a specific adapter

If you know which adapter you're using, or if its dbt plugin is not included by the standard distribution, you can always install it directly as `dbt-[adapter]`. For instance, if using postgres:
```shell
pip install dbt-postgres
```
This will install `dbt-core` and `dbt-postgres` _only_:
```
$ dbt --version
installed version: 0.19.1
   latest version: 0.19.1

Up to date!

Plugins:
  - postgres: 0.19.1
```

All adapters build on top of `dbt-core`. Some also depend on other adapters: for example, `dbt-redshift` builds on top of `dbt-postgres`. In that case, you would see those adapters included by your specific installation, too.

### Upgrading
To upgrade the standard dbt distribution, use:
```shell
pip install --upgrade dbt
```
To upgrade a specific adapter plugin:
```shell
pip install --upgrade dbt-[adapter]
```
