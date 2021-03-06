drill-excel-plugin [![Build Status](https://travis-ci.org/bizreach/drill-excel-plugin.svg?branch=master)](https://travis-ci.org/bizreach/drill-excel-plugin)
==================
Apache Drill plugin for Excel files.

Installation
----

Download `drill-excel-plugin-VERSION-jar-with-dependencies.jar` from the [release page](https://github.com/bizreach/drill-excel-plugin/releases) and put it into `DRILL_HOME/jars/3rdparty`.

Add a format setting to the storage configuration as:

```javascript
  "formats": {
    "excel": {
      "type": "excel",
      "extensions": [
        "xlsx"
      ]
    },
    ...
  }
```

Then you can query `*.xlsx` files on Apache Drill.

```
0: jdbc:drill:zk=local> SELECT id, name FROM dfs.`/tmp/emp.xlsx` where age > 35.0;
+----------+----------------+
|    id    |      name      |
+----------+----------------+
| takezoe  | Naoki Takezoe  |
+----------+----------------+
1 row selected (3.118 seconds)
```

Build from source
----

Run `mvn package -DskipTests=true`. `drill-excel-plugin-VERSION-jar-with-dependencies.jar` is generated into `target` directory.
