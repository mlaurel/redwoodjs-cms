# Migration `20200529183929-create-products-table`

This migration has been generated by Mike Laurel at 5/29/2020, 6:39:29 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
PRAGMA foreign_keys=OFF;

CREATE TABLE "quaint"."Product" (
"description" TEXT   ,"id" INTEGER NOT NULL  PRIMARY KEY AUTOINCREMENT,"image" TEXT   ,"name" TEXT NOT NULL  ,"price" REAL NOT NULL  )

PRAGMA "quaint".foreign_key_check;

PRAGMA foreign_keys=ON;
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200529183929-create-products-table
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,19 @@
+datasource DS {
+  provider = "sqlite"
+  url      = env("DATABASE_URL")
+}
+
+generator client {
+  provider      = "prisma-client-js"
+  binaryTargets = env("BINARY_TARGET")
+}
+
+// Define your own datamodels here and run `yarn redwood db save` to create
+// migrations for them.
+model Product {
+  id                     Int     @default(autoincrement()) @id
+  name               String
+  price                Float
+  description    String?
+  image              String?
+}
```

