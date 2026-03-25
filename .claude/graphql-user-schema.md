# GraphQL User API Reference

**Endpoint:** `https://storefront-user.yalochat.dev/v3/user/storefronts`  
**Generated:** 2026-03-25

---

## Table of Contents

- [Queries](#queries)
- [Mutations](#mutations)
- [Input Types](#input-types)
- [Return Types](#return-types)
- [Enums](#enums)

---

## Queries

### `APIToken`

**Returns:** `Token`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |


### `alternativeProducts`

**Returns:** `[Product]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront name |
| `sessionUid` | `ID!` | **Yes** |  | ID of the session |
| `skus` | `[String]!` | **Yes** |  | Product SKUs to get alternatives for |


### `banners`

**Returns:** `[Banner]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `brands`

**Returns:** `[Brand]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |


### `cart`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `catalog`

**Returns:** `[Catalog]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront name |
| `sessionUid` | `String!` | **Yes** |  | Id of the session |
| `category` | `String` | No |  | category uid |
| `pagination` | `PaginationInput` | No |  | Pagination |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |
| `groupCategories` | `Boolean` | No | false | This group categories with children so they are adjacent to the parent on the response |
| `showChildrenCategories` | `Boolean` | No | false | This show children categories |
| `showHiddenCategories` | `Boolean` | No | false | This show hidden categories |


### `catalogFlat`

**Returns:** `[Product]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront name |
| `sessionUid` | `String!` | **Yes** |  | Id of the session |
| `pagination` | `PaginationSkipInput` | No |  | Pagination |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |


### `categories`

**Returns:** `[Category]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `pagination` | `PaginationInput` | No |  |  |
| `parentId` | `ID` | No |  |  |
| `sessionUid` | `String` | No |  |  |
| `skipAddon` | `Boolean` | No | false |  |
| `showChildrenCategories` | `Boolean` | No | false |  |
| `showHidden` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `autoPopulate` | `AutoPopulateCategoryInput` | No |  |  |


### `checkoutSessionRule`

**Returns:** `ResponseSessionRule`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `ruleType` | `String` | No |  |  |


### `customer`

**Returns:** `Customer`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `code` | `String!` | **Yes** |  |  |
| `referrer` | `String` | No |  |  |


### `customerSegments`

**Returns:** `CustomerSegmentsResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionId` | `ID!` | **Yes** |  |  |


### `frequentlyBoughtTogether`

**Returns:** `[Product]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront Name |
| `skus` | `[String]!` | **Yes** |  | Product IDs |
| `sessionUid` | `String!` | **Yes** |  | Id of the session |
| `limit` | `Int` | No |  | Number of products to return |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |


### `getCheckoutRule`

**Returns:** `ResponseRules`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `ruleType` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `getLoyaltyPoints`

**Returns:** `LoyaltyPoints`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `customerCode` | `String` | No |  |  |


### `getProductBySKU`

**Returns:** `Product`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront name |
| `sessionUid` | `String!` | **Yes** |  | Type of customer |
| `sku` | `String!` | **Yes** |  | Product sku |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |
| `referrer` | `String` | No |  | referrer |


### `getSpecialPromotions`

**Returns:** `[Promotion]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `getStores`

**Returns:** `PaginatedStores`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterStoreInput` | No |  |  |


### `getTotalPromotions`

**Returns:** `[Promotion]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `skipAddon` | `Boolean` | No | false |  |


### `lastOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `skipAddon` | `Boolean` | No | false |  |


### `link`

**Returns:** `LinkData`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `skipAddon` | `Boolean` | No | false |  |


### `linkedProducts`

**Returns:** `[Product]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront name |
| `sessionUid` | `ID!` | **Yes** |  | ID of the session |


### `locateNearbyStores`

**Returns:** `[Store]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `String!` | **Yes** |  |  |
| `data` | `CustomerLocationInput!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |


### `order`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `id` | `ID` | No |  |  |


### `prefillCart`

**Returns:** `[CartProduct]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront Name |
| `sessionUid` | `String!` | **Yes** |  | Id of the session |
| `limit` | `Int` | No |  | Number of products to return |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |


### `promotedProducts`

**Returns:** `PromotedProductsReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront name |
| `sessionUid` | `String!` | **Yes** |  | Id of the session |
| `pagination` | `PaginationInput` | No |  | Pagination |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |


### `search`

**Returns:** `ProductSearchReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront name |
| `sessionUid` | `String!` | **Yes** |  | Id of the session |
| `searchTerm` | `String` | No |  | Search term |
| `tags` | `[String]` | No |  | Product tags |
| `categories` | `[String]` | No |  | Product categories |
| `attributes` | `[String]` | No |  | Product attributes |
| `skus` | `[String]` | No |  | Products sku |
| `filter` | `SearchFilterInput` | No |  | Advanced search filter |
| `pagination` | `PaginationInput` | No |  | Pagination |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |


### `searchProduct`

**Returns:** `[Product]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront name |
| `sessionUid` | `String!` | **Yes** |  | Id of the session |
| `searchTerm` | `String` | No |  | Search term |
| `tags` | `[String]` | No |  | Product tags |
| `categories` | `[String]` | No |  | Product categories |
| `attributes` | `[String]` | No |  | Product attributes |
| `skus` | `[String]` | No |  | Products sku |
| `filter` | `SearchFilterInput` | No |  | Advanced search filter |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |


### `session`

**Returns:** `Session`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `store`

**Returns:** `Store`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `storefront`

**Returns:** `Storefront`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `id` | `ID` | No |  |  |
| `name` | `String` | No |  |  |


### `stores` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getStores' query instead

**Returns:** `[Store]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterStoreInput` | No |  |  |


### `suggestedItems`

**Returns:** `[SuggestedItemReturned]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront Name |
| `sessionUid` | `String!` | **Yes** |  | Id of the session |
| `limit` | `Int` | No |  | Number of products to return |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |


### `summary`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `validateCart`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


---

## Mutations

### `acceptedCheckoutRule`

**Returns:** `ResponseAcceptedRule`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `ruleType` | `String!` | **Yes** |  |  |


### `activateDeferredPromotion`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `data` | `ActivateDeferredPromotionDataInput!` | **Yes** |  |  |


### `cancelOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `id` | `ID` | No |  |  |


### `cancelOrders`

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `cartAddFee`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `data` | `CartAddFeeDataInput!` | **Yes** |  |  |


### `cartAddProduct`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `data` | `CartProductOpInput!` | **Yes** |  |  |


### `cartEmpty`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `cartRemoveFee`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `data` | `CartRemoveFeeDataInput!` | **Yes** |  |  |


### `cartRemoveProduct`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `data` | `CartProductOpInput!` | **Yes** |  |  |


### `checkOrder`

**Returns:** `CheckOrderResult`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `orderUid` | `String!` | **Yes** |  |  |
| `name` | `String!` | **Yes** |  |  |


### `confirmOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `id` | `ID` | No |  |  |
| `data` | `OrderInput` | No |  |  |


### `confirmOrders`

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `createAPIToken`

**Returns:** `Token`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |


### `createOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `data` | `OrderInput` | No |  |  |
| `skipAddon` | `Boolean` | No | false |  |


### `createOrders`

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `data` | `OrderInput` | No |  |  |
| `skipAddon` | `Boolean` | No | false |  |


### `createSession`

**Returns:** `Session`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `SessionInput!` | **Yes** |  |  |
| `skipAddon` | `Boolean` | No | false |  |
| `skipRegistration` | `Boolean` | No | false |  |


### `deliverOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `id` | `ID` | No |  |  |
| `data` | `OrderInput` | No |  |  |


### `deliverOrders`

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `expireSession`

**Returns:** `Session`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `markOrderAsError`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `id` | `ID` | No |  |  |


### `markOrdersAsError`

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `notifyBackInStock`

**Returns:** `Product`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `sku` | `String!` | **Yes** |  |  |


### `orderCallback`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID` | No |  |  |
| `data` | `OrderData!` | **Yes** |  |  |


### `payOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `id` | `ID` | No |  |  |
| `data` | `PayOrderInput!` | **Yes** |  |  |


### `payOrders`

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `data` | `PayOrderInput!` | **Yes** |  |  |


### `placeOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `id` | `ID` | No |  |  |
| `data` | `OrderInput` | No |  |  |


### `placeOrders`

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `prefillCart`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `items` | `[CartProductInput]` | No |  |  |
| `replaceCart` | `Boolean` | No | true |  |
| `referrer` | `String` | No |  |  |


### `recalculateCart`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `removeAPIToken`

**Returns:** `String`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |


### `removeSession`

**Returns:** `Session`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `SessionInput!` | **Yes** |  |  |


### `sendOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `id` | `ID` | No |  |  |
| `data` | `OrderInput` | No |  |  |


### `sendOrders`

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `setCheckoutRuleOrder`

**Returns:** `ResponseSetRules`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `String!` | **Yes** |  |  |
| `orderUid` | `String!` | **Yes** |  |  |
| `ruleType` | `String!` | **Yes** |  |  |
| `value` | `JSON!` | **Yes** |  |  |


### `setCheckoutRuleSession`

**Returns:** `ResponseSetRules`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `String!` | **Yes** |  |  |
| `ruleType` | `String!` | **Yes** |  |  |
| `value` | `JSON!` | **Yes** |  |  |


### `shipOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID` | No |  |  |
| `id` | `ID` | No |  |  |
| `data` | `OrderInput` | No |  |  |


### `shipOrders`

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |


### `updateCustomer`

**Returns:** `Customer`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `data` | `CustomerUpdateInput!` | **Yes** |  |  |


### `updateSession`

**Returns:** `Session`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `SessionUpdateInput!` | **Yes** |  |  |


---

## Input Types

Input types used as parameters in queries and mutations.

#### `ActivateDeferredPromotionDataInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `selectBy` | `PromotionSelectionCriteria!` | **Yes** |  |  |
| `selectedGroupIdentifier` | `String` | No |  |  |
| `promotionUid` | `String!` | **Yes** |  |  |
| `skuQuantitySelections` | `[SkuQuantitySelectionInput]` | No |  |  |


#### `ActiveFeeInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `fee` | `ActiveFeeThresholdInput` | No |  |  |
| `total` | `Float` | No |  |  |


#### `ActiveFeeThresholdInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `FeeType!` | **Yes** |  |  |
| `threshold` | `Float` | No |  |  |
| `fee` | `Float` | No |  |  |
| `thresholds` | `[ActiveThresholdInput]` | No |  |  |


#### `ActiveThresholdInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `threshold` | `Float!` | **Yes** |  |  |
| `fee` | `Float!` | **Yes** |  |  |


#### `AutoPopulateCategoryInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `String` | No |  |  |


#### `BannerInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `imagesURL` | `[String]!` | **Yes** |  |  |
| `customerType` | `String` | No |  |  |
| `reference` | `String` | No |  |  |
| `type` | `BannerType!` | **Yes** |  |  |
| `isActive` | `Boolean` | No |  |  |
| `priority` | `Int` | No |  |  |
| `startDate` | `Date!` | **Yes** |  |  |
| `expirationDate` | `Date!` | **Yes** |  |  |
| `segments` | `[String]` | No |  |  |
| `userAgent` | `UserAgentType` | No |  |  |


#### `BannerUpdate`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `imagesURL` | `[String]` | No |  |  |
| `customerType` | `String` | No |  |  |
| `reference` | `String` | No |  |  |
| `type` | `BannerType` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `priority` | `Int` | No |  |  |
| `startDate` | `Date` | No |  |  |
| `expirationDate` | `Date` | No |  |  |
| `segments` | `[String]` | No |  |  |
| `userAgent` | `UserAgentType` | No |  |  |


#### `BundleInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `displayOption` | `BundleDisplayOptionsEnum` | No |  |  |
| `items` | `[String]` | No |  |  |
| `label` | `String` | No |  |  |
| `maxQtyPerSku` | `Int` | No |  |  |
| `maxSkus` | `Int` | No |  |  |
| `minQtyPerSku` | `Int` | No |  |  |
| `minSkus` | `Int` | No |  |  |
| `totalItems` | `Int` | No |  |  |
| `maxTotalQty` | `Int` | No |  |  |
| `minTotalQty` | `Int` | No |  |  |


#### `CartAddFeeDataInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `String!` | **Yes** |  |  |
| `thresholds` | `[ActiveThresholdInput]!` | **Yes** |  |  |


#### `CartProductInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `additionalMeasurementUnits` | `[ProductAdditionalMeasurementInput]` | No |  |  |
| `attributes` | `[String]` | No |  |  |
| `basePrice` | `Float` | No |  |  |
| `brand` | `String` | No |  |  |
| `category` | `String` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `deactivationDate` | `Date` | No |  |  |
| `discount` | `Float` | No |  |  |
| `discounts` | `Float` | No |  |  |
| `divisionsByUnit` | `Int` | No |  |  |
| `extraPackages` | `[PricedProductPackageInput]` | No |  |  |
| `fees` | `[FeeThresholdInput]` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `isPackageRequired` | `Boolean` | No |  |  |
| `linkedConditionalStock` | `LinkedConditionalStockInput` | No |  |  |
| `linkedProducts` | `[String]` | No |  |  |
| `maxQty` | `Int` | No |  |  |
| `maxQtyAlert` | `Int` | No |  |  |
| `minQty` | `Int` | No |  |  |
| `packagePrice` | `Float` | No |  |  |
| `packageType` | `String` | No |  |  |
| `price` | `Float` | No |  |  |
| `promotionalQty` | `Int` | No |  |  |
| `quantity` | `Int!` | **Yes** |  |  |
| `selectedPackage` | `String` | No |  |  |
| `size` | `String` | No |  |  |
| `sku` | `String!` | **Yes** |  |  |
| `subItems` | `[CartProductSubItemInput]` | No |  |  |
| `tags` | `[String]` | No |  |  |
| `totalFee` | `Float` | No |  |  |
| `unitDivision` | `String` | No |  |  |
| `unitPrice` | `Float` | No |  |  |
| `unitsPerPackage` | `Int` | No |  |  |
| `userQty` | `Int` | No |  |  |


#### `CartProductOpInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `sku` | `String!` | **Yes** |  |  |
| `quantity` | `Int!` | **Yes** |  |  |
| `replace` | `Boolean` | No |  |  |
| `referrer` | `String` | No |  |  |
| `subItems` | `[CartProductSubItemInput]` | No |  |  |
| `package` | `String` | No |  |  |


#### `CartProductSubItemInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `items` | `JSON` | No |  |  |
| `quantity` | `Int` | No |  |  |


#### `CartRemoveFeeDataInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `String!` | **Yes** |  |  |


#### `CustomerLocationInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `longitude` | `Float!` | **Yes** |  |  |
| `latitude` | `Float!` | **Yes** |  |  |
| `distanceInMeters` | `Float!` | **Yes** |  |  |


#### `CustomerUpdateInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `phoneNumber` | `PhoneNumberInput` | No |  |  |
| `acceptance` | `Boolean` | No |  |  |
| `address` | `String` | No |  |  |


#### `EndpointInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `url` | `String` | No |  |  |
| `status` | `StorefrontStatus` | No |  |  |


#### `ExtraIdInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `key` | `String` | No |  |  |
| `value` | `String` | No |  |  |


#### `FeeThresholdInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `FeeType!` | **Yes** |  |  |
| `threshold` | `Float!` | **Yes** |  |  |
| `fee` | `Float!` | **Yes** |  |  |


#### `FilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `isActive` | `Boolean` | No |  |  |


#### `FilterOrderInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `sessionUid` | `ID` | No |  |  |
| `status` | `OrderStatus` | No |  |  |
| `startDate` | `Date` | No |  |  |
| `endDate` | `Date` | No |  |  |
| `customerCode` | `String` | No |  |  |
| `storeCode` | `String` | No |  |  |
| `externalRef` | `String` | No |  |  |
| `sequence` | `Float` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `routes` | `[String!]` | No |  |  |
| `dateRangeField` | `OrderDateRangeField` | No |  |  |


#### `FilterProductInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String` | No |  |  |
| `category` | `String` | No |  |  |
| `sku` | `String` | No |  |  |
| `skus` | `[String]` | No |  |  |
| `description` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `customFields` | `JSON` | No |  |  |


#### `FilterStoreInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `name` | `String` | No |  |  |
| `type` | `String` | No |  |  |
| `owner` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `LinkedConditionalStockInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `requiredQuantity` | `Float` | No |  |  |
| `stockPerRequiredQuantity` | `Float` | No |  |  |


#### `OrderData`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `externalOrderUid` | `String` | No |  |  |
| `externalRefNumber` | `String` | No |  |  |
| `externalRefStatus` | `ExternalRefStatus` | No |  |  |
| `externalErrorMessage` | `String` | No |  |  |
| `externalMessage` | `String` | No |  |  |


#### `OrderGroupInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `groupBy` | `[String]` | No |  |  |
| `items` | `[CartProductInput]` | No |  |  |
| `total` | `Float` | No |  |  |


#### `OrderInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `customFields` | `JSON` | No |  |  |
| `expectedDeliveryDate` | `Date` | No |  |  |
| `externalErrorMessage` | `String` | No |  |  |
| `externalMessage` | `String` | No |  |  |
| `externalRef` | `String` | No |  |  |
| `externalRefNumber` | `String` | No |  |  |
| `externalRefStatus` | `ExternalRefStatus` | No |  |  |
| `notes` | `String` | No |  |  |
| `sequence` | `Float` | No |  |  |
| `source` | `String` | No |  |  |
| `originalId` | `String` | No |  |  |


#### `PackagePriceInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String!` | **Yes** |  |  |
| `price` | `Float!` | **Yes** |  |  |
| `basePrice` | `Float` | No |  |  |
| `fees` | `[FeeThresholdInput]` | No |  |  |


#### `PaginationInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `pageNumber` | `Int` | No |  |  |
| `pageSize` | `Int` | No |  |  |


#### `PaginationSkipInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `pageNumber` | `Int` | No |  |  |
| `pageSize` | `Int` | No |  |  |
| `skip` | `Int` | No |  |  |


#### `PayOrderInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `customFields` | `JSON` | No |  |  |
| `expectedDeliveryDate` | `Date` | No |  |  |
| `externalErrorMessage` | `String` | No |  |  |
| `externalMessage` | `String` | No |  |  |
| `externalRef` | `String` | No |  |  |
| `externalRefNumber` | `String` | No |  |  |
| `externalRefStatus` | `ExternalRefStatus` | No |  |  |
| `notes` | `String` | No |  |  |
| `sequence` | `Float` | No |  |  |
| `source` | `String` | No |  |  |
| `paymentInfo` | `JSON` | No |  |  |
| `paymentMethod` | `OrderPaymentMethod!` | **Yes** |  |  |


#### `PhoneNumberInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `number` | `String` | No |  |  |
| `target` | `String` | No |  |  |


#### `PricedProductPackageInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String!` | **Yes** |  |  |
| `label` | `String!` | **Yes** |  |  |
| `quantity` | `Int!` | **Yes** |  |  |
| `price` | `Float!` | **Yes** |  |  |
| `jumpQty` | `Int` | No |  |  |
| `minQty` | `Int` | No |  |  |
| `maxQty` | `Int` | No |  |  |
| `stock` | `Int` | No |  |  |
| `outOfStock` | `Boolean` | No |  |  |
| `basePrice` | `Float` | No |  |  |
| `fees` | `[FeeThresholdInput]` | No |  |  |


#### `ProductAdditionalMeasurementInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `MeasurementTypes!` | **Yes** |  |  |
| `unit` | `MeasurementUnits!` | **Yes** |  |  |
| `value` | `Float!` | **Yes** |  |  |


#### `ProductCategoryInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String!` | **Yes** |  |  |
| `priority` | `Int` | No |  |  |


#### `ProductInputType`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `additionalMeasurementUnits` | `[ProductAdditionalMeasurementInput]` | No |  |  |
| `attributes` | `[String]` | No |  |  |
| `brand` | `String` | No |  |  |
| `bundle` | `BundleInput` | No |  |  |
| `categories` | `[ProductCategoryInput]` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `deactivationDate` | `Date` | No |  |  |
| `divisionsByUnit` | `Int` | No |  |  |
| `extraPackages` | `[ProductPackageInput]` | No |  |  |
| `isHidden` | `Boolean` | No |  |  |
| `jumpQty` | `Int` | No |  |  |
| `layerDown` | `Int` | No |  | Threshold for rounding down to previous complete pallet layer. |
| `layerQty` | `Int` | No |  | The minimum quantity of products a layer should have. |
| `layerUp` | `Int` | No |  | Threshold for rounding up to next complete pallet layer. |
| `linkedConditionalStock` | `LinkedConditionalStockInput` | No |  |  |
| `linkedProducts` | `[String]` | No |  |  |
| `maxQty` | `Int` | No |  |  |
| `maxQtyAlert` | `Int` | No |  |  |
| `minQty` | `Int` | No |  |  |
| `packageType` | `String` | No |  |  |
| `palletDown` | `Int` | No |  | Threshold for rounding down to previous complete pallet. |
| `palletQty` | `Int` | No |  | Maximum capacity of a complete pallet. Sets the upper boundary for pallet-level rounding calculations. |
| `palletUp` | `Int` | No |  | Threshold for rounding up to next complete pallet. |
| `priority` | `Int` | No |  |  |
| `size` | `String` | No |  |  |
| `tags` | `[String]` | No |  |  |
| `unitDivision` | `String` | No |  |  |
| `unitsPerPackage` | `Int` | No |  |  |
| `category` | `ProductCategoryInput!` | **Yes** |  |  |
| `description` | `String!` | **Yes** |  |  |
| `imageURL` | `[String]!` | **Yes** |  |  |
| `isActive` | `Boolean!` | **Yes** |  |  |
| `name` | `String!` | **Yes** |  |  |
| `sku` | `String!` | **Yes** |  |  |


#### `ProductPackageInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String!` | **Yes** |  |  |
| `quantity` | `Int!` | **Yes** |  |  |
| `label` | `String!` | **Yes** |  |  |
| `jumpQty` | `Int` | No |  |  |
| `minQty` | `Int` | No |  |  |
| `maxQty` | `Int` | No |  |  |


#### `SearchFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `attributes` | `[String]` | No |  |  |
| `promotions` | `Boolean` | No |  |  |
| `categories` | `[String]` | No |  |  |
| `brands` | `[String]` | No |  |  |


#### `SessionAttributionInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `referrer` | `SessionAttributionReferrer` | No |  |  |
| `skus` | `[String]` | No |  |  |


#### `SessionInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `attributions` | `[SessionAttributionInput]` | No |  |  |
| `code` | `String!` | **Yes** |  |  |
| `customFields` | `JSON` | No |  |  |
| `type` | `String` | No |  |  |
| `validate` | `Boolean!` | **Yes** |  |  |
| `validateBy` | `String!` | **Yes** |  |  |
| `workflow` | `SessionWorkflowInput` | No |  |  |
| `extraIds` | `[ExtraIdInput]` | No |  |  |


#### `SessionUpdateInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `customFields` | `JSON` | No |  |  |
| `lockedStoreCode` | `String!` | **Yes** |  |  |
| `segments` | `[String]` | No |  |  |


#### `SessionWorkflowInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String!` | **Yes** |  |  |
| `userUid` | `String!` | **Yes** |  |  |
| `channel` | `String` | No |  |  |
| `channelUid` | `String` | No |  |  |
| `token` | `String` | No |  |  |
| `triggerId` | `String` | No |  |  |


#### `SkuQuantitySelectionInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `sku` | `String!` | **Yes** |  |  |
| `quantity` | `Int!` | **Yes** |  |  |


#### `SortOptionsExtraInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `properties` | `[SortPropertyExtraInput]` | No |  |  |


#### `SortOptionsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `properties` | `[SortPropertyInput]` | No |  |  |


#### `SortPropertyExtraInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `property` | `SortByExtra!` | **Yes** |  |  |
| `direction` | `SortDirection` | No |  |  |


#### `SortPropertyInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `property` | `SortBy!` | **Yes** |  |  |
| `direction` | `SortDirection` | No |  |  |


#### `UpdateBannersPriorityInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `id` | `ID!` | **Yes** |  |  |
| `newPosition` | `Int!` | **Yes** |  |  |


#### `UpdateProductInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `additionalMeasurementUnits` | `[ProductAdditionalMeasurementInput]` | No |  |  |
| `attributes` | `[String]` | No |  |  |
| `brand` | `String` | No |  |  |
| `bundle` | `BundleInput` | No |  |  |
| `categories` | `[ProductCategoryInput]` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `deactivationDate` | `Date` | No |  |  |
| `divisionsByUnit` | `Int` | No |  |  |
| `extraPackages` | `[ProductPackageInput]` | No |  |  |
| `isHidden` | `Boolean` | No |  |  |
| `jumpQty` | `Int` | No |  |  |
| `layerDown` | `Int` | No |  | Threshold for rounding down to previous complete pallet layer. |
| `layerQty` | `Int` | No |  | The minimum quantity of products a layer should have. |
| `layerUp` | `Int` | No |  | Threshold for rounding up to next complete pallet layer. |
| `linkedConditionalStock` | `LinkedConditionalStockInput` | No |  |  |
| `linkedProducts` | `[String]` | No |  |  |
| `maxQty` | `Int` | No |  |  |
| `maxQtyAlert` | `Int` | No |  |  |
| `minQty` | `Int` | No |  |  |
| `packageType` | `String` | No |  |  |
| `palletDown` | `Int` | No |  | Threshold for rounding down to previous complete pallet. |
| `palletQty` | `Int` | No |  | Maximum capacity of a complete pallet. Sets the upper boundary for pallet-level rounding calculations. |
| `palletUp` | `Int` | No |  | Threshold for rounding up to next complete pallet. |
| `priority` | `Int` | No |  |  |
| `size` | `String` | No |  |  |
| `tags` | `[String]` | No |  |  |
| `unitDivision` | `String` | No |  |  |
| `unitsPerPackage` | `Int` | No |  |  |
| `category` | `ProductCategoryInput` | No |  |  |
| `description` | `String` | No |  |  |
| `imageURL` | `[String]` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `name` | `String` | No |  |  |
| `sku` | `String` | No |  |  |


---

## Return Types

Object types returned by queries and mutations.

#### `ActiveFee`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `fee` | `ActiveFeeThreshold` |  |  |
| `total` | `Float` |  |  |


#### `ActiveFeeThreshold`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `FeeType` |  |  |
| `threshold` | `Float` |  |  |
| `fee` | `Float` |  |  |
| `thresholds` | `[ActiveThreshold]` |  |  |


#### `ActivePromotion`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `appliedItems` | `AppliedItems` |  |  |
| `complexConfiguration` | `ComplexPromotionConfigurationType` |  |  |
| `count` | `Int` |  |  |
| `countBySku` | `JSON` |  |  |
| `freeGoods` | `[FreeGoods]` |  |  |
| `itemsConsumed` | `JSON` | ~~Use 'appliedItems' instead~~ |  |
| `label` | `String` |  |  |
| `pricePerItem` | `Float` |  |  |
| `promotion` | `Promotion` |  |  |
| `source` | `String` |  |  |


#### `ActivePromotions`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `appliedItems` | `AppliedItems` |  |  |
| `complexConfiguration` | `ComplexPromotionConfigurationType` |  |  |
| `count` | `Int` |  |  |
| `countBySku` | `JSON` |  |  |
| `freeGoods` | `[FreeGoods]` |  |  |
| `itemsConsumed` | `JSON` | ~~Use 'appliedItems' instead~~ |  |
| `label` | `String` |  |  |
| `pricePerItem` | `Float` |  |  |
| `promotion` | `Promotion` |  |  |
| `source` | `String` |  |  |
| `promotions` | `Promotion` |  |  |


#### `ActiveThreshold`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `threshold` | `Float` |  |  |
| `fee` | `Float` |  |  |


#### `AppliedItems`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `consumed` | `[SkuQuantity]` |  |  |
| `count` | `Int` |  |  |


#### `Attribution`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `referrer` | `String` |  |  |
| `skus` | `[String]` |  |  |


#### `AutoPopulateCategory`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `CategoryPopulateTypes` |  |  |


#### `Banner`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID` |  |  |
| `imagesURL` | `[String]` |  |  |
| `customerType` | `String` |  |  |
| `reference` | `String` |  |  |
| `type` | `BannerType` |  |  |
| `isActive` | `Boolean` |  |  |
| `priority` | `Int` |  |  |
| `startDate` | `Date` |  |  |
| `expirationDate` | `Date` |  |  |
| `segments` | `[String]` |  |  |
| `userAgent` | `UserAgentType` |  |  |


#### `Brand`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `name` | `String` |  |  |


#### `BudgetConfig`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `skipBudgetPreAllocation` | `Boolean` |  |  |


#### `BundleType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `displayOption` | `BundleDisplayOptionsEnum` |  |  |
| `items` | `[String]` |  |  |
| `label` | `String` |  |  |
| `maxQtyPerSku` | `Int` |  |  |
| `maxSkus` | `Int` |  |  |
| `minQtyPerSku` | `Int` |  |  |
| `minSkus` | `Int` |  |  |
| `totalItems` | `Int` |  |  |
| `maxTotalQty` | `Int` |  |  |
| `minTotalQty` | `Int` |  |  |


#### `BundlesExtraType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `customFields` | `JSON` |  |  |
| `name` | `String` |  |  |
| `price` | `Float` |  |  |
| `sku` | `String` |  |  |
| `stock` | `Int` |  |  |
| `description` | `String` |  |  |
| `packageType` | `String` |  |  |
| `unitsPerPackage` | `Int` |  |  |


#### `Cart`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID!` |  |  |
| `items` | `[CartProduct]` |  |  |
| `total` | `Float` |  |  |
| `subtotal` | `Float` |  |  |
| `totalFee` | `Float` |  |  |
| `compensations` | `Float` |  |  |
| `activePromotions` | `[ActivePromotion]` |  |  |
| `deferredPromotions` | `[DeferredPromotion]` |  |  |
| `status` | `CartStatus` |  |  |
| `warnings` | `[String]` |  |  |
| `customFields` | `JSON` |  |  |
| `groups` | `[CartGroup]` |  |  |
| `activeFees` | `[ActiveFee]` |  |  |
| `notifications` | `[CartNotification]` |  |  |
| `attributions` | `[Attribution]` |  |  |
| `discountsByPromotion` | `JSON` |  |  |
| `createdAt` | `Date` |  |  |
| `updatedAt` | `Date` |  |  |


#### `CartConditionCheckLinkedProducts`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `message` | `String` |  |  |
| `isActive` | `Boolean` |  |  |


#### `CartConditionPendingAdditionalMeasurement`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `MeasurementTypes` |  |  |
| `unit` | `MeasurementUnits` |  |  |
| `quantity` | `Float` |  |  |
| `message` | `String` |  |  |
| `isActive` | `Boolean` |  |  |


#### `CartConditionPendingMaxAmount`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `quantity` | `Float` |  |  |
| `message` | `String` |  |  |
| `isActive` | `Boolean` |  |  |


#### `CartConditionPendingMaxQty`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `quantity` | `Int` |  |  |
| `message` | `String` |  |  |
| `isActive` | `Boolean` |  |  |


#### `CartConditionPendingMinAmount`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `quantity` | `Float` |  |  |
| `message` | `String` |  |  |
| `isActive` | `Boolean` |  |  |
| `replaceQuantityWithField` | `ReplaceableCheckoutRuleQuantityFieldEnum` |  |  |


#### `CartConditionPendingMinQty`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `quantity` | `Int` |  |  |
| `message` | `String` |  |  |
| `isActive` | `Boolean` |  |  |


#### `CartConditionPendingUserValidation`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `message` | `String` |  |  |
| `sku` | `[String]` |  |  |
| `attribute` | `String` |  |  |
| `isActive` | `Boolean` |  |  |


#### `CartGroup`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `groupBy` | `[String]` |  |  |
| `items` | `[CartProduct]` |  |  |
| `subtotal` | `Float` |  |  |
| `total` | `Float` |  |  |


#### `CartNotification`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `CartNotificationType` |  |  |
| `showed` | `Boolean` |  |  |
| `title` | `String` |  |  |
| `message` | `String` |  |  |
| `products` | `[CartNotificationProduct]` |  |  |


#### `CartNotificationProduct`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `sku` | `String` |  |  |
| `name` | `String` |  |  |
| `description` | `String` |  |  |
| `imageURL` | `[String]` |  |  |


#### `CartProduct`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `additionalMeasurementUnits` | `[ProductAdditionalMeasurement]` |  |  |
| `additionalMeasurementUnit` | `[ProductAdditionalMeasurement]` | ~~Use additionalMeasurementUnits instead.~~ |  |
| `attributes` | `[String]` |  |  |
| `brand` | `String` |  |  |
| `bundle` | `BundleType` |  |  |
| `bundlesExtra` | `[BundlesExtraType]` |  |  |
| `categories` | `[String]` |  |  |
| `category` | `String` |  |  |
| `customFields` | `JSON` |  |  |
| `deactivationDate` | `Date` |  |  |
| `divisionsByUnit` | `Int` |  |  |
| `id` | `ID!` |  |  |
| `imageURL` | `[String]` |  |  |
| `isActive` | `Boolean!` |  |  |
| `isHidden` | `Boolean` |  |  |
| `jumpQty` | `Int` |  |  |
| `layerDown` | `Int` |  |  |
| `layerQty` | `Int` |  |  |
| `layerUp` | `Int` |  |  |
| `linkedConditionalStock` | `LinkedConditionalStockType` |  |  |
| `linkedProducts` | `[String]` |  |  |
| `maxQty` | `Int` |  |  |
| `maxQtyAlert` | `Int` |  |  |
| `minQty` | `Int` |  |  |
| `packageType` | `String` |  |  |
| `palletDown` | `Int` |  |  |
| `palletQty` | `Int` |  |  |
| `palletUp` | `Int` |  |  |
| `priority` | `Int` |  |  |
| `size` | `String` |  |  |
| `sku` | `String!` |  |  |
| `tags` | `[String]` |  |  |
| `unitDivision` | `String` |  |  |
| `unitsPerPackage` | `Int` |  |  |
| `basePrice` | `Float` |  |  |
| `extraPackages` | `[PricedProductPackage]` |  |  |
| `fees` | `[FeeThreshold]` |  |  |
| `hasDynamicPrice` | `Boolean` |  |  |
| `isPackageRequired` | `Boolean` |  |  |
| `outOfStock` | `Boolean` |  |  |
| `packagePrice` | `Float` |  |  |
| `price` | `Float` |  |  |
| `stock` | `Int` |  |  |
| `unitPrice` | `Float` |  |  |
| `description` | `String` |  |  |
| `discount` | `Float` | ~~use 'discounts' instead~~ |  |
| `discounts` | `Float` |  |  |
| `name` | `String` |  |  |
| `promotionalQty` | `Int` |  |  |
| `promotions` | `[Promotion]` |  |  |
| `quantity` | `Int!` |  |  |
| `totalFee` | `Float` |  |  |
| `userQty` | `Int` |  |  |
| `subItems` | `[CartProductSubItemType]` |  |  |
| `package` | `PricedProductPackage` |  |  |


#### `CartProductSubItemType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `items` | `JSON` |  |  |
| `quantity` | `Int` |  |  |
| `hash` | `String` |  |  |


#### `CartWarningCheckReturnables`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `message` | `String` |  |  |
| `sku` | `[String]` |  |  |
| `attribute` | `String` |  |  |
| `isActive` | `Boolean` |  |  |


#### `Catalog`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `category` | `String` |  | Product category |
| `parentId` | `String` |  | ParentId of the category |
| `priority` | `Int` |  | category priority |
| `productsPrices` | `[Product]` |  | Product list with prices |
| `subCategories` | `[CatalogCategory]` |  |  |


#### `CatalogCategory`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `String!` |  |  |
| `name` | `String` |  |  |
| `parentId` | `String` |  |  |
| `priority` | `Int` |  |  |
| `productsPrices` | `[Product]` |  |  |


#### `Category`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `createdAt` | `Date` |  |  |
| `id` | `ID!` |  |  |
| `imageURL` | `[String]` |  |  |
| `isActive` | `Boolean!` |  |  |
| `name` | `String` |  |  |
| `parentId` | `ID` |  |  |
| `priority` | `Int` |  |  |
| `updatedAt` | `Date` |  |  |
| `autoPopulate` | `AutoPopulateCategory` |  |  |


#### `CheckOrderResult`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `executeResult` | `Boolean` |  |  |
| `result` | `JSON` |  |  |
| `name` | `String` |  |  |


#### `CheckoutRulesByTypeConfig`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `String` |  |  |
| `checkoutRules` | `ConfigCheckoutRules` |  |  |


#### `ComplexPromotionBuysGroup`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `items` | `[ComplexPromotionBuysProduct]` |  |  |
| `type` | `ComplexPromotionTypes` |  |  |
| `identifier` | `String` |  |  |


#### `ComplexPromotionBuysProduct`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `ComplexPromotionTypes` |  |  |
| `sku` | `String` |  |  |
| `quantity` | `Int` |  |  |
| `amount` | `Float` |  |  |
| `productPackage` | `String` |  |  |


#### `ComplexPromotionConfigurationType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `selectBy` | `PromotionSelectionCriteria` |  |  |
| `selectedGroupIdentifier` | `String` |  |  |
| `skuQuantitySelections` | `[SkuQuantitySelection]` |  |  |


#### `ComplexPromotionGetsGroup`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `items` | `[ComplexPromotionGetsProduct]` |  |  |
| `type` | `ComplexPromotionTypes` |  |  |
| `identifier` | `String` |  |  |
| `maxSkuSelectionQuantity` | `Int` |  |  |


#### `ComplexPromotionGetsProduct`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `ComplexPromotionTypes` |  |  |
| `sku` | `String` |  |  |
| `quantity` | `Int` |  |  |
| `amount` | `Float` |  |  |
| `productPackage` | `String` |  |  |
| `percentage` | `Float` |  |  |


#### `ConfigBanner`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `enabled` | `Boolean` |  |  |
| `maximumActive` | `Int` |  |  |


#### `ConfigBooleanFilter`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `active` | `Boolean` |  |  |


#### `ConfigCart`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `precisionDigits` | `Int` |  |  |
| `quantityAdjustment` | `QuantityAdjustmentMode` |  | QuantityAdjustmentMode indicates how the pallet optimization should be performed. |


#### `ConfigCheckoutRules`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `cartConditionPendingMinAmount` | `CartConditionPendingMinAmount` |  |  |
| `cartConditionPendingMaxAmount` | `CartConditionPendingMaxAmount` |  |  |
| `cartConditionPendingMinQty` | `CartConditionPendingMinQty` |  |  |
| `cartConditionPendingMaxQty` | `CartConditionPendingMaxQty` |  |  |
| `cartConditionPendingMinAdditionalMeasurement` | `CartConditionPendingAdditionalMeasurement` |  |  |
| `cartConditionPendingMaxAdditionalMeasurement` | `CartConditionPendingAdditionalMeasurement` |  |  |
| `cartConditionPendingUserValidation` | `CartConditionPendingUserValidation` |  |  |
| `cartWarningCheckReturnables` | `CartWarningCheckReturnables` |  |  |
| `cartConditionCheckLinkedProducts` | `CartConditionCheckLinkedProducts` |  |  |
| `orderDailyLimit` | `OrderDailyLimit` |  |  |


#### `ConfigFee`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `FeeType!` |  |  |
| `entity` | `FeeEntities!` |  |  |


#### `ConfigFilters`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `attributes` | `[String]` |  |  |
| `promotions` | `ConfigBooleanFilter` |  |  |
| `categories` | `ConfigBooleanFilter` |  |  |
| `brands` | `ConfigBooleanFilter` |  |  |


#### `ConfigGrouper`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `active` | `Boolean` |  |  |
| `session` | `[String]` |  |  |
| `product` | `[String]` |  |  |


#### `ConfigGroupers`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `cart` | `ConfigGrouper` |  |  |
| `order` | `ConfigGrouper` |  |  |


#### `ConfigSplitter`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `active` | `Boolean` |  |  |
| `maxProduct` | `Int` |  |  |


#### `ConfigSplitters`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `order` | `ConfigSplitter` |  |  |


#### `ConfigStock`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `StockType!` |  |  |
| `threshold` | `ConfigStockThreshold` |  |  |
| `timer` | `ConfigStockTimer` |  |  |
| `key` | `String` |  |  |
| `hideOutOfStock` | `Boolean` |  |  |
| `returnStock` | `ReturnStock` |  |  |
| `prioritizeProductsInStock` | `Boolean` |  |  |
| `enabled` | `Boolean` | ~~Use stock.type instead~~ |  |
| `stockThreshold` | `Int` | ~~Use stock.threshold instead~~ |  |


#### `ConfigStockThreshold`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `lowWarning` | `ConfigStockWarning` |  |  |
| `criticalLowWarning` | `ConfigStockWarning` |  |  |


#### `ConfigStockTimer`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `expirationMinutes` | `Int` |  |  |


#### `ConfigStockWarning`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `String` |  |  |
| `warningMessage` | `String` |  |  |
| `quantity` | `Int` |  |  |
| `enabled` | `Boolean` |  |  |


#### `Configuration`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `banner` | `ConfigBanner` |  |  |
| `budget` | `BudgetConfig` |  |  |
| `cart` | `ConfigCart` |  |  |
| `checkoutRules` | `ConfigCheckoutRules` |  |  |
| `checkoutRulesByType` | `[CheckoutRulesByTypeConfig]` |  |  |
| `emptyFees` | `Boolean` |  |  |
| `fees` | `[ConfigFee]` |  |  |
| `filters` | `ConfigFilters` |  |  |
| `forceConfig` | `ForceConfig` |  |  |
| `groupers` | `ConfigGroupers` |  |  |
| `i18n` | `I18n` |  |  |
| `notifications` | `[NotificationType]` |  |  |
| `orderFinalStatuses` | `[OrderStatus]` |  |  |
| `priceless` | `Boolean` |  |  |
| `promotions` | `PromotionConfig` |  |  |
| `recommendedProducts` | `recommendedProductsType` |  |  |
| `segments` | `SegmentsConfig` |  |  |
| `sessionTtl` | `Int` |  |  |
| `showRecommendations` | `Boolean` |  |  |
| `sortFields` | `SortFieldsConfig` |  |  |
| `splitters` | `ConfigSplitters` |  |  |
| `stock` | `ConfigStock` |  |  |
| `topLineProtection` | `JSON` | ~~Legacy configuration not used~~ |  |
| `useStores` | `Boolean` |  |  |
| `webview` | `Webview` | ~~Frontend configuration is not used in the storefront~~ |  |
| `workflow` | `JSON` |  |  |


#### `Customer`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `acceptance` | `Boolean` |  |  |
| `acceptanceDate` | `Date` |  |  |
| `address` | `String` |  |  |
| `categories` | `[String]` |  |  |
| `city` | `String` |  |  |
| `code` | `String` |  |  |
| `country` | `String` |  |  |
| `creditAmount` | `Float` |  |  |
| `customFields` | `JSON` |  |  |
| `deactivationDate` | `Date` |  |  |
| `email` | `String` |  |  |
| `extraCode` | `[String]` |  |  |
| `hasCredit` | `Boolean` |  |  |
| `lockedStoreCode` | `String` |  |  |
| `minimumOrderAmount` | `Float` |  |  |
| `name` | `String` |  |  |
| `periodicity` | `Float` |  |  |
| `phoneNumber` | `[String]` |  |  |
| `region` | `String` |  |  |
| `routes` | `[String]` |  |  |
| `ruleType` | `String` |  |  |
| `state` | `String` |  |  |
| `taxId` | `String` |  |  |
| `visitDate` | `Date` |  |  |
| `visitDays` | `[VisitDay]` |  |  |
| `zipCode` | `String` |  |  |
| `createdAt` | `Date` |  |  |
| `id` | `ID!` |  |  |
| `isActive` | `Boolean` |  |  |
| `type` | `String!` |  |  |
| `updatedAt` | `Date` |  |  |
| `location` | `CustomerLocation` |  |  |


#### `CustomerBuysType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `value` | `CustomerBuysValueType` |  |  |
| `items` | `[String]` |  |  |
| `groups` | `[ComplexPromotionBuysGroup]` |  |  |


#### `CustomerBuysValueType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `String` |  |  |
| `unit` | `String` |  |  |
| `quantity` | `Int` |  |  |
| `amount` | `Float` |  |  |
| `minimum` | `Int` |  |  |
| `minimumAmount` | `Float` |  |  |
| `productPackage` | `String` |  |  |


#### `CustomerGetsType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `value` | `CustomerGetsValueType` |  |  |
| `items` | `[String]` |  |  |
| `itemsExtra` | `[PromotionProduct]` |  |  |
| `groups` | `[ComplexPromotionGetsGroup]` |  |  |


#### `CustomerGetsValueType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `quantity` | `Int` |  |  |
| `percentage` | `Float` |  |  |
| `cash` | `Float` |  |  |
| `amount` | `Float` |  |  |
| `productPackage` | `String` |  |  |


#### `CustomerLocation`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `coordinates` | `[Float]` |  |  |
| `distanceInMeters` | `Float` |  |  |


#### `CustomerSegmentsResponse`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `segmentType` | `SegmentsTypes!` |  |  |
| `segments` | `[SegmentMembership!]!` |  |  |


#### `CustomerType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `customerUid` | `[ID]` |  |  |
| `type` | `[String]` |  |  |
| `customerCode` | `[String]` |  |  |
| `storeCode` | `[String]` |  |  |
| `segments` | `[String]` |  |  |


#### `DeferredPromotion`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `count` | `Int` |  |  |
| `promotion` | `Promotion` |  |  |
| `complexConfiguration` | `ComplexPromotionConfigurationType` |  |  |


#### `Endpoint`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `url` | `String` |  |  |
| `status` | `StorefrontStatus` |  |  |


#### `ExtraId`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `key` | `String` |  |  |
| `value` | `String` |  |  |


#### `FakePromotion`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID` |  |  |
| `isActive` | `Boolean` |  |  |
| `startDate` | `Date` |  |  |
| `endDate` | `Date` |  |  |
| `priority` | `Int` |  |  |
| `type` | `PromotionTypes` |  |  |


#### `FeeThreshold`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `FeeType` |  |  |
| `threshold` | `Float` |  |  |
| `fee` | `Float` |  |  |


#### `ForceColumnConfig`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `field` | `String!` |  |  |
| `label` | `String!` |  |  |
| `type` | `ForceTypes!` |  |  |
| `format` | `String` |  |  |
| `mobilePosition` | `Int` |  |  |


#### `ForceConfig`
> YaloForceConfiguration to config columns content and naming.

| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `main` | `[ForceColumnConfig!]!` |  |  |
| `details` | `[ForceColumnConfig!]!` |  |  |


#### `FreeGoods`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `consumed` | `[SkuQuantity]` |  |  |
| `count` | `Int` |  |  |
| `items` | `[SkuQuantity]` |  |  |


#### `I18n`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `language` | `String` |  |  |
| `currencyFormat` | `String` |  |  |
| `currencySymbol` | `String` |  |  |
| `currencyCode` | `String` |  |  |
| `currencyDisplay` | `String` |  |  |
| `country` | `String` |  |  |
| `timezone` | `String` |  |  |


#### `Journey`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID` |  |  |
| `experienceId` | `String` |  |  |
| `audienceId` | `String` |  |  |
| `include` | `[String]` |  |  |
| `exclude` | `[String]` |  |  |
| `startDate` | `Date` |  |  |
| `endDate` | `Date` |  |  |


#### `LinkData`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `url` | `String` |  |  |
| `type` | `LinkType` |  |  |


#### `LinkedConditionalStockType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `requiredQuantity` | `Float` |  |  |
| `stockPerRequiredQuantity` | `Float` |  |  |


#### `LoyaltyPoints`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `total` | `Float` |  |  |
| `historicalData` | `[LoyaltyPointsHistoricalData]` |  |  |


#### `LoyaltyPointsHistoricalData`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `date` | `Date` |  |  |
| `points` | `Float` |  |  |
| `reason` | `String` |  |  |


#### `NotificationType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `abTestingSlug` | `String` |  |  |
| `botSlug` | `String` |  |  |
| `customerType` | `String` |  |  |
| `enabled` | `Boolean` |  |  |
| `notificationAtHours` | `[Int]` |  |  |
| `notificationOnDays` | `[NotificationDaysEnum]` |  |  |
| `priority` | `Int` |  |  |
| `studioAccountId` | `String` |  |  |
| `templateId` | `String` |  |  |
| `thresholdInMinutes` | `Int` |  |  |
| `type` | `NotificationTypeEnum` |  |  |
| `workflow` | `NotificationWorkflow` |  |  |


#### `NotificationWorkflow`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `channel` | `String` |  |  |
| `ng` | `Boolean` |  |  |
| `token` | `String` |  |  |
| `triggerId` | `String` |  |  |
| `workflowId` | `String` |  |  |
| `workflowName` | `String` |  |  |


#### `Order`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID` |  |  |
| `customerCode` | `String` |  |  |
| `storeCode` | `String` |  |  |
| `sessionUid` | `ID` |  |  |
| `customerUid` | `ID` |  |  |
| `cartUid` | `ID` |  |  |
| `items` | `[CartProduct]` |  |  |
| `status` | `OrderStatus` |  |  |
| `processedAt` | `Date` |  |  |
| `externalRef` | `String` |  |  |
| `parentOrderUid` | `ID` |  |  |
| `notes` | `String` |  |  |
| `externalRefNumber` | `String` |  |  |
| `externalRefStatus` | `ExternalRefStatus` |  |  |
| `externalErrorMessage` | `String` |  |  |
| `externalMessage` | `String` |  |  |
| `source` | `String` |  |  |
| `customFields` | `JSON` |  |  |
| `total` | `Float` |  |  |
| `totalFee` | `Float` |  |  |
| `compensations` | `Float` |  |  |
| `sequence` | `Int` |  |  |
| `checkoutRules` | `[OrderCheckoutRule]` |  |  |
| `postOrderCheck` | `JSON` |  |  |
| `preOrderCheck` | `JSON` |  |  |
| `activePromotions` | `[ActivePromotions]` |  |  |
| `createdAt` | `Date` |  |  |
| `updatedAt` | `Date` |  |  |
| `groups` | `[OrderGroup]` |  |  |
| `activeFees` | `[ActiveFee]` |  |  |
| `expectedDeliveryDate` | `Date` |  |  |
| `paymentMethod` | `OrderPaymentMethod` |  |  |
| `paymentInfo` | `JSON` |  |  |
| `attributions` | `[Attribution]` |  |  |
| `discountsByPromotion` | `JSON` |  |  |
| `customer` | `OrderCustomer` |  |  |
| `originalId` | `String` |  |  |


#### `OrderCheckoutRule`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `String` |  |  |
| `ruleType` | `String` |  |  |
| `value` | `JSON` |  |  |


#### `OrderCustomer`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `acceptance` | `Boolean` |  |  |
| `acceptanceDate` | `Date` |  |  |
| `address` | `String` |  |  |
| `categories` | `[String]` |  |  |
| `city` | `String` |  |  |
| `code` | `String` |  |  |
| `country` | `String` |  |  |
| `creditAmount` | `Float` |  |  |
| `customFields` | `JSON` |  |  |
| `deactivationDate` | `Date` |  |  |
| `email` | `String` |  |  |
| `extraCode` | `[String]` |  |  |
| `hasCredit` | `Boolean` |  |  |
| `lockedStoreCode` | `String` |  |  |
| `minimumOrderAmount` | `Float` |  |  |
| `name` | `String` |  |  |
| `periodicity` | `Float` |  |  |
| `phoneNumber` | `[String]` |  |  |
| `region` | `String` |  |  |
| `routes` | `[String]` |  |  |
| `ruleType` | `String` |  |  |
| `state` | `String` |  |  |
| `taxId` | `String` |  |  |
| `visitDate` | `Date` |  |  |
| `visitDays` | `[VisitDay]` |  |  |
| `zipCode` | `String` |  |  |
| `createdAt` | `Date` |  |  |
| `id` | `ID!` |  |  |
| `isActive` | `Boolean` |  |  |
| `type` | `String!` |  |  |
| `updatedAt` | `Date` |  |  |


#### `OrderDailyLimit`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `quantity` | `Int` |  |  |
| `message` | `String` |  |  |
| `isActive` | `Boolean` |  |  |


#### `OrderGroup`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `groupBy` | `[String]` |  |  |
| `items` | `[CartProduct]` |  |  |
| `total` | `Float` |  |  |


#### `OwnerInfo`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `slug` | `String` |  |  |


#### `PackagePrice`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `name` | `String!` |  |  |
| `price` | `Float!` |  |  |
| `basePrice` | `Float` |  |  |
| `fees` | `[FeeThreshold]` |  |  |


#### `PaginatedStores`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `stores` | `[Store]` |  |  |
| `pagination` | `Pagination` |  |  |


#### `Pagination`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `total` | `Int` |  |  |
| `totalPages` | `Int` |  |  |
| `pageNumber` | `Int` |  |  |
| `pageSize` | `Int` |  |  |
| `nextPage` | `Int` |  |  |
| `previousPage` | `Int` |  |  |
| `hasNextPage` | `Boolean` |  |  |


#### `PricedProductPackage`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `name` | `String!` |  |  |
| `label` | `String!` |  |  |
| `quantity` | `Int!` |  |  |
| `price` | `Float!` |  |  |
| `jumpQty` | `Int` |  |  |
| `minQty` | `Int` |  |  |
| `maxQty` | `Int` |  |  |
| `stock` | `Int` |  |  |
| `outOfStock` | `Boolean` |  |  |
| `basePrice` | `Float` |  |  |
| `fees` | `[FeeThreshold]` |  |  |


#### `Product`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `additionalMeasurementUnits` | `[ProductAdditionalMeasurement]` |  |  |
| `additionalMeasurementUnit` | `[ProductAdditionalMeasurement]` | ~~Use additionalMeasurementUnits instead.~~ |  |
| `attributes` | `[String]` |  |  |
| `brand` | `String` |  |  |
| `bundle` | `BundleType` |  |  |
| `bundlesExtra` | `[BundlesExtraType]` |  |  |
| `categories` | `[String]` |  |  |
| `category` | `String` |  |  |
| `customFields` | `JSON` |  |  |
| `deactivationDate` | `Date` |  |  |
| `divisionsByUnit` | `Int` |  |  |
| `id` | `ID!` |  |  |
| `imageURL` | `[String]` |  |  |
| `isActive` | `Boolean!` |  |  |
| `isHidden` | `Boolean` |  |  |
| `jumpQty` | `Int` |  |  |
| `layerDown` | `Int` |  |  |
| `layerQty` | `Int` |  |  |
| `layerUp` | `Int` |  |  |
| `linkedConditionalStock` | `LinkedConditionalStockType` |  |  |
| `linkedProducts` | `[String]` |  |  |
| `maxQty` | `Int` |  |  |
| `maxQtyAlert` | `Int` |  |  |
| `minQty` | `Int` |  |  |
| `packageType` | `String` |  |  |
| `palletDown` | `Int` |  |  |
| `palletQty` | `Int` |  |  |
| `palletUp` | `Int` |  |  |
| `priority` | `Int` |  |  |
| `size` | `String` |  |  |
| `sku` | `String!` |  |  |
| `tags` | `[String]` |  |  |
| `unitDivision` | `String` |  |  |
| `unitsPerPackage` | `Int` |  |  |
| `basePrice` | `Float` |  |  |
| `extraPackages` | `[PricedProductPackage]` |  |  |
| `fees` | `[FeeThreshold]` |  |  |
| `hasDynamicPrice` | `Boolean` |  |  |
| `isPackageRequired` | `Boolean` |  |  |
| `outOfStock` | `Boolean` |  |  |
| `packagePrice` | `Float` |  |  |
| `price` | `Float` |  |  |
| `stock` | `Int` |  |  |
| `unitPrice` | `Float` |  |  |
| `createdAt` | `Date` |  |  |
| `customerType` | `String` |  |  |
| `description` | `String!` |  |  |
| `name` | `String!` |  |  |
| `promotions` | `[Promotion]` |  |  |
| `updatedAt` | `Date` |  |  |


#### `ProductAdditionalMeasurement`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `MeasurementTypes!` |  |  |
| `unit` | `MeasurementUnits!` |  |  |
| `value` | `Float!` |  |  |


#### `ProductPackage`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `name` | `String!` |  |  |
| `quantity` | `Int!` |  |  |
| `label` | `String!` |  |  |
| `jumpQty` | `Int` |  |  |
| `minQty` | `Int` |  |  |
| `maxQty` | `Int` |  |  |


#### `ProductSearchReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `products` | `[Product]` |  |  |
| `pagination` | `Pagination` |  |  |


#### `PromotedProductsReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `products` | `[Product]` |  |  |
| `pagination` | `Pagination` |  |  |


#### `Promotion`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `appliesToAllProducts` | `Boolean` |  |  |
| `id` | `ID` |  |  |
| `code` | `String` |  |  |
| `customFields` | `JSON` |  |  |
| `customer` | `CustomerType!` |  |  |
| `customerBuys` | `CustomerBuysType!` |  |  |
| `customerGets` | `CustomerGetsType` |  |  |
| `description` | `String` |  |  |
| `endDate` | `Date!` |  |  |
| `isActive` | `Boolean` |  |  |
| `label` | `String` |  |  |
| `name` | `String` |  |  |
| `priority` | `Int!` |  |  |
| `ranking` | `Int` |  |  |
| `startDate` | `Date!` |  |  |
| `type` | `PromotionTypes!` |  |  |
| `usageLimit` | `UsageLimitType` |  |  |
| `validSegments` | `Boolean` |  |  |


#### `PromotionConfig`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `autoAdd` | `Boolean` |  |  |
| `disableFreeGoodsAsDiscount` | `Boolean` |  |  |
| `disableVolumeStacking` | `Boolean` |  |  |
| `discountFromStock` | `Boolean` |  |  |
| `enabled` | `Boolean` |  |  |
| `limitTotalPromotions` | `Boolean` |  |  |
| `maximumActive` | `Int` |  |  |


#### `PromotionProduct`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `additionalMeasurementUnits` | `[ProductAdditionalMeasurement]` |  |  |
| `additionalMeasurementUnit` | `[ProductAdditionalMeasurement]` | ~~Use additionalMeasurementUnits instead.~~ |  |
| `attributes` | `[String]` |  |  |
| `brand` | `String` |  |  |
| `bundle` | `BundleType` |  |  |
| `bundlesExtra` | `[BundlesExtraType]` |  |  |
| `categories` | `[String]` |  |  |
| `category` | `String` |  |  |
| `customFields` | `JSON` |  |  |
| `deactivationDate` | `Date` |  |  |
| `divisionsByUnit` | `Int` |  |  |
| `id` | `ID!` |  |  |
| `imageURL` | `[String]` |  |  |
| `isActive` | `Boolean!` |  |  |
| `isHidden` | `Boolean` |  |  |
| `jumpQty` | `Int` |  |  |
| `layerDown` | `Int` |  |  |
| `layerQty` | `Int` |  |  |
| `layerUp` | `Int` |  |  |
| `linkedConditionalStock` | `LinkedConditionalStockType` |  |  |
| `linkedProducts` | `[String]` |  |  |
| `maxQty` | `Int` |  |  |
| `maxQtyAlert` | `Int` |  |  |
| `minQty` | `Int` |  |  |
| `packageType` | `String` |  |  |
| `palletDown` | `Int` |  |  |
| `palletQty` | `Int` |  |  |
| `palletUp` | `Int` |  |  |
| `priority` | `Int` |  |  |
| `size` | `String` |  |  |
| `sku` | `String!` |  |  |
| `tags` | `[String]` |  |  |
| `unitDivision` | `String` |  |  |
| `unitsPerPackage` | `Int` |  |  |
| `basePrice` | `Float` |  |  |
| `extraPackages` | `[PricedProductPackage]` |  |  |
| `fees` | `[FeeThreshold]` |  |  |
| `hasDynamicPrice` | `Boolean` |  |  |
| `isPackageRequired` | `Boolean` |  |  |
| `outOfStock` | `Boolean` |  |  |
| `packagePrice` | `Float` |  |  |
| `price` | `Float` |  |  |
| `stock` | `Int` |  |  |
| `unitPrice` | `Float` |  |  |
| `name` | `String` |  |  |
| `description` | `String` |  |  |
| `customerType` | `String` |  |  |
| `createdAt` | `Date` |  |  |
| `updatedAt` | `Date` |  |  |
| `promotions` | `[FakePromotion]` |  |  |


#### `ResponseAcceptedRule`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `ruleType` | `String` |  |  |
| `accepted` | `Boolean` |  |  |


#### `ResponseRules`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `ruleType` | `String` |  |  |
| `data` | `[JSON]` |  |  |


#### `ResponseSessionRule`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `rules` | `[Rules]` |  |  |
| `resultCheck` | `Boolean` |  |  |


#### `ResponseSetRules`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `ruleType` | `String` |  |  |
| `value` | `JSON` |  |  |


#### `ReturnStock`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `enabled` | `Boolean` |  |  |
| `statuses` | `[OrderStatus]` |  |  |


#### `Rules`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `ruleType` | `String` |  |  |
| `blocks` | `Boolean` |  |  |
| `checked` | `Boolean` |  |  |
| `data` | `JSON` |  |  |


#### `SegmentMembership`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `String!` |  |  |
| `belongs` | `Boolean!` |  |  |


#### `SegmentsConfig`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `SegmentsTypes` |  |  |


#### `Session`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID` |  |  |
| `customerUid` | `String` |  |  |
| `customerAlias` | `String` |  |  |
| `customer` | `SessionCustomer` |  |  |
| `cartUid` | `ID` |  |  |
| `configuration` | `Configuration` |  |  |
| `configurationHash` | `String` |  |  |
| `workflow` | `SessionWorkflow` |  |  |
| `startedAt` | `Date` |  |  |
| `finishedAt` | `Date` |  |  |
| `status` | `SessionStatus` |  |  |
| `customFields` | `JSON` |  |  |
| `isBlockedToOrder` | `Boolean` |  |  |
| `checkoutRules` | `[SessionCheckoutRule]` |  |  |
| `banners` | `[Banner]` |  |  |
| `journeys` | `[Journey]` |  |  |
| `segments` | `[String]` |  |  |
| `attributions` | `[SessionAttribution]` |  |  |
| `extraIds` | `[ExtraId]` |  |  |
| `owner` | `String` |  |  |
| `ownerInfo` | `OwnerInfo` |  |  |
| `createdAt` | `Date` |  |  |
| `updatedAt` | `Date` |  |  |
| `type` | `String` |  |  |


#### `SessionAttribution`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `referrer` | `SessionAttributionReferrer` |  |  |
| `skus` | `[String]` |  |  |


#### `SessionCheckoutRule`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `String` |  |  |
| `value` | `JSON` |  |  |


#### `SessionCustomer`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `acceptance` | `Boolean` |  |  |
| `acceptanceDate` | `Date` |  |  |
| `address` | `String` |  |  |
| `categories` | `[String]` |  |  |
| `city` | `String` |  |  |
| `code` | `String` |  |  |
| `country` | `String` |  |  |
| `creditAmount` | `Float` |  |  |
| `customFields` | `JSON` |  |  |
| `deactivationDate` | `Date` |  |  |
| `email` | `String` |  |  |
| `extraCode` | `[String]` |  |  |
| `hasCredit` | `Boolean` |  |  |
| `lockedStoreCode` | `String` |  |  |
| `minimumOrderAmount` | `Float` |  |  |
| `name` | `String` |  |  |
| `periodicity` | `Float` |  |  |
| `phoneNumber` | `[String]` |  |  |
| `region` | `String` |  |  |
| `routes` | `[String]` |  |  |
| `ruleType` | `String` |  |  |
| `state` | `String` |  |  |
| `taxId` | `String` |  |  |
| `visitDate` | `Date` |  |  |
| `visitDays` | `[VisitDay]` |  |  |
| `zipCode` | `String` |  |  |
| `type` | `String!` |  |  |
| `isActive` | `Boolean` | ~~Not used but left for compatibility~~ |  |


#### `SessionWorkflow`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `name` | `String` |  |  |
| `channel` | `String` |  |  |
| `channelUid` | `String` |  |  |
| `userUid` | `String` |  |  |


#### `SkuQuantity`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `sku` | `String` |  |  |
| `quantity` | `Int` |  |  |
| `packageName` | `String` |  |  |


#### `SkuQuantitySelection`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `sku` | `String!` |  |  |
| `quantity` | `Int!` |  |  |


#### `SortFieldsConfig`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `order` | `[SortOrderProperty]` |  |  |


#### `Store`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID!` |  |  |
| `code` | `String!` |  |  |
| `name` | `String!` |  |  |
| `phoneNumbers` | `[String]` |  |  |
| `email` | `String` |  |  |
| `region` | `String` |  |  |
| `type` | `String` |  |  |
| `address` | `String` |  |  |
| `stockHandling` | `Boolean` |  |  |
| `extensions` | `JSON` |  |  |
| `owner` | `String` |  |  |
| `storePrice` | `Boolean` |  |  |
| `minimumOrderAmount` | `Float` |  |  |
| `isActive` | `Boolean` |  |  |
| `location` | `StoreLocation` |  |  |
| `createdAt` | `Date` |  |  |
| `updatedAt` | `Date` |  |  |
| `customFields` | `JSON` |  |  |


#### `StoreLocation`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `coordinates` | `[Float]` |  |  |
| `distanceInMeters` | `Float` |  |  |


#### `Storefront`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID` |  |  |
| `name` | `String!` |  |  |
| `status` | `StorefrontStatus` |  |  |
| `customFields` | `JSON` |  |  |
| `endpoints` | `[Endpoint]` |  |  |
| `owner` | `String!` |  |  |
| `templateID` | `ID` |  |  |
| `configuration` | `Configuration` |  |  |
| `createdAt` | `Date` |  |  |
| `updatedAt` | `Date` |  |  |
| `productive` | `Boolean` |  |  |


#### `SuggestedItemReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `additionalMeasurementUnits` | `[ProductAdditionalMeasurement]` |  |  |
| `additionalMeasurementUnit` | `[ProductAdditionalMeasurement]` | ~~Use additionalMeasurementUnits instead.~~ |  |
| `attributes` | `[String]` |  |  |
| `brand` | `String` |  |  |
| `bundle` | `BundleType` |  |  |
| `bundlesExtra` | `[BundlesExtraType]` |  |  |
| `categories` | `[String]` |  |  |
| `category` | `String` |  |  |
| `customFields` | `JSON` |  |  |
| `deactivationDate` | `Date` |  |  |
| `divisionsByUnit` | `Int` |  |  |
| `id` | `ID!` |  |  |
| `imageURL` | `[String]` |  |  |
| `isActive` | `Boolean!` |  |  |
| `isHidden` | `Boolean` |  |  |
| `jumpQty` | `Int` |  |  |
| `layerDown` | `Int` |  |  |
| `layerQty` | `Int` |  |  |
| `layerUp` | `Int` |  |  |
| `linkedConditionalStock` | `LinkedConditionalStockType` |  |  |
| `linkedProducts` | `[String]` |  |  |
| `maxQty` | `Int` |  |  |
| `maxQtyAlert` | `Int` |  |  |
| `minQty` | `Int` |  |  |
| `packageType` | `String` |  |  |
| `palletDown` | `Int` |  |  |
| `palletQty` | `Int` |  |  |
| `palletUp` | `Int` |  |  |
| `priority` | `Int` |  |  |
| `size` | `String` |  |  |
| `sku` | `String!` |  |  |
| `tags` | `[String]` |  |  |
| `unitDivision` | `String` |  |  |
| `unitsPerPackage` | `Int` |  |  |
| `basePrice` | `Float` |  |  |
| `extraPackages` | `[PricedProductPackage]` |  |  |
| `fees` | `[FeeThreshold]` |  |  |
| `hasDynamicPrice` | `Boolean` |  |  |
| `isPackageRequired` | `Boolean` |  |  |
| `outOfStock` | `Boolean` |  |  |
| `packagePrice` | `Float` |  |  |
| `price` | `Float` |  |  |
| `stock` | `Int` |  |  |
| `unitPrice` | `Float` |  |  |
| `createdAt` | `Date` |  |  |
| `customerType` | `String` |  |  |
| `description` | `String!` |  |  |
| `name` | `String!` |  |  |
| `promotions` | `[Promotion]` |  |  |
| `updatedAt` | `Date` |  |  |
| `quantity` | `Int` |  |  |


#### `Token`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `key` | `String` |  |  |
| `secret` | `String` |  |  |


#### `UsageLimitType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `budgetId` | `ID` |  |  |
| `perCustomer` | `Int` |  |  |
| `perOrder` | `Int` |  |  |


#### `Webview`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `logo` | `String` |  |  |


#### `recommendedProductsType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `suggestedItems` | `SuggestedItemsTypeEnum` |  |  |
| `frequentlyBoughtTogether` | `FrequentlyBoughtTogetherTypeEnum` |  |  |
| `prefillCart` | `PrefillCartTypeEnum` |  |  |


---

## Enums

#### `BannerType`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CATEGORY` |  |  |
| `CATEGORY_NAV` |  |  |
| `EXTERNAL_LINK` |  |  |
| `GENERAL` |  |  |
| `PARENT_CATEGORY` |  |  |
| `PRODUCT` |  |  |
| `SUBCATEGORY_NAV` |  |  |


#### `BundleDisplayOptionsEnum`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `NAME` |  |  |
| `DESCRIPTION` |  |  |
| `UNITS_PER_PACKAGE` |  |  |


#### `CartNotificationType`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `FREE_PRODUCT` |  |  |
| `WARNING` |  |  |
| `DISCOUNT` |  |  |
| `ALERT` |  |  |


#### `CartStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CREATED` |  |  |
| `IN_PROGRESS` |  |  |
| `CANCELLED` |  |  |
| `CHECK_OUT` |  |  |
| `ERROR` |  |  |
| `EXPIRED` |  |  |


#### `CategoryPopulateTypes`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `PROMOTIONS` |  |  |


#### `ComplexPromotionTypes`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `AMOUNT` |  |  |
| `DIRECT_PERCENTAGE` |  |  |
| `MIXED` |  |  |
| `PERCENTAGE` |  |  |
| `QUANTITY` |  |  |
| `QUANTITY_SELECTION` |  |  |


#### `ExternalRefStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `PROCESSING` |  |  |
| `CONFIRMED` |  |  |
| `REJECTED` |  |  |
| `ERROR` |  |  |
| `TIMEOUT` |  |  |


#### `FavoriteStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `FAVORITE` |  |  |
| `NONE` |  |  |


#### `FeeEntities`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `NONE` |  |  |
| `PRODUCT` |  |  |


#### `FeeType`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `SERVICE` |  |  |
| `MATERIAL` |  |  |
| `PERCEPTION` |  |  |


#### `ForceTypes`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `number` |  |  |
| `amount` |  |  |
| `date` |  |  |
| `string` |  |  |


#### `FrequentlyBoughtTogetherTypeEnum`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `ML` |  |  |
| `NONE` |  |  |


#### `LinkType`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `COMMERCE` |  |  |
| `EXTERNAL` |  |  |


#### `MeasurementTypes`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `WEIGHT` |  |  |


#### `MeasurementUnits`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `T` |  |  |
| `KG` |  |  |
| `G` |  |  |
| `MG` |  |  |


#### `NotificationDaysEnum`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `MONDAY` |  |  |
| `TUESDAY` |  |  |
| `WEDNESDAY` |  |  |
| `THURSDAY` |  |  |
| `FRIDAY` |  |  |
| `SATURDAY` |  |  |
| `SUNDAY` |  |  |


#### `NotificationTypeEnum`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `ABANDONED_CART` |  |  |
| `ORDER_REMINDER` |  |  |
| `SESSION_CREATED` |  |  |
| `AUTHENTICATION_NEEDED` |  |  |
| `STOCK_AVAILABLE` |  |  |


#### `OrderDateRangeField`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `createdAt` |  |  |
| `updatedAt` |  |  |
| `expectedDeliveryDate` |  |  |


#### `OrderPaymentMethod`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `POINTS` |  |  |
| `YALO_PAGO` |  |  |
| `CREDIT` |  |  |


#### `OrderStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CANCELLED` |  |  |
| `CONFIRMED` |  |  |
| `CREATED` |  |  |
| `DELIVERED` |  |  |
| `EDITED` |  |  |
| `ERROR` |  |  |
| `IN_PROGRESS` |  |  |
| `PAID` |  |  |
| `PROCESSED` |  |  |
| `SENT` |  |  |
| `SHIPPED` |  |  |
| `SUGGESTED` |  |  |
| `WAITING_CALLBACK` |  |  |


#### `PrefillCartTypeEnum`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `ML` |  |  |
| `LAST_ORDER` |  |  |
| `NONE` |  |  |


#### `ProductAttributes`
> This ProductAttributes is not used at the moment to allow sending the values in lower or upper case

| Value | Deprecated | Description |
|-------|-----------|-------------|
| `ALCOHOL` |  |  |
| `RETURNABLE` |  |  |


#### `PromotionSelectionCriteria`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CUSTOMER_SELECTION` |  |  |
| `DEFAULT_GROUP_ID` |  |  |
| `QUANTITY_SELECTION` |  |  |
| `REFUSED` |  |  |


#### `PromotionTypes`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `COMBO` |  |  |
| `DIRECT` |  |  |
| `VOLUME` |  |  |
| `TOTAL` |  |  |
| `COMPLEX` |  |  |


#### `QuantityAdjustmentMode`
> QuantityAdjustmentMode indicates the product quantity adjustment behavior
when interacting with the cart and its products.
- NONE: Skip product quantity adjustment entirely - no validation or rounding is performed
- VALIDATE: Validate that the quantity matches the adjusted value - returns an error if they differ (default)
- ROUND: Automatically adjust the quantity to the adjusted value if they differ

| Value | Deprecated | Description |
|-------|-----------|-------------|
| `NONE` |  |  |
| `VALIDATE` |  |  |
| `ROUND` |  |  |


#### `ReplaceableCheckoutRuleQuantityFieldEnum`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `MINIMUM_AMOUNT` |  |  |


#### `SegmentsTypes`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `BIG_QUERY` |  |  |
| `CDP` |  |  |
| `NONE` |  |  |


#### `SessionAttributionReferrer`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CAMPAIGN` |  |  |
| `REMINDER` |  |  |


#### `SessionStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `ACTIVE` |  |  |
| `FINISHED` |  |  |
| `EXPIRED` |  |  |
| `ERROR` |  |  |


#### `SortBy`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CREATED_AT` |  |  |
| `UPDATED_AT` |  |  |


#### `SortByExtra`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CREATED_AT` |  |  |
| `UPDATED_AT` |  |  |
| `PRIORITY` |  |  |


#### `SortDirection`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `ASC` |  |  |
| `DESC` |  |  |


#### `SortOrderProperty`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `createdAt` |  |  |
| `updatedAt` |  |  |
| `expectedDeliveryDate` |  |  |


#### `StockType`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `INFINITE` |  |  |
| `SELF_MANAGED` |  |  |
| `REAL_TIME` |  |  |


#### `StorefrontStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CREATING` |  |  |
| `RUNNING` |  |  |
| `PUBLISH` |  |  |
| `DRAFT` |  |  |


#### `SuggestedItemsTypeEnum`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `ML` |  |  |
| `NONE` |  |  |


#### `UserAgentType`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `ANDROID` |  |  |
| `IOS` |  |  |
| `WEB` |  |  |
| `ALL` |  |  |


#### `VisitDay`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `SUN` |  |  |
| `MON` |  |  |
| `TUE` |  |  |
| `WED` |  |  |
| `THU` |  |  |
| `FRI` |  |  |
| `SAT` |  |  |

