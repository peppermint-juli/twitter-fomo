# Migration `20200809220012-add-unique-to-twitter-id`

This migration has been generated by Tom Dohnal at 8/10/2020, 12:00:12 AM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE UNIQUE INDEX "Tweet.twitterId_unique" ON "public"."Tweet"("twitterId")
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration 20200809204743-init..20200809220012-add-unique-to-twitter-id
--- datamodel.dml
+++ datamodel.dml
@@ -2,9 +2,9 @@
 // learn more about it in the docs: https://pris.ly/d/prisma-schema
 datasource db {
   provider  =  "postgresql"
-  url = "***"
+  url = "***"
 }
 generator client {
   provider = "prisma-client-js"
@@ -126,9 +126,9 @@
 model Tweet {
   id              Int                @id @default(autoincrement())
   list            List[]
-  twitterId       String
+  twitterId       String             @unique
   publishedAt     DateTime
   text            String
   accountName     String
   account         Account            @relation(fields: [accountId], references: [id])
```


