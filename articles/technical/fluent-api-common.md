---
uid: tech-fluent-api-common
title: Fluent API common parts
---

# IColumnTypeSyntax&lt;TNext&gt;

<pre>
--------+- AsAnsiString -+--------+-------------+---------------+-> TNext
        |                |        |             |               |
        |                +- size -+- collation -+               |
        |                                                       |
        +- AsBinary -----+--------+-----------------------------+
        |                |        |                             |
        |                +- size -+                             |
        |                                                       |
        +- AsBoolean -------------------------------------------+
        |                                                       |
        +- AsByte ----------------------------------------------+
        |                                                       |
        +- AsCurrency ------------------------------------------+
        |                                                       |
        +- AsDate ----------------------------------------------+
        |                                                       |
        +- AsDateTime ------------------------------------------+
        |                                                       |
        +- AsDateTime2 -----------------------------------------+
        |                                                       |
        +- AsDateTimeOffset ------------------------------------+
        |                                                       |
        +- AsDecimal -------------------------------------------+
        |                                                       |
        +- AsDouble --------------------------------------------+
        |                                                       |
        +- AsGuid ----------------------------------------------+
        |                                                       |
        +- AsFixedLengthString --- size -----+-------------+----+
        |                                    |             |    |
        |                                    +- collation -+    |
        |                                                       |
        +- AsFixedLengthAnsiString --- size -+-------------+----+
        |                                    |             |    |
        |                                    +- collation -+    |
        |                                                       |
        +- AsFloat ---------------------------------------------+
        |                                                       |
        +- AsInt16 ---------------------------------------------+
        |                                                       |
        +- AsInt32 ---------------------------------------------+
        |                                                       |
        +- AsInt64 ---------------------------------------------+
        |                                                       |
        +- AsString -----+--------+-------------+---------------+
        |                |        |             |               |
        |                +- size -+- collation -+               |
        |                                                       |
        +- AsTime ----------------------------------------------+
        |                                                       |
        +- AsXml --------+--------+-----------------------------+
        |                |        |                             |
        |                +- size -+                             |
        |                                                       |
        +- AsCustom --- customType -----------------------------+
</pre>

# IColumnOptionSyntax&lt;TNext,TNextFk&gt;

<pre>
--------+- WithDefault --- method --------------------------------------+--> TNext
        |                                                               |
        +- WithDefaultValue --- value ----------------------------------+
        |                                                               |
        +- WithColumnDescription --- description -----------------------+
        |                                                               |
        +- Identity ----------------------------------------------------+
        |                                                               |
        +- Indexed -----------------------------------------------------+
        |                                                               |
        +- PrimaryKey -+--------+---------------------------------------+
        |              |        |                                       |
        |              +- name -+                                       |
        |                                                               |
        +- Nullable ----------------------------------------------------+
        |                                                               |
        +- NotNullable -------------------------------------------------+
        |                                                               |
        +- Unique -----+--------+---------------------------------------+
        |              |        |
        |              +- name -+
        |
        +- ForeignKey ---+-------------------------------------------+--+--> TNextFk
        |                |                                           |  |
        |                +-----------------------+- table --- column-+  |
        |                |                       |                      |
        |                +- name -+-+----------+-+                      |
        |                           |          |                        |
        |                           +- schema -+                        |
        |                                                               |
        +- ReferencedBy -+-----------------------+- table --- column-+--+
                         |                       |
                         +- name -+-+----------+-+
                                    |          |
                                    +- schema -+
</pre>

# IForeignKeyCascadeSyntax&lt;TNext,TNextFk&gt;

<pre>
--------+- OnDeleteOrUpdate --- rule ---> TNext
        |
        +- OnDelete --- rule -+---------> TNextFk
        |                     |
        +- OnUpdate --- rule -+
</pre>