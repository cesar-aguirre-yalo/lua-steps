# GraphQL Admin API Reference

**Endpoint:** `https://storefront-admin.yalochat.dev/v3/admin/storefronts`  
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

### `addOn`

**Returns:** `AddOn`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `addOnTypesInfo`

**Returns:** `[AddOnTypesInfo]`

**Parameters:**

_No parameters_


### `addOns`

**Returns:** `[AddOn]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `filter` | `AddOnInputUpdate` | No |  |  |
| `pagination` | `PaginationInput` | No |  |  |


### `banner`

**Returns:** `Banner`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `banners`

**Returns:** `[Banner]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterInput` | No |  |  |


### `cart`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `carts`

**Returns:** `[Cart]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |
| `pagination` | `PaginationInput` | No |  |  |


### `catalogByCustomerType`

**Returns:** `[Product]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  | Storefront name |
| `customerType` | `String` | No |  | Customer type |
| `pagination` | `PaginationSkipInput` | No |  | Pagination |
| `skipAddon` | `Boolean` | No | false | Skip Addons call |
| `skus` | `[String]` | No |  | Skus to filter |
| `stockAsInfinite` | `Boolean` | No | false | Handle stock as if were infinite |


### `categories` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getCategories' query instead

**Returns:** `[Category]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterCategoryInput` | No |  |  |


### `category`

**Returns:** `Category`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `checkIn`

**Returns:** `CheckIn`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `checkOrder`

**Returns:** `CheckOrder`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `checkOrders`

**Returns:** `[CheckOrder]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |


### `checkoutRule`

**Returns:** `CheckoutRule`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `checkoutRules`

**Returns:** `[CheckoutRule]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |


### `cleanUpProcess`

**Returns:** `CleanUpProcess`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `id` | `ID!` | **Yes** |  |  |


### `customer`

**Returns:** `Customer`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `customers` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getCustomers' query instead

**Returns:** `[Customer]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterCustomerInput` | No |  |  |


### `getCategories`

**Returns:** `CategoriesReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterCategoryInput` | No |  |  |


### `getCheckIns`

**Returns:** `CheckInsReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `CheckInFilterInput` | No |  |  |


### `getCustomers`

**Returns:** `CustomersReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterCustomerInput` | No |  |  |
| `sort` | `SortOptionsInput` | No |  |  |


### `getOrders`

**Returns:** `OrdersReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterOrderInput` | No |  |  |
| `sort` | `SortOptionsInput` | No |  |  |


### `getPrices`

**Returns:** `PricesReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterPriceInput` | No |  |  |


### `getProducts`

**Returns:** `ProductsReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterProductInput` | No |  |  |


### `getPromotions`

**Returns:** `PromotionsReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `PromotionFilterInput` | No |  |  |


### `getPromotionsByCustomerCode`

**Returns:** `[Promotion]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `customerCode` | `String!` | **Yes** |  |  |


### `getSalesRepresentatives`

**Returns:** `SalesRepresentativesReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `SalesRepFilterInput` | No |  |  |


### `getStocks`

**Returns:** `StocksReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterStocksInput` | No |  |  |


### `getStorefronts`

**Returns:** `StorefrontsReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterStorefrontInput` | No |  |  |
| `sort` | `SortOptionsInput` | No |  |  |


### `getStores`

**Returns:** `PaginatedStores`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterStoreInput` | No |  |  |


### `getVisitPlans`

**Returns:** `VisitPlansReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `VisitPlanFilterInput` | No |  |  |


### `locateNearbyCustomers`

**Returns:** `CustomersReturned`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `location` | `NearbyCustomersLocationInput!` | **Yes** |  |  |
| `filter` | `NearbyCustomersFilterInput` | No |  |  |
| `pagination` | `PaginationInput` | No |  |  |


### `order`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `orders` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getOrders' query instead

**Returns:** `[Order]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterOrderInput` | No |  |  |


### `price`

**Returns:** `Price`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `prices` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getPrices' query instead

**Returns:** `[Price]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |


### `process`

**Returns:** `Process`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `processId` | `ID!` | **Yes** |  |  |


### `processes`

**Returns:** `[Process]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterProcessInput` | No |  |  |
| `sort` | `SortProcessOptionsInput` | No |  |  |


### `product`

**Returns:** `ProductBase`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `products` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getProducts' query instead

**Returns:** `[ProductBase]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterProductInput` | No |  |  |


### `promotion`

**Returns:** `Promotion`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `promotions` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getPromotions' query instead

**Returns:** `[Promotion]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |
| `pagination` | `PaginationInput` | No |  |  |


### `randomCustomer`

**Returns:** `Customer`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |


### `salesRepresentative`

**Returns:** `SalesRep`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `schemasInfo`

**Returns:** `SchemasInfo`

**Parameters:**

_No parameters_


### `session`

**Returns:** `Session`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `sessions`

**Returns:** `[Session]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterSessionInput` | No |  |  |


### `stock`

**Returns:** `Stock`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `stocks` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getStocks' query instead

**Returns:** `[Stock]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |


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


### `storefronts` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getStorefronts' query instead

**Returns:** `[Storefront]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterStorefrontInput` | No |  |  |


### `stores` ~~[DEPRECATED]~~

> **Deprecated:** Use the 'getStores' query instead

**Returns:** `[Store]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `pagination` | `PaginationInput` | No |  |  |
| `filter` | `FilterStoreInput` | No |  |  |


### `validateProductRecommendations`

**Returns:** `[ValidProductRecommendation]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `customerCode` | `String!` | **Yes** |  |  |
| `skus` | `[String!]!` | **Yes** |  |  |


### `visitPlan`

**Returns:** `VisitPlan`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


---

## Mutations

### `assignCategories`

**Returns:** `[Category]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |


### `cleanUpPromotions`

**Returns:** `CleanUpProcess!`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `CleanUpPromotionsInput` | No |  |  |


### `cleanUpPromotionsForAllStorefronts`

**Returns:** `CleanUpProcess!`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `data` | `CleanUpPromotionsInput` | No |  |  |


### `createAddOn`

**Returns:** `AddOn`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `AddOnInput!` | **Yes** |  |  |


### `createBanner`

**Returns:** `Banner`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `BannerInput!` | **Yes** |  |  |


### `createCart`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `CartInputType!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `createCategories`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `callbackUrl` | `String` | No |  |  |
| `deactivate` | `Boolean` | No | false |  |
| `emailToNotify` | `String` | No |  |  |
| `executionId` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `fileURL` | `String` | No |  |  |
| `flowId` | `String` | No |  |  |
| `hideProcess` | `Boolean` | No |  |  |
| `skipBulkImport` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[CategoryBulkInput]` | No |  |  |


### `createCategory`

**Returns:** `Category`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `CategoryInput!` | **Yes** |  |  |


### `createCheckIn`

**Returns:** `CheckIn`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `CheckInInput!` | **Yes** |  |  |


### `createCheckOrder`

**Returns:** `CheckOrder`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `CheckOrderInput!` | **Yes** |  |  |


### `createCheckoutRule`

**Returns:** `CheckoutRule`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `CheckoutRuleInput!` | **Yes** |  |  |


### `createCustomer`

**Returns:** `Customer`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `CustomerCreateInputType!` | **Yes** |  |  |


### `createCustomers`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `callbackUrl` | `String` | No |  |  |
| `deactivate` | `Boolean` | No | false |  |
| `emailToNotify` | `String` | No |  |  |
| `executionId` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `fileURL` | `String` | No |  |  |
| `flowId` | `String` | No |  |  |
| `hideProcess` | `Boolean` | No |  |  |
| `skipBulkImport` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[CustomerCreateInputType]` | No |  |  |


### `createOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `OrderInput!` | **Yes** |  |  |


### `createPrice`

**Returns:** `Price`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `PriceInputType!` | **Yes** |  |  |


### `createPrices`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `callbackUrl` | `String` | No |  |  |
| `deactivate` | `Boolean` | No | false |  |
| `emailToNotify` | `String` | No |  |  |
| `executionId` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `fileURL` | `String` | No |  |  |
| `flowId` | `String` | No |  |  |
| `hideProcess` | `Boolean` | No |  |  |
| `skipBulkImport` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[PriceInputType]` | No |  |  |


### `createProduct`

**Returns:** `ProductBase`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `ProductInputType!` | **Yes** |  |  |


### `createProducts`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `callbackUrl` | `String` | No |  |  |
| `deactivate` | `Boolean` | No | false |  |
| `emailToNotify` | `String` | No |  |  |
| `executionId` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `fileURL` | `String` | No |  |  |
| `flowId` | `String` | No |  |  |
| `hideProcess` | `Boolean` | No |  |  |
| `skipBulkImport` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[ProductInputType]` | No |  |  |


### `createPromotion`

**Returns:** `Promotion`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `PromotionInput!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `createPromotions`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `callbackUrl` | `String` | No |  |  |
| `deactivate` | `Boolean` | No | false |  |
| `emailToNotify` | `String` | No |  |  |
| `executionId` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `fileURL` | `String` | No |  |  |
| `flowId` | `String` | No |  |  |
| `hideProcess` | `Boolean` | No |  |  |
| `skipBulkImport` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[PromotionInput]` | No |  |  |


### `createSalesRepresentative`

**Returns:** `SalesRep`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `SalesRepInput!` | **Yes** |  |  |


### `createSalesRepresentatives`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `callbackUrl` | `String` | No |  |  |
| `deactivate` | `Boolean` | No | false |  |
| `emailToNotify` | `String` | No |  |  |
| `executionId` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `fileURL` | `String` | No |  |  |
| `flowId` | `String` | No |  |  |
| `hideProcess` | `Boolean` | No |  |  |
| `skipBulkImport` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[SalesRepresentativeBulkInput]` | No |  |  |


### `createSession`

**Returns:** `Session`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `SessionInput!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `createStock`

**Returns:** `Stock`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `StockInput!` | **Yes** |  |  |


### `createStocks`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `callbackUrl` | `String` | No |  |  |
| `deactivate` | `Boolean` | No | false |  |
| `emailToNotify` | `String` | No |  |  |
| `executionId` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `fileURL` | `String` | No |  |  |
| `flowId` | `String` | No |  |  |
| `hideProcess` | `Boolean` | No |  |  |
| `skipBulkImport` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[StockInput]` | No |  |  |


### `createStore`

**Returns:** `Store`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `StoreInput!` | **Yes** |  |  |


### `createStorefront`

**Returns:** `Storefront`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `data` | `StorefrontInput!` | **Yes** |  |  |


### `createStores`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `callbackUrl` | `String` | No |  |  |
| `deactivate` | `Boolean` | No | false |  |
| `emailToNotify` | `String` | No |  |  |
| `executionId` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `fileURL` | `String` | No |  |  |
| `flowId` | `String` | No |  |  |
| `hideProcess` | `Boolean` | No |  |  |
| `skipBulkImport` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[StoreInput]` | No |  |  |


### `createVisitPlan`

**Returns:** `VisitPlan`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `VisitPlanInput!` | **Yes** |  |  |


### `createVisitPlans`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `callbackUrl` | `String` | No |  |  |
| `deactivate` | `Boolean` | No | false |  |
| `emailToNotify` | `String` | No |  |  |
| `executionId` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `fileURL` | `String` | No |  |  |
| `flowId` | `String` | No |  |  |
| `hideProcess` | `Boolean` | No |  |  |
| `skipBulkImport` | `Boolean` | No | false |  |
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[VisitPlanBulkInput]` | No |  |  |


### `disablePromotion`

**Returns:** `Promotion`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `enablePromotion`

**Returns:** `Promotion`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `enqueueProcess`

**Returns:** `BulkImportResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `processId` | `ID` | No |  |  |


### `expireSessions`

**Returns:** `[ExpireSessions]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String` | No |  |  |


### `forgottenCartSessions`

**Returns:** `[RemindedSessions]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String` | No |  |  |
| `customerUid` | `String` | No |  |  |
| `sessionUid` | `String` | No |  |  |


### `migrateStockStorefronts`

**Returns:** `[StorefrontMigrationResult]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `id` | `ID` | No |  |  |
| `name` | `String` | No |  |  |


### `removeAddOn`

**Returns:** `AddOn`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeBanner`

**Returns:** `Banner`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeCacheSession`

**Returns:** `RemoveCacheResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `sessionUid` | `String!` | **Yes** |  |  |


### `removeCart`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `removeCategory`

**Returns:** `Category`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeCheckIn`

**Returns:** `CheckIn`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeCheckOrder`

**Returns:** `CheckOrder`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeCheckoutRule`

**Returns:** `CheckoutRule`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeCustomer`

**Returns:** `Customer`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeExpiredSessions`

**Returns:** `[RemovedSessionCarts]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String` | No |  |  |


### `removeOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removePrice`

**Returns:** `Price`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeProduct`

**Returns:** `ProductBase`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removePromotion`

**Returns:** `Promotion`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removePromotionHouseKeeping`

**Returns:** `Promotion`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeSalesRepresentative`

**Returns:** `SalesRep`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeSession`

**Returns:** `Session`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `removeStock`

**Returns:** `Stock`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeStore`

**Returns:** `Store`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `removeStorefront`

**Returns:** `Storefront`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `id` | `ID` | No |  |  |
| `name` | `String` | No |  |  |


### `removeVisitPlan`

**Returns:** `VisitPlan`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |


### `triggerCustomerEvents`

**Returns:** `EventsTriggererResponse`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |


### `triggerStorefrontsCustomerEvents`

**Returns:** `EventsTriggererResponse`

**Parameters:**

_No parameters_


### `updateAddOn`

**Returns:** `AddOn`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `AddOnInputUpdate!` | **Yes** |  |  |


### `updateBanner`

**Returns:** `Banner`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `BannerUpdate!` | **Yes** |  |  |


### `updateBannersPriority`

**Returns:** `[Banner]`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `data` | `[UpdateBannersPriorityInput]!` | **Yes** |  |  |


### `updateCart`

**Returns:** `Cart`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `CartInputType!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `updateCategory`

**Returns:** `Category`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `CategoryUpdateInput!` | **Yes** |  |  |


### `updateCheckIn`

**Returns:** `CheckIn`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `CheckInUpdateInput!` | **Yes** |  |  |


### `updateCheckOrder`

**Returns:** `CheckOrder`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `CheckOrderUpdate!` | **Yes** |  |  |


### `updateCheckoutRule`

**Returns:** `CheckoutRule`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `CheckoutRuleInput!` | **Yes** |  |  |


### `updateCustomer`

**Returns:** `Customer`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `CustomerUpdateInputType!` | **Yes** |  |  |


### `updateOrder`

**Returns:** `Order`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `OrderUpdate!` | **Yes** |  |  |


### `updatePrice`

**Returns:** `Price`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `UpdatePriceInput!` | **Yes** |  |  |


### `updateProduct`

**Returns:** `ProductBase`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `UpdateProductInput!` | **Yes** |  |  |


### `updatePromotion`

**Returns:** `Promotion`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `PromotionUpdate!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `updateSalesRepresentative`

**Returns:** `SalesRep`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `SalesRepresentativeUpdateInput!` | **Yes** |  |  |


### `updateSession`

**Returns:** `Session`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `SessionUpdate!` | **Yes** |  |  |
| `houseKeeping` | `Boolean` | No |  |  |


### `updateStock`

**Returns:** `Stock`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `UpdateStockInput!` | **Yes** |  |  |


### `updateStore`

**Returns:** `Store`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `UpdateStoreInput!` | **Yes** |  |  |


### `updateStorefront`

**Returns:** `Storefront`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `id` | `ID` | No |  |  |
| `name` | `String` | No |  |  |
| `data` | `UpdateStorefrontInput!` | **Yes** |  |  |


### `updateVisitPlan`

**Returns:** `VisitPlan`

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `storefrontName` | `String!` | **Yes** |  |  |
| `id` | `ID!` | **Yes** |  |  |
| `data` | `VisitPlanUpdateInput!` | **Yes** |  |  |


---

## Input Types

Input types used as parameters in queries and mutations.

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


#### `AddOnConfigInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `url` | `String!` | **Yes** |  |  |
| `method` | `AddOnMethod` | No |  |  |
| `authMethod` | `AddOnAuthMethod` | No |  |  |
| `token` | `String` | No |  |  |
| `headers` | `JSON` | No |  |  |
| `body` | `JSON` | No |  |  |
| `tokenParamName` | `String` | No |  |  |
| `customFields` | `JSON` | No |  |  |


#### `AddOnConfigInputUpdate`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `url` | `String` | No |  |  |
| `method` | `AddOnMethod` | No |  |  |
| `authMethod` | `AddOnAuthMethod` | No |  |  |
| `token` | `String` | No |  |  |
| `headers` | `JSON` | No |  |  |
| `body` | `JSON` | No |  |  |
| `tokenParamName` | `String` | No |  |  |
| `customFields` | `JSON` | No |  |  |


#### `AddOnInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `AddOnTypes!` | **Yes** |  |  |
| `flavor` | `String!` | **Yes** |  |  |
| `config` | `AddOnConfigInput!` | **Yes** |  |  |
| `callback` | `JSON` | No |  |  |
| `executionTime` | `AddOnExecutionTime` | No | INSTEAD |  |


#### `AddOnInputUpdate`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `AddOnTypes` | No |  |  |
| `flavor` | `String` | No |  |  |
| `config` | `AddOnConfigInputUpdate` | No |  |  |
| `status` | `AddOnStatus` | No |  |  |
| `callback` | `JSON` | No |  |  |
| `executionTime` | `AddOnExecutionTime` | No |  |  |


#### `AutoPopulateCategoryInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `CategoryPopulateTypes` | No |  |  |


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


#### `BudgetConfigFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `skipBudgetPreAllocation` | `Boolean` | No |  |  |


#### `BudgetConfigInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `skipBudgetPreAllocation` | `Boolean` | No | false |  |


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


#### `BusinessHoursInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `businessStartTime` | `BusinessTimeInput` | No |  |  |
| `businessEndTime` | `BusinessTimeInput` | No |  |  |


#### `BusinessTimeInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `hours` | `Int` | No |  |  |
| `minutes` | `Int` | No |  |  |


#### `CartConditionCheckLinkedProductsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `message` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CartConditionPendingAdditionalMeasurementInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `MeasurementTypes` | No |  |  |
| `unit` | `MeasurementUnits` | No |  |  |
| `quantity` | `Float` | No |  |  |
| `message` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CartConditionPendingMaxAmountInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `quantity` | `Float` | No |  |  |
| `message` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CartConditionPendingMaxQtyInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `quantity` | `Int` | No |  |  |
| `message` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CartConditionPendingMinAmountInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `quantity` | `Float` | No |  |  |
| `message` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `replaceQuantityWithField` | `ReplaceableCheckoutRuleQuantityFieldEnum` | No |  |  |


#### `CartConditionPendingMinQtyInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `quantity` | `Int` | No |  |  |
| `message` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CartConditionPendingUserValidationInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `message` | `String` | No |  |  |
| `sku` | `[String]` | No |  |  |
| `attribute` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CartGroupInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `groupBy` | `[String]` | No |  |  |
| `items` | `[CartProductInput]` | No |  |  |
| `subtotal` | `Float` | No |  |  |
| `total` | `Float` | No |  |  |


#### `CartInputType`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `activeFees` | `[ActiveFeeInput]` | No |  |  |
| `compensations` | `Float` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `groups` | `[CartGroupInput]` | No |  |  |
| `items` | `[CartProductInput]` | No |  |  |
| `status` | `CartStatus` | No |  |  |
| `subtotal` | `Float` | No |  |  |
| `total` | `Float` | No |  |  |
| `totalFee` | `Float` | No |  |  |


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


#### `CartWarningCheckReturnablesInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `message` | `String` | No |  |  |
| `sku` | `[String]` | No |  |  |
| `attribute` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CategoryBulkInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `imageURL` | `[String]` | No |  |  |
| `isActive` | `Boolean!` | **Yes** |  |  |
| `isHidden` | `Boolean` | No |  |  |
| `name` | `String!` | **Yes** |  |  |
| `parentName` | `String` | No |  |  |
| `priority` | `Int` | No |  |  |
| `autoPopulate` | `AutoPopulateCategoryInput` | No |  |  |


#### `CategoryInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `imageURL` | `[String]` | No |  |  |
| `isActive` | `Boolean!` | **Yes** |  |  |
| `isHidden` | `Boolean` | No |  |  |
| `name` | `String!` | **Yes** |  |  |
| `parentId` | `ID` | No |  |  |
| `priority` | `Int` | No |  |  |
| `autoPopulate` | `AutoPopulateCategoryInput` | No |  |  |


#### `CategoryUpdateInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `imageURL` | `[String]` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `isHidden` | `Boolean` | No |  |  |
| `name` | `String` | No |  |  |
| `parentId` | `ID` | No |  |  |
| `priority` | `Int` | No |  |  |
| `autoPopulate` | `AutoPopulateCategoryInput` | No |  |  |


#### `CheckArgsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `validateAll` | `Boolean` | No |  |  |
| `skuList` | `[String]` | No |  |  |
| `minimumQuantity` | `Int` | No |  |  |


#### `CheckInFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `visitPlanCode` | `String` | No |  |  |
| `salesRepCode` | `String` | No |  |  |
| `customerCode` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CheckInInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `visitPlanCode` | `String!` | **Yes** |  |  |
| `salesRepCode` | `String!` | **Yes** |  |  |
| `customerCode` | `String!` | **Yes** |  |  |
| `customFields` | `JSON` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CheckInUpdateInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `salesRepCode` | `String` | No |  |  |
| `customerCode` | `String` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `CheckOrderInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `CheckTypes!` | **Yes** |  |  |
| `name` | `String!` | **Yes** |  |  |
| `args` | `CheckArgsInput!` | **Yes** |  |  |
| `externalFunction` | `ExternalFunctionInput` | No |  |  |
| `executeMethod` | `CheckMethod!` | **Yes** |  |  |


#### `CheckOrderUpdate`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `CheckTypes` | No |  |  |
| `name` | `String` | No |  |  |
| `args` | `CheckArgsInput` | No |  |  |
| `externalFunction` | `ExternalFunctionInput` | No |  |  |
| `executeMethod` | `CheckMethod` | No |  |  |


#### `CheckoutRuleInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `ruleType` | `String` | No |  |  |
| `mappings` | `MappingsInput` | No |  |  |
| `dateRules` | `DateRuleInput` | No |  |  |
| `paymentRules` | `PaymentRuleInput` | No |  |  |
| `customerRuleType` | `String` | No |  |  |


#### `CheckoutRulesByTypeConfigInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `String` | No |  |  |
| `checkoutRules` | `ConfigCheckoutRulesInput` | No |  |  |


#### `CleanUpPromotionsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `daysSinceEndDate` | `Int` | No | 10 |  |


#### `ComplexPromotionBuysGroupInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `items` | `[ComplexPromotionBuysProductInput]!` | **Yes** |  |  |
| `type` | `ComplexPromotionTypes!` | **Yes** |  |  |
| `identifier` | `String` | No |  |  |


#### `ComplexPromotionBuysProductInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `ComplexPromotionTypes` | No |  |  |
| `sku` | `String!` | **Yes** |  |  |
| `quantity` | `Int` | No |  |  |
| `amount` | `Float` | No |  |  |
| `productPackage` | `String` | No |  |  |


#### `ComplexPromotionGetsGroupInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `items` | `[ComplexPromotionGetsProductInput]!` | **Yes** |  |  |
| `type` | `ComplexPromotionTypes!` | **Yes** |  |  |
| `identifier` | `String` | No |  |  |
| `maxSkuSelectionQuantity` | `Int` | No |  |  |


#### `ComplexPromotionGetsProductInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `ComplexPromotionTypes` | No |  |  |
| `sku` | `String!` | **Yes** |  |  |
| `quantity` | `Int` | No |  |  |
| `amount` | `Float` | No |  |  |
| `productPackage` | `String` | No |  |  |
| `percentage` | `Float` | No |  |  |


#### `ComplexPromotionUpdateBuysGroupInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `items` | `[ComplexPromotionUpdateBuysProductInput]` | No |  |  |
| `type` | `ComplexPromotionTypes` | No |  |  |
| `identifier` | `String` | No |  |  |


#### `ComplexPromotionUpdateBuysProductInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `ComplexPromotionTypes` | No |  |  |
| `sku` | `String` | No |  |  |
| `quantity` | `Int` | No |  |  |
| `amount` | `Float` | No |  |  |
| `productPackage` | `String` | No |  |  |


#### `ComplexPromotionUpdateGetsGroupInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `items` | `[ComplexPromotionUpdateGetsProductInput]` | No |  |  |
| `type` | `ComplexPromotionTypes` | No |  |  |
| `identifier` | `String` | No |  |  |
| `maxSkuSelectionQuantity` | `Int` | No |  |  |


#### `ComplexPromotionUpdateGetsProductInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `ComplexPromotionTypes` | No |  |  |
| `sku` | `String` | No |  |  |
| `quantity` | `Int` | No |  |  |
| `amount` | `Float` | No |  |  |
| `productPackage` | `String` | No |  |  |
| `percentage` | `Float` | No |  |  |


#### `ConfigBannerInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `enabled` | `Boolean` | No |  |  |
| `maximumActive` | `Int` | No |  |  |


#### `ConfigBooleanFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `active` | `Boolean` | No |  |  |


#### `ConfigCartInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `precisionDigits` | `Int` | No |  |  |
| `quantityAdjustment` | `QuantityAdjustmentMode` | No |  | QuantityAdjustmentMode indicates how the product quantity adjustment should be performed. |


#### `ConfigCheckoutRulesInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `cartConditionPendingMinAmount` | `CartConditionPendingMinAmountInput` | No |  |  |
| `cartConditionPendingMaxAmount` | `CartConditionPendingMaxAmountInput` | No |  |  |
| `cartConditionPendingMinQty` | `CartConditionPendingMinQtyInput` | No |  |  |
| `cartConditionPendingMaxQty` | `CartConditionPendingMaxQtyInput` | No |  |  |
| `cartConditionPendingMinAdditionalMeasurement` | `CartConditionPendingAdditionalMeasurementInput` | No |  |  |
| `cartConditionPendingMaxAdditionalMeasurement` | `CartConditionPendingAdditionalMeasurementInput` | No |  |  |
| `cartConditionPendingUserValidation` | `CartConditionPendingUserValidationInput` | No |  |  |
| `cartWarningCheckReturnables` | `CartWarningCheckReturnablesInput` | No |  |  |
| `cartConditionCheckLinkedProducts` | `CartConditionCheckLinkedProductsInput` | No |  |  |
| `orderDailyLimit` | `OrderDailyLimitInput` | No |  |  |


#### `ConfigFeeFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `FeeType` | No |  |  |
| `entity` | `FeeEntities` | No |  |  |


#### `ConfigFeeInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `FeeType!` | **Yes** |  |  |
| `entity` | `FeeEntities!` | **Yes** |  |  |


#### `ConfigFiltersInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `attributes` | `[String]` | No |  |  |
| `promotions` | `ConfigBooleanFilterInput` | No |  |  |
| `categories` | `ConfigBooleanFilterInput` | No |  |  |
| `brands` | `ConfigBooleanFilterInput` | No |  |  |


#### `ConfigGrouperInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `active` | `Boolean` | No |  |  |
| `session` | `[String]` | No |  |  |
| `product` | `[String]` | No |  |  |


#### `ConfigGroupersInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `cart` | `ConfigGrouperInput` | No |  |  |
| `order` | `ConfigGrouperInput` | No |  |  |


#### `ConfigSplitterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `active` | `Boolean` | No |  |  |
| `maxProduct` | `Int` | No |  |  |


#### `ConfigSplittersInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `order` | `ConfigSplitterInput` | No |  |  |


#### `ConfigStockFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `StockType` | No |  |  |
| `threshold` | `ConfigStockThresholdInput` | No |  |  |
| `timer` | `ConfigStockTimerInput` | No |  |  |
| `key` | `String` | No |  |  |
| `hideOutOfStock` | `Boolean` | No |  |  |
| `returnStock` | `ReturnStockFilterInput` | No |  |  |
| `prioritizeProductsInStock` | `Boolean` | No |  |  |


#### `ConfigStockInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `StockType!` | **Yes** |  |  |
| `threshold` | `ConfigStockThresholdInput` | No |  |  |
| `timer` | `ConfigStockTimerInput` | No |  |  |
| `key` | `String` | No |  |  |
| `hideOutOfStock` | `Boolean` | No |  |  |
| `returnStock` | `ReturnStockInput` | No |  |  |
| `prioritizeProductsInStock` | `Boolean` | No |  |  |


#### `ConfigStockThresholdInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `lowWarning` | `ConfigStockWarningInput` | No |  |  |
| `criticalLowWarning` | `ConfigStockWarningInput` | No |  |  |


#### `ConfigStockTimerInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `expirationMinutes` | `Int` | No |  |  |


#### `ConfigStockUpdateInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `StockType` | No |  |  |
| `threshold` | `ConfigStockThresholdInput` | No |  |  |
| `timer` | `ConfigStockTimerInput` | No |  |  |
| `key` | `String` | No |  |  |
| `hideOutOfStock` | `Boolean` | No |  |  |
| `returnStock` | `ReturnStockInput` | No |  |  |
| `prioritizeProductsInStock` | `Boolean` | No |  |  |


#### `ConfigStockWarningInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `id` | `String` | No |  |  |
| `warningMessage` | `String` | No |  |  |
| `quantity` | `Int` | No |  |  |
| `enabled` | `Boolean` | No |  |  |


#### `ConfigurationFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `banner` | `ConfigBannerInput` | No |  |  |
| `budget` | `BudgetConfigFilterInput` | No |  |  |
| `cart` | `ConfigCartInput` | No |  |  |
| `checkoutRules` | `ConfigCheckoutRulesInput` | No |  |  |
| `checkoutRulesByType` | `[CheckoutRulesByTypeConfigInput]` | No |  |  |
| `emptyFees` | `Boolean` | No |  |  |
| `fees` | `[ConfigFeeFilterInput]` | No |  |  |
| `filters` | `ConfigFiltersInput` | No |  |  |
| `forceConfig` | `ForceConfigFilterInput` | No |  |  |
| `groupers` | `ConfigGroupersInput` | No |  |  |
| `i18n` | `I18nInput` | No |  |  |
| `notifications` | `[NotificationTypeFilterInput]` | No |  |  |
| `orderFinalStatuses` | `[String]` | No |  |  |
| `priceless` | `Boolean` | No |  |  |
| `promotions` | `PromotionsConfigInput` | No |  |  |
| `recommendedProducts` | `recommendedProductsInput` | No |  |  |
| `segments` | `SegmentsConfigInput` | No |  |  |
| `sessionTtl` | `Int` | No |  |  |
| `showRecommendations` | `Boolean` | No |  |  |
| `sortFields` | `SortFieldsConfigInput` | No |  |  |
| `splitters` | `ConfigSplittersInput` | No |  |  |
| `stock` | `ConfigStockFilterInput` | No |  |  |
| `useStores` | `Boolean` | No |  |  |
| `workflow` | `JSON` | No |  |  |


#### `ConfigurationInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `banner` | `ConfigBannerInput` | No | {enabled: true, maximumActive: 6} |  |
| `budget` | `BudgetConfigInput` | No |  |  |
| `cart` | `ConfigCartInput` | No | {precisionDigits: 2, quantityAdjustment: VALIDATE} |  |
| `checkoutRules` | `ConfigCheckoutRulesInput` | No |  |  |
| `checkoutRulesByType` | `[CheckoutRulesByTypeConfigInput]` | No |  |  |
| `emptyFees` | `Boolean` | No |  |  |
| `fees` | `[ConfigFeeInput]` | No |  |  |
| `filters` | `ConfigFiltersInput` | No |  |  |
| `forceConfig` | `ForceConfigInput` | No |  |  |
| `groupers` | `ConfigGroupersInput` | No |  |  |
| `i18n` | `I18nInput` | No |  |  |
| `notifications` | `[NotificationTypeInput]` | No |  |  |
| `orderFinalStatuses` | `[String]` | No | ["CONFIRMED"] |  |
| `priceless` | `Boolean` | No | false |  |
| `promotions` | `PromotionsConfigInput` | No |  |  |
| `recommendedProducts` | `recommendedProductsInput` | No |  |  |
| `segments` | `SegmentsConfigInput` | No |  |  |
| `sessionTtl` | `Int` | No | 1440 |  |
| `showRecommendations` | `Boolean` | No |  |  |
| `sortFields` | `SortFieldsConfigInput` | No |  |  |
| `splitters` | `ConfigSplittersInput` | No |  |  |
| `stock` | `ConfigStockInput` | No | {type: INFINITE} |  |
| `useStores` | `Boolean` | No |  |  |
| `workflow` | `JSON` | No |  |  |


#### `ConfigurationUpdateInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `banner` | `ConfigBannerInput` | No |  |  |
| `budget` | `BudgetConfigInput` | No |  |  |
| `cart` | `ConfigCartInput` | No |  |  |
| `checkoutRules` | `ConfigCheckoutRulesInput` | No |  |  |
| `checkoutRulesByType` | `[CheckoutRulesByTypeConfigInput]` | No |  |  |
| `emptyFees` | `Boolean` | No |  |  |
| `fees` | `[ConfigFeeInput]` | No |  |  |
| `filters` | `ConfigFiltersInput` | No |  |  |
| `forceConfig` | `ForceConfigInput` | No |  |  |
| `groupers` | `ConfigGroupersInput` | No |  |  |
| `i18n` | `I18nInput` | No |  |  |
| `notifications` | `[NotificationUpdateInput]` | No |  |  |
| `orderFinalStatuses` | `[OrderStatus]` | No |  |  |
| `priceless` | `Boolean` | No |  |  |
| `promotions` | `PromotionsConfigInput` | No |  |  |
| `recommendedProducts` | `recommendedProductsInput` | No |  |  |
| `segments` | `SegmentsConfigInput` | No |  |  |
| `sessionTtl` | `Int` | No |  |  |
| `showRecommendations` | `Boolean` | No |  |  |
| `sortFields` | `SortFieldsConfigInput` | No |  |  |
| `splitters` | `ConfigSplittersInput` | No |  |  |
| `stock` | `ConfigStockUpdateInput` | No |  |  |
| `useStores` | `Boolean` | No |  |  |
| `workflow` | `JSON` | No |  |  |


#### `CustomerBuysInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `value` | `CustomerBuysValueInput` | No |  |  |
| `items` | `[String]` | No |  |  |
| `groups` | `[ComplexPromotionBuysGroupInput]` | No |  |  |


#### `CustomerBuysValueInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `amount` | `Float` | No |  |  |
| `minimum` | `Int` | No |  |  |
| `minimumAmount` | `Float` | No |  |  |
| `productPackage` | `String` | No |  |  |
| `quantity` | `Int` | No |  |  |
| `type` | `String` | No |  |  |
| `unit` | `String` | No |  |  |


#### `CustomerCreateInputType`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `acceptance` | `Boolean` | No |  |  |
| `address` | `String` | No |  |  |
| `categories` | `[String]` | No |  |  |
| `city` | `String` | No |  |  |
| `code` | `String` | No |  |  |
| `country` | `String` | No |  |  |
| `creditAmount` | `Float` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `deactivationDate` | `Date` | No |  |  |
| `email` | `String` | No |  |  |
| `extraCode` | `[String]` | No |  |  |
| `hasCredit` | `Boolean` | No |  |  |
| `isActive` | `Boolean` | No | true |  |
| `location` | `CustomerLocationDataInput` | No |  |  |
| `lockedStoreCode` | `String` | No |  |  |
| `minimumOrderAmount` | `Float` | No |  |  |
| `name` | `String` | No |  |  |
| `periodicity` | `Float` | No |  |  |
| `phoneNumber` | `[String]` | No |  |  |
| `region` | `String` | No |  |  |
| `routes` | `[String]` | No |  |  |
| `ruleType` | `String` | No |  |  |
| `state` | `String` | No |  |  |
| `taxId` | `String` | No |  |  |
| `type` | `String!` | **Yes** |  |  |
| `visitDate` | `Date` | No |  |  |
| `visitDays` | `[VisitDay]` | No |  |  |
| `zipCode` | `String` | No |  |  |


#### `CustomerGetsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `value` | `CustomerGetsValueInput` | No |  |  |
| `items` | `[String]` | No |  |  |
| `groups` | `[ComplexPromotionGetsGroupInput]` | No |  |  |


#### `CustomerGetsValueInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `amount` | `Float` | No |  |  |
| `cash` | `Float` | No |  |  |
| `percentage` | `Float` | No |  |  |
| `productPackage` | `String` | No |  |  |
| `quantity` | `Int` | No |  |  |


#### `CustomerInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `customerUid` | `[ID]` | No |  |  |
| `type` | `[String]` | No |  |  |
| `customerCode` | `[String]` | No |  |  |
| `storeCode` | `[String]` | No |  |  |
| `segments` | `[String]` | No |  |  |


#### `CustomerLocationDataInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `coordinates` | `[Float!]` | No |  |  |


#### `CustomerUpdateInputType`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `acceptance` | `Boolean` | No |  |  |
| `address` | `String` | No |  |  |
| `categories` | `[String]` | No |  |  |
| `city` | `String` | No |  |  |
| `code` | `String` | No |  |  |
| `country` | `String` | No |  |  |
| `creditAmount` | `Float` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `deactivationDate` | `Date` | No |  |  |
| `email` | `String` | No |  |  |
| `extraCode` | `[String]` | No |  |  |
| `hasCredit` | `Boolean` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `location` | `CustomerLocationDataInput` | No |  |  |
| `lockedStoreCode` | `String` | No |  |  |
| `minimumOrderAmount` | `Float` | No |  |  |
| `name` | `String` | No |  |  |
| `periodicity` | `Float` | No |  |  |
| `phoneNumber` | `[String]` | No |  |  |
| `region` | `String` | No |  |  |
| `routes` | `[String]` | No |  |  |
| `ruleType` | `String` | No |  |  |
| `sessionLog` | `JSON` | No |  |  |
| `state` | `String` | No |  |  |
| `taxId` | `String` | No |  |  |
| `type` | `String` | No |  |  |
| `visitDate` | `Date` | No |  |  |
| `visitDays` | `[VisitDay]` | No |  |  |
| `zipCode` | `String` | No |  |  |


#### `DateRuleInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `timezone` | `String` | No |  |  |
| `offsets` | `[Int]` | No |  |  |
| `businessStartTime` | `String` | No |  |  |
| `businessEndTime` | `String` | No |  |  |
| `default` | `[Int]` | No |  |  |
| `custom` | `[BusinessHoursInput]` | No |  |  |


#### `EndpointInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `url` | `String` | No |  |  |
| `status` | `StorefrontStatus` | No |  |  |


#### `ExternalFunctionInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `url` | `String` | No |  |  |
| `token` | `String` | No |  |  |


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


#### `FilterCategoryInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `imageURL` | `[String]` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `name` | `String` | No |  |  |
| `parentId` | `ID` | No |  |  |
| `autoPopulate` | `AutoPopulateCategoryInput` | No |  |  |


#### `FilterCustomerInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `email` | `String` | No |  |  |
| `extraCodes` | `[String]` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `lockedStoreCode` | `String` | No |  |  |
| `name` | `String` | No |  |  |
| `phoneNumber` | `String` | No |  |  |
| `type` | `String` | No |  |  |


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


#### `FilterPriceInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `sku` | `String` | No |  |  |
| `key` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `customFields` | `JSON` | No |  |  |


#### `FilterProcessInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `status` | `[ProcessStatus]` | No |  |  |
| `startDate` | `Date` | No |  |  |
| `endDate` | `Date` | No |  |  |


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


#### `FilterSessionInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `customerUid` | `String` | No |  |  |
| `cartUid` | `String` | No |  |  |
| `status` | `SessionStatus` | No |  |  |
| `workflow` | `SessionWorkflowFilterInput` | No |  |  |


#### `FilterStocksInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `sku` | `String` | No |  |  |
| `key` | `String` | No |  |  |
| `stock` | `Int` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `FilterStoreInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `name` | `String` | No |  |  |
| `type` | `String` | No |  |  |
| `owner` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `FilterStorefrontInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `addons` | `StorefrontAddOnsInput` | No |  |  |
| `authorizedEmails` | `String` | No |  |  |
| `configuration` | `ConfigurationFilterInput` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `name` | `String` | No |  |  |
| `owner` | `String` | No |  |  |
| `ownerSlug` | `String` | No |  |  |
| `status` | `StorefrontStatus` | No |  |  |


#### `ForceColumnConfigFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `field` | `String` | No |  |  |
| `label` | `String` | No |  |  |
| `type` | `ForceTypes` | No |  |  |
| `format` | `String` | No |  |  |
| `mobilePosition` | `Int` | No |  |  |


#### `ForceColumnConfigInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `field` | `String!` | **Yes** |  |  |
| `label` | `String!` | **Yes** |  |  |
| `type` | `ForceTypes!` | **Yes** |  |  |
| `format` | `String` | No |  |  |
| `mobilePosition` | `Int` | No |  |  |


#### `ForceConfigFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `main` | `[ForceColumnConfigFilterInput]` | No |  |  |
| `details` | `[ForceColumnConfigFilterInput]` | No |  |  |


#### `ForceConfigInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `main` | `[ForceColumnConfigInput!]!` | **Yes** |  |  |
| `details` | `[ForceColumnConfigInput!]!` | **Yes** |  |  |


#### `I18nInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `language` | `String` | No |  |  |
| `currencyFormat` | `String` | No |  |  |
| `currencySymbol` | `String` | No |  |  |
| `currencyCode` | `String` | No |  |  |
| `currencyDisplay` | `String` | No |  |  |
| `country` | `String` | No |  |  |
| `timezone` | `String` | No |  |  |


#### `LinkedConditionalStockInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `requiredQuantity` | `Float` | No |  |  |
| `stockPerRequiredQuantity` | `Float` | No |  |  |


#### `MappingsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `dates` | `JSON` | No |  |  |
| `paymentMethods` | `JSON` | No |  |  |


#### `NearbyCustomersFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `isActive` | `Boolean` | No |  |  |


#### `NearbyCustomersLocationInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `distanceInMeters` | `Int!` | **Yes** |  |  |
| `latitude` | `Float!` | **Yes** |  |  |
| `longitude` | `Float!` | **Yes** |  |  |


#### `NotificationTypeFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `abTestingSlug` | `String` | No |  |  |
| `botSlug` | `String` | No |  |  |
| `customerType` | `String` | No |  |  |
| `enabled` | `Boolean` | No |  |  |
| `notificationAtHours` | `[Int]` | No |  |  |
| `notificationOnDays` | `[NotificationDaysEnum]` | No |  |  |
| `priority` | `Int` | No |  |  |
| `studioAccountId` | `String` | No |  |  |
| `templateId` | `String` | No |  |  |
| `thresholdInMinutes` | `Int` | No |  |  |
| `type` | `NotificationTypeEnum` | No |  |  |
| `workflow` | `NotificationWorkflowInput` | No |  |  |


#### `NotificationTypeInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `abTestingSlug` | `String` | No |  |  |
| `botSlug` | `String!` | **Yes** |  |  |
| `customerType` | `String` | No |  |  |
| `enabled` | `Boolean!` | **Yes** |  |  |
| `notificationAtHours` | `[Int]!` | **Yes** |  |  |
| `notificationOnDays` | `[NotificationDaysEnum]!` | **Yes** |  |  |
| `priority` | `Int` | No |  |  |
| `studioAccountId` | `String!` | **Yes** |  |  |
| `templateId` | `String!` | **Yes** |  |  |
| `thresholdInMinutes` | `Int` | No | 0 |  |
| `type` | `NotificationTypeEnum!` | **Yes** |  |  |
| `workflow` | `NotificationWorkflowInput` | No |  |  |


#### `NotificationUpdateInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `abTestingSlug` | `String` | No |  |  |
| `botSlug` | `String` | No |  |  |
| `customerType` | `String` | No |  |  |
| `enabled` | `Boolean` | No |  |  |
| `notificationAtHours` | `[Int]` | No |  |  |
| `notificationOnDays` | `[NotificationDaysEnum]` | No |  |  |
| `priority` | `Int` | No |  |  |
| `studioAccountId` | `String` | No |  |  |
| `templateId` | `String` | No |  |  |
| `thresholdInMinutes` | `Int` | No |  |  |
| `type` | `NotificationTypeEnum` | No |  |  |
| `workflow` | `NotificationWorkflowInput` | No |  |  |


#### `NotificationWorkflowInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `channel` | `String` | No |  |  |
| `ng` | `Boolean` | No |  |  |
| `token` | `String` | No |  |  |
| `triggerId` | `String` | No |  |  |
| `workflowId` | `String` | No |  |  |
| `workflowName` | `String` | No |  |  |


#### `OrderCustomerInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `acceptance` | `Boolean` | No |  |  |
| `acceptanceDate` | `Date` | No |  |  |
| `address` | `String` | No |  |  |
| `categories` | `[String]` | No |  |  |
| `city` | `String` | No |  |  |
| `code` | `String` | No |  |  |
| `country` | `String` | No |  |  |
| `creditAmount` | `Float` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `deactivationDate` | `Date` | No |  |  |
| `email` | `String` | No |  |  |
| `extraCode` | `[String]` | No |  |  |
| `hasCredit` | `Boolean` | No |  |  |
| `lockedStoreCode` | `String` | No |  |  |
| `minimumOrderAmount` | `Float` | No |  |  |
| `name` | `String` | No |  |  |
| `periodicity` | `Float` | No |  |  |
| `phoneNumber` | `[String]` | No |  |  |
| `region` | `String` | No |  |  |
| `routes` | `[String]` | No |  |  |
| `ruleType` | `String` | No |  |  |
| `state` | `String` | No |  |  |
| `taxId` | `String` | No |  |  |
| `visitDate` | `Date` | No |  |  |
| `visitDays` | `[VisitDay]` | No |  |  |
| `zipCode` | `String` | No |  |  |
| `type` | `String` | No |  |  |


#### `OrderDailyLimitInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `quantity` | `Int` | No |  |  |
| `message` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `OrderGroupInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `groupBy` | `[String]` | No |  |  |
| `items` | `[CartProductInput]` | No |  |  |
| `total` | `Float` | No |  |  |


#### `OrderInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `activeFees` | `[ActiveFeeInput]` | No |  |  |
| `cartUid` | `ID` | No |  |  |
| `compensations` | `Float` | No |  |  |
| `customerCode` | `String!` | **Yes** |  |  |
| `customerUid` | `ID!` | **Yes** |  |  |
| `customFields` | `JSON` | No |  |  |
| `expectedDeliveryDate` | `Date` | No |  |  |
| `externalErrorMessage` | `String` | No |  |  |
| `externalMessage` | `String` | No |  |  |
| `externalRef` | `String` | No |  |  |
| `externalRefNumber` | `String` | No |  |  |
| `externalRefStatus` | `ExternalRefStatus` | No |  |  |
| `groups` | `[OrderGroupInput]` | No |  |  |
| `items` | `[CartProductInput]!` | **Yes** |  |  |
| `notes` | `String` | No |  |  |
| `parentOrderUid` | `ID` | No |  |  |
| `paymentInfo` | `JSON` | No |  |  |
| `paymentMethod` | `OrderPaymentMethod` | No |  |  |
| `processedAt` | `Date` | No |  |  |
| `sequence` | `Float` | No |  |  |
| `sessionUid` | `ID!` | **Yes** |  |  |
| `source` | `String` | No |  |  |
| `status` | `String` | No |  |  |
| `storeCode` | `String` | No |  |  |
| `total` | `Float` | No |  |  |


#### `OrderUpdate`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `activeFees` | `[ActiveFeeInput]` | No |  |  |
| `compensations` | `Float` | No |  |  |
| `customer` | `OrderCustomerInput` | No |  |  |
| `customerCode` | `String` | No |  |  |
| `customerUid` | `ID` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `expectedDeliveryDate` | `Date` | No |  |  |
| `externalErrorMessage` | `String` | No |  |  |
| `externalMessage` | `String` | No |  |  |
| `externalRef` | `String` | No |  |  |
| `externalRefNumber` | `String` | No |  |  |
| `externalRefStatus` | `ExternalRefStatus` | No |  |  |
| `groups` | `[OrderGroupInput]` | No |  |  |
| `items` | `[CartProductInput]` | No |  |  |
| `notes` | `String` | No |  |  |
| `parentOrderUid` | `ID` | No |  |  |
| `paymentInfo` | `JSON` | No |  |  |
| `paymentMethod` | `OrderPaymentMethod` | No |  |  |
| `processedAt` | `Date` | No |  |  |
| `sequence` | `Float` | No |  |  |
| `sessionUid` | `ID` | No |  |  |
| `source` | `String` | No |  |  |
| `status` | `String` | No |  |  |
| `storeCode` | `String` | No |  |  |
| `total` | `Float` | No |  |  |


#### `PackagePriceInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String!` | **Yes** |  |  |
| `price` | `Float!` | **Yes** |  |  |
| `basePrice` | `Float` | No |  |  |
| `fees` | `[FeeThresholdInput]` | No |  |  |


#### `PackageStockInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String` | No |  |  |
| `stock` | `Int` | No |  |  |


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


#### `PaymentRuleInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `default` | `[String]` | No |  |  |


#### `PriceInputType`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `basePrice` | `Float` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `fees` | `[FeeThresholdInput]` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `isDynamic` | `Boolean` | No |  |  |
| `key` | `String!` | **Yes** |  |  |
| `packagePrice` | `Float` | No |  |  |
| `price` | `Float!` | **Yes** |  |  |
| `sku` | `String!` | **Yes** |  |  |
| `unitPrice` | `Float` | No |  |  |
| `packagesPrices` | `[PackagePriceInput]` | No |  |  |
| `isPackageRequired` | `Boolean` | No |  |  |


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


#### `ProcessInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `callBackUrl` | `String` | No |  |  |
| `emailToNotify` | `String` | No |  |  |
| `executionMode` | `ExecutionMode` | No | AUTOMATED |  |
| `inputType` | `InputStatus!` | **Yes** |  |  |
| `originatingEntity` | `OriginatingEntityStatus!` | **Yes** |  |  |
| `processId` | `String!` | **Yes** |  |  |


#### `ProcessResultInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `status` | `ProcessResultStatus!` | **Yes** |  |  |
| `errorId` | `Int` | No |  |  |
| `parsed` | `Int` | No |  |  |
| `total` | `Int` | No |  |  |
| `inserted` | `Int` | No |  |  |
| `description` | `String` | No |  |  |


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


#### `PromotionFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `exactCodes` | `[String]` | No |  |  |
| `type` | `PromotionTypes` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `segments` | `[String]` | No |  |  |


#### `PromotionInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `customer` | `CustomerInput!` | **Yes** |  |  |
| `customerBuys` | `CustomerBuysInput!` | **Yes** |  |  |
| `customerGets` | `CustomerGetsInput!` | **Yes** |  |  |
| `description` | `String` | No |  |  |
| `endDate` | `Date!` | **Yes** |  |  |
| `isActive` | `Boolean` | No |  |  |
| `name` | `String` | No |  |  |
| `priority` | `Int!` | **Yes** |  |  |
| `startDate` | `Date!` | **Yes** |  |  |
| `type` | `PromotionTypes!` | **Yes** |  |  |
| `usageLimit` | `UsageLimitInput` | No |  |  |
| `version` | `String` | No |  |  |


#### `PromotionUpdate`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `customer` | `CustomerInput` | No |  |  |
| `customerBuys` | `UpdateCustomerBuysInput` | No |  |  |
| `customerGets` | `UpdateCustomerGetsInput` | No |  |  |
| `endDate` | `Date` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `priority` | `Int` | No |  |  |
| `startDate` | `Date` | No |  |  |
| `type` | `PromotionTypes` | No |  |  |
| `usageLimit` | `UsageLimitInput` | No |  |  |
| `name` | `String` | No |  |  |
| `description` | `String` | No |  |  |
| `code` | `String` | No |  |  |


#### `PromotionsConfigInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `autoAdd` | `Boolean` | No |  |  |
| `disableFreeGoodsAsDiscount` | `Boolean` | No |  |  |
| `disableVolumeStacking` | `Boolean` | No |  |  |
| `discountFromStock` | `Boolean` | No |  |  |
| `enabled` | `Boolean` | No |  |  |
| `limitTotalPromotions` | `Boolean` | No |  |  |
| `maximumActive` | `Int` | No |  |  |


#### `ReturnStockFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `enabled` | `Boolean` | No |  |  |
| `statuses` | `[OrderStatus]` | No |  |  |


#### `ReturnStockInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `enabled` | `Boolean!` | **Yes** |  |  |
| `statuses` | `[OrderStatus]!` | **Yes** |  |  |


#### `SalesRepFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `name` | `String` | No |  |  |
| `routes` | `[String]` | No |  |  |
| `reps` | `[ID]` | No |  |  |
| `phoneNumbers` | `[String]` | No |  |  |


#### `SalesRepInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String!` | **Yes** |  |  |
| `routes` | `[String]` | No |  |  |
| `reps` | `[String]` | No |  |  |
| `code` | `String!` | **Yes** |  |  |
| `phoneNumbers` | `[String]` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `SalesRepresentativeBulkInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String!` | **Yes** |  |  |
| `name` | `String!` | **Yes** |  |  |
| `phoneNumbers` | `[String]` | No |  |  |
| `reps` | `[String]` | No |  |  |
| `routes` | `[String]` | No |  |  |


#### `SalesRepresentativeUpdateInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String` | No |  |  |
| `routes` | `[String]` | No |  |  |
| `reps` | `[String]` | No |  |  |
| `phoneNumbers` | `[String]` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `customFields` | `JSON` | No |  |  |


#### `SegmentsConfigInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `type` | `SegmentsTypes` | No |  |  |


#### `SessionCustomerInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `phoneNumber` | `[String]` | No |  |  |
| `email` | `String` | No |  |  |
| `name` | `String` | No |  |  |
| `address` | `String` | No |  |  |
| `type` | `String!` | **Yes** |  |  |
| `minimumOrderAmount` | `Float` | No |  |  |
| `hasCredit` | `Boolean` | No |  |  |
| `creditAmount` | `Float` | No |  |  |
| `acceptance` | `Boolean` | No |  |  |
| `acceptanceDate` | `Date` | No |  |  |
| `periodicity` | `Float` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `lockedStoreCode` | `String` | No |  |  |


#### `SessionInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `customerUid` | `String!` | **Yes** |  |  |
| `customerAlias` | `String!` | **Yes** |  |  |
| `customer` | `SessionCustomerInput` | No |  |  |
| `cartUid` | `ID!` | **Yes** |  |  |
| `configuration` | `ConfigurationInput` | No |  |  |
| `workflow` | `SessionWorkflowInput` | No |  |  |
| `extraIds` | `[ExtraIdInput]` | No |  |  |
| `startedAt` | `Date` | No |  |  |
| `finishedAt` | `Date` | No |  |  |
| `status` | `SessionStatus!` | **Yes** |  |  |
| `customFields` | `JSON` | No |  |  |


#### `SessionUpdate`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `cartUid` | `ID` | No |  |  |
| `customer` | `SessionUpdateCustomerInput` | No |  |  |
| `customerAlias` | `String` | No |  |  |
| `customerUid` | `String` | No |  |  |
| `configuration` | `ConfigurationUpdateInput` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `extraIds` | `[ExtraIdInput]` | No |  |  |
| `finishedAt` | `Date` | No |  |  |
| `segments` | `[String]` | No |  |  |
| `startedAt` | `Date` | No |  |  |
| `status` | `SessionStatus` | No |  |  |


#### `SessionUpdateCustomerInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `phoneNumber` | `[String]` | No |  |  |
| `email` | `String` | No |  |  |
| `name` | `String` | No |  |  |
| `address` | `String` | No |  |  |
| `type` | `String` | No |  |  |
| `minimumOrderAmount` | `Float` | No |  |  |
| `hasCredit` | `Boolean` | No |  |  |
| `creditAmount` | `Float` | No |  |  |
| `acceptance` | `Boolean` | No |  |  |
| `acceptanceDate` | `Date` | No |  |  |
| `periodicity` | `Float` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `lockedStoreCode` | `String` | No |  |  |


#### `SessionWorkflowFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `channelUid` | `String` | No |  |  |
| `userUid` | `String` | No |  |  |


#### `SessionWorkflowInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String` | No |  |  |
| `channel` | `String` | No |  |  |
| `channelUid` | `String` | No |  |  |
| `userUid` | `String` | No |  |  |


#### `SkuQuantitySelectionInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `sku` | `String!` | **Yes** |  |  |
| `quantity` | `Int!` | **Yes** |  |  |


#### `SortFieldsConfigInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `order` | `[SortOrderProperty]` | No |  |  |


#### `SortOptionsExtraInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `properties` | `[SortPropertyExtraInput]` | No |  |  |


#### `SortOptionsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `properties` | `[SortPropertyInput]` | No |  |  |


#### `SortProcessOptionsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `properties` | `[SortPropertyProcessInput]` | No |  |  |


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


#### `SortPropertyProcessInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `property` | `SortByProcess!` | **Yes** |  |  |
| `direction` | `SortDirection` | No |  |  |


#### `StockInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `sku` | `String!` | **Yes** |  |  |
| `key` | `String` | No |  |  |
| `stock` | `Int!` | **Yes** |  |  |
| `isActive` | `Boolean` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `stockByPackage` | `[PackageStockInput]` | No |  |  |


#### `StoreInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String!` | **Yes** |  |  |
| `name` | `String!` | **Yes** |  |  |
| `phoneNumbers` | `[String]` | No |  |  |
| `email` | `String` | No |  |  |
| `region` | `String` | No |  |  |
| `type` | `String` | No |  |  |
| `address` | `String` | No |  |  |
| `stockHandling` | `Boolean` | No |  |  |
| `extensions` | `JSON` | No |  |  |
| `owner` | `String` | No |  |  |
| `storePrice` | `Boolean` | No |  |  |
| `minimumOrderAmount` | `Float` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `location` | `StoreLocationInput` | No |  |  |
| `customFields` | `JSON` | No |  |  |


#### `StoreLocationInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `coordinates` | `[Float]` | No |  |  |


#### `StorefrontAddOnsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `after` | `[String]` | No |  |  |
| `instead` | `[String]` | No |  |  |
| `validation` | `[String]` | No |  |  |


#### `StorefrontInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `authorizedEmails` | `[String]` | No |  |  |
| `configuration` | `ConfigurationInput!` | **Yes** |  |  |
| `customFields` | `JSON` | No |  |  |
| `favoriteStatus` | `FavoriteStatus` | No |  |  |
| `name` | `String!` | **Yes** |  |  |
| `owner` | `String!` | **Yes** |  |  |
| `productive` | `Boolean` | No |  |  |
| `status` | `StorefrontStatus` | No |  |  |


#### `UpdateBannersPriorityInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `id` | `ID!` | **Yes** |  |  |
| `newPosition` | `Int!` | **Yes** |  |  |


#### `UpdateCustomerBuysInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `value` | `CustomerBuysValueInput` | No |  |  |
| `items` | `[String]` | No |  |  |
| `groups` | `[ComplexPromotionUpdateBuysGroupInput]` | No |  |  |


#### `UpdateCustomerGetsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `value` | `CustomerGetsValueInput` | No |  |  |
| `items` | `[String]` | No |  |  |
| `groups` | `[ComplexPromotionUpdateGetsGroupInput]` | No |  |  |


#### `UpdatePriceInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `basePrice` | `Float` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `fees` | `[FeeThresholdInput]` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `isDynamic` | `Boolean` | No |  |  |
| `key` | `String` | No |  |  |
| `packagePrice` | `Float` | No |  |  |
| `price` | `Float` | No |  |  |
| `sku` | `String` | No |  |  |
| `unitPrice` | `Float` | No |  |  |
| `packagesPrices` | `[PackagePriceInput]` | No |  |  |
| `isPackageRequired` | `Boolean` | No |  |  |


#### `UpdateProcessInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `status` | `ProcessStatus` | No |  |  |
| `startDate` | `Date` | No |  |  |
| `result` | `ProcessResultInput` | No |  |  |


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


#### `UpdateStockInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `sku` | `String` | No |  |  |
| `key` | `String` | No |  |  |
| `stock` | `Int` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `stockByPackage` | `[PackageStockInput]` | No |  |  |


#### `UpdateStoreInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `name` | `String` | No |  |  |
| `phoneNumbers` | `[String]` | No |  |  |
| `email` | `String` | No |  |  |
| `region` | `String` | No |  |  |
| `type` | `String` | No |  |  |
| `address` | `String` | No |  |  |
| `stockHandling` | `Boolean` | No |  |  |
| `extensions` | `JSON` | No |  |  |
| `owner` | `String` | No |  |  |
| `storePrice` | `Boolean` | No |  |  |
| `minimumOrderAmount` | `Float` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `location` | `StoreLocationInput` | No |  |  |
| `customFields` | `JSON` | No |  |  |


#### `UpdateStorefrontInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `additionalEmailsToNotify` | `[String]` | No |  |  |
| `authorizedEmails` | `[String]` | No |  |  |
| `configuration` | `ConfigurationUpdateInput` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `favoriteStatus` | `FavoriteStatus` | No |  |  |
| `owner` | `String` | No |  |  |
| `productive` | `Boolean` | No |  |  |
| `status` | `StorefrontStatus` | No |  |  |


#### `UsageLimitInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `budgetId` | `ID` | No |  |  |
| `perCustomer` | `Int` | No |  |  |
| `perOrder` | `Int` | No |  |  |


#### `VisitPlanBulkInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String!` | **Yes** |  |  |
| `salesRepCode` | `String!` | **Yes** |  |  |
| `customersCode` | `[String]` | No |  |  |
| `dateStart` | `String` | No |  |  |
| `dateEnd` | `String` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `VisitPlanFilterInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `code` | `String` | No |  |  |
| `isActive` | `Boolean` | No |  |  |
| `salesRepCode` | `String` | No |  |  |


#### `VisitPlanInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `salesRepCode` | `String!` | **Yes** |  |  |
| `customersCode` | `[String]` | No |  |  |
| `dateStart` | `String` | No |  |  |
| `dateEnd` | `String` | No |  |  |
| `code` | `String!` | **Yes** |  |  |
| `customFields` | `JSON` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `VisitPlanUpdateInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `customersCode` | `[String]` | No |  |  |
| `dateStart` | `String` | No |  |  |
| `dateEnd` | `String` | No |  |  |
| `customFields` | `JSON` | No |  |  |
| `isActive` | `Boolean` | No |  |  |


#### `WebviewInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `logo` | `String` | No |  |  |


#### `WorkflowInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `name` | `String` | No |  |  |
| `channel` | `String` | No |  |  |
| `channelUid` | `String` | No |  |  |
| `region` | `String` | No |  |  |
| `orderStepHook` | `String` | No |  |  |
| `jwtToken` | `String` | No |  |  |
| `body` | `JSON` | No |  |  |


#### `recommendedProductsInput`
| Field | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `suggestedItems` | `SuggestedItemsTypeEnum` | No |  |  |
| `frequentlyBoughtTogether` | `FrequentlyBoughtTogetherTypeEnum` | No |  |  |
| `prefillCart` | `PrefillCartTypeEnum` | No |  |  |


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


#### `AddOn`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID!` |  |  |
| `type` | `AddOnTypes` |  |  |
| `flavor` | `String` |  |  |
| `config` | `AddOnConfig` |  |  |
| `status` | `AddOnStatus` |  |  |
| `callback` | `JSON` |  |  |
| `executionTime` | `AddOnExecutionTime` |  |  |


#### `AddOnConfig`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `url` | `String!` |  |  |
| `method` | `AddOnMethod` |  |  |
| `authMethod` | `AddOnAuthMethod` |  |  |
| `token` | `String` |  |  |
| `headers` | `JSON` |  |  |
| `body` | `JSON` |  |  |
| `tokenParamName` | `String` |  |  |
| `customFields` | `JSON` |  |  |


#### `AddOnTypesInfo`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `AddOnTypes` |  |  |
| `description` | `String` |  |  |


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


#### `BudgetConfig`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `skipBudgetPreAllocation` | `Boolean` |  |  |


#### `BulkImportResponse`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `additionalEmailsToNotify` | `[String]` |  |  |
| `callbackUrl` | `String` |  |  |
| `createdAt` | `Date` |  |  |
| `customFields` | `JSON` |  |  |
| `dataLength` | `Int!` |  |  |
| `deactivate` | `Boolean` |  |  |
| `emailToNotify` | `String` |  |  |
| `executionId` | `String` |  |  |
| `executionMode` | `ExecutionMode` |  |  |
| `fileURL` | `String` |  |  |
| `flowId` | `String` |  |  |
| `inputType` | `String!` |  |  |
| `operationId` | `ID!` |  |  |
| `storefrontName` | `String!` |  |  |


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


#### `BusinessHours`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `businessStartTime` | `BusinessTime` |  |  |
| `businessEndTime` | `BusinessTime` |  |  |


#### `BusinessTime`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `hours` | `Int` |  |  |
| `minutes` | `Int` |  |  |


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
| `customFields` | `JSON` |  |  |
| `groups` | `[CartGroup]` |  |  |
| `activeFees` | `[ActiveFee]` |  |  |
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
| `priority` | `Int` |  | category priority |
| `productsPrices` | `[Product]` |  | Product list with prices |


#### `CategoriesReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `categories` | `[Category]` |  |  |
| `pagination` | `Pagination` |  |  |


#### `Category`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `createdAt` | `Date` |  |  |
| `id` | `ID!` |  |  |
| `imageURL` | `[String]` |  |  |
| `isActive` | `Boolean!` |  |  |
| `isHidden` | `Boolean` |  |  |
| `name` | `String` |  |  |
| `parentId` | `ID` |  |  |
| `priority` | `Int` |  |  |
| `products` | `[CategoryProduct]` |  |  |
| `updatedAt` | `Date` |  |  |
| `autoPopulate` | `AutoPopulateCategory` |  |  |


#### `CategoryProduct`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `sku` | `String` |  |  |
| `priority` | `Int` |  |  |


#### `CheckArgs`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `validateAll` | `Boolean` |  |  |
| `skuList` | `[String]` |  |  |
| `minimumQuantity` | `Int` |  |  |


#### `CheckIn`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID!` |  |  |
| `visitPlanCode` | `String!` |  |  |
| `salesRepCode` | `String!` |  |  |
| `customerCode` | `String!` |  |  |
| `customFields` | `JSON` |  |  |
| `isActive` | `Boolean` |  |  |


#### `CheckInsReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `checkIns` | `[CheckIn]` |  |  |
| `pagination` | `Pagination` |  |  |


#### `CheckOrder`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID` |  |  |
| `type` | `CheckTypes` |  |  |
| `name` | `String` |  |  |
| `args` | `CheckArgs` |  |  |
| `externalFunction` | `ExternalFunction` |  |  |
| `executeMethod` | `CheckMethod` |  |  |
| `createdAt` | `Date` |  |  |
| `updatedAt` | `Date` |  |  |


#### `CheckoutRule`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID` |  |  |
| `ruleType` | `String` |  |  |
| `mappings` | `Mappings` |  |  |
| `dateRules` | `DateRule` |  |  |
| `paymentRules` | `PaymentRule` |  |  |
| `customerRuleType` | `String` |  |  |


#### `CheckoutRulesByTypeConfig`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `type` | `String` |  |  |
| `checkoutRules` | `ConfigCheckoutRules` |  |  |


#### `CleanUpProcess`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `entity` | `String!` |  |  |
| `finishedAt` | `Date` |  |  |
| `id` | `ID!` |  |  |
| `startedAt` | `Date!` |  |  |
| `status` | `String!` |  |  |
| `storefrontName` | `String!` |  |  |


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
| `orders` | `[CustomerOrder]` |  |  |


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


#### `CustomerOrder`
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


#### `CustomerType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `customerUid` | `[ID]` |  |  |
| `type` | `[String]` |  |  |
| `customerCode` | `[String]` |  |  |
| `storeCode` | `[String]` |  |  |
| `segments` | `[String]` |  |  |


#### `CustomersReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `customers` | `[Customer]` |  |  |
| `pagination` | `Pagination` |  |  |


#### `DateRule`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `timezone` | `String` |  |  |
| `offsets` | `[Int]` |  |  |
| `businessStartTime` | `String` |  |  |
| `businessEndTime` | `String` |  |  |
| `default` | `[Int]` |  |  |
| `custom` | `[BusinessHours]` |  |  |


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


#### `EventsTriggererResponse`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `message` | `String` |  |  |


#### `ExpireSessions`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `storefrontName` | `String` |  |  |
| `sessions` | `[String]` |  |  |


#### `ExternalFunction`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `url` | `String` |  |  |
| `token` | `String` |  |  |


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


#### `LinkedConditionalStockType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `requiredQuantity` | `Float` |  |  |
| `stockPerRequiredQuantity` | `Float` |  |  |


#### `Mappings`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `dates` | `JSON` |  |  |
| `paymentMethods` | `JSON` |  |  |


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


#### `OrdersReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `orders` | `[Order]` |  |  |
| `pagination` | `Pagination` |  |  |


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


#### `PackageStock`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `name` | `String` |  |  |
| `stock` | `Int` |  |  |


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


#### `PaymentRule`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `default` | `[String]` |  |  |


#### `Price`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `basePrice` | `Float` |  |  |
| `createdAt` | `Date` |  |  |
| `customFields` | `JSON` |  |  |
| `fees` | `[FeeThreshold]` |  |  |
| `id` | `ID!` |  |  |
| `isActive` | `Boolean` |  |  |
| `isDynamic` | `Boolean` |  |  |
| `key` | `String!` |  |  |
| `packagePrice` | `Float` |  |  |
| `price` | `Float!` |  |  |
| `sku` | `String!` |  |  |
| `unitPrice` | `Float` |  |  |
| `updatedAt` | `Date` |  |  |
| `packagesPrices` | `[PackagePrice]` |  |  |
| `isPackageRequired` | `Boolean` |  |  |


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


#### `PricesReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `prices` | `[Price]` |  |  |
| `pagination` | `Pagination` |  |  |


#### `Process`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID!` |  |  |
| `callBackUrl` | `String` |  |  |
| `emailToNotify` | `String` |  |  |
| `inputType` | `InputStatus` |  |  |
| `originatingEntity` | `OriginatingEntityStatus` |  |  |
| `inputFileUrl` | `String` |  |  |
| `deactivate` | `Boolean` |  |  |
| `processId` | `String` |  |  |
| `executionMode` | `ExecutionMode` |  |  |
| `status` | `ProcessStatus` |  |  |
| `startDate` | `Date` |  |  |
| `endDate` | `Date` |  |  |
| `result` | `ProcessResult` |  |  |
| `createdAt` | `Date` |  |  |
| `updatedAt` | `Date` |  |  |


#### `ProcessResult`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `status` | `ProcessResultStatus` |  |  |
| `logFilePath` | `String` |  |  |
| `errorId` | `Int` |  |  |
| `parsed` | `Int` |  |  |
| `total` | `Int` |  |  |
| `inserted` | `Int` |  |  |
| `description` | `String` |  |  |


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


#### `ProductBase`
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
| `createdAt` | `Date` |  |  |
| `description` | `String!` |  |  |
| `name` | `String!` |  |  |
| `updatedAt` | `Date` |  |  |
| `extraPackages` | `[ProductPackage]` |  |  |


#### `ProductPackage`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `name` | `String!` |  |  |
| `quantity` | `Int!` |  |  |
| `label` | `String!` |  |  |
| `jumpQty` | `Int` |  |  |
| `minQty` | `Int` |  |  |
| `maxQty` | `Int` |  |  |


#### `ProductsReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `products` | `[ProductBase]` |  |  |
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


#### `PromotionsReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `promotions` | `[Promotion]` |  |  |
| `pagination` | `Pagination` |  |  |


#### `RemindedSessions`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `storefrontName` | `String` |  |  |
| `sessions` | `[String]` |  |  |


#### `RemoveCacheResponse`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `success` | `Boolean` |  |  |


#### `RemovedSessionCarts`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `storefrontName` | `String` |  |  |
| `removedSessionsCount` | `Int` |  |  |
| `removedCartsCount` | `Int` |  |  |


#### `ReturnStock`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `enabled` | `Boolean` |  |  |
| `statuses` | `[OrderStatus]` |  |  |


#### `SalesRep`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID!` |  |  |
| `name` | `String!` |  |  |
| `routes` | `[String]` |  |  |
| `reps` | `[ID]` |  |  |
| `code` | `String!` |  |  |
| `phoneNumbers` | `[String]` |  |  |
| `customFields` | `JSON` |  |  |
| `isActive` | `Boolean` |  |  |


#### `SalesRepresentativesReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `salesRepresentatives` | `[SalesRep]` |  |  |
| `pagination` | `Pagination` |  |  |


#### `SchemasInfo`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `category` | `JSON` |  |  |
| `customer` | `JSON` |  |  |
| `price` | `JSON` |  |  |
| `product` | `JSON` |  |  |
| `promotion` | `JSON` |  |  |
| `salesRepresentative` | `JSON` |  |  |
| `stock` | `JSON` |  |  |
| `store` | `JSON` |  |  |


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


#### `Stock`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID!` |  |  |
| `sku` | `String!` |  |  |
| `key` | `String` |  |  |
| `stock` | `Int!` |  |  |
| `isActive` | `Boolean` |  |  |
| `customFields` | `JSON` |  |  |
| `createdAt` | `Date` |  |  |
| `updatedAt` | `Date` |  |  |
| `stockByPackage` | `[PackageStock]` |  |  |


#### `StocksReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `stocks` | `[Stock]` |  |  |
| `pagination` | `Pagination` |  |  |


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
| `additionalEmailsToNotify` | `[String]` |  |  |
| `addons` | `StorefrontAddOns` |  |  |
| `authorizedEmails` | `[String]` |  |  |
| `configuration` | `Configuration` |  |  |
| `configurationHash` | `String` |  |  |
| `createdAt` | `Date` |  |  |
| `customFields` | `JSON` |  |  |
| `endpoints` | `[Endpoint]` | ~~No longer supported~~ |  |
| `favoriteStatus` | `FavoriteStatus` |  |  |
| `id` | `ID` |  |  |
| `name` | `String!` |  |  |
| `owner` | `String!` |  |  |
| `ownerInfo` | `OwnerInfo!` |  |  |
| `productive` | `Boolean` |  |  |
| `status` | `StorefrontStatus` |  |  |
| `templateID` | `ID` | ~~No longer supported~~ |  |
| `updatedAt` | `Date` |  |  |


#### `StorefrontAddOns`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `after` | `[String]` |  |  |
| `instead` | `[String]` |  |  |
| `validation` | `[String]` |  |  |


#### `StorefrontMigrationResult`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `stockType` | `StockType` |  |  |
| `found` | `Int` |  |  |
| `migrated` | `Int` |  |  |


#### `StorefrontsReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `storefronts` | `[Storefront]` |  |  |
| `pagination` | `Pagination` |  |  |


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


#### `UsageLimitType`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `budgetId` | `ID` |  |  |
| `perCustomer` | `Int` |  |  |
| `perOrder` | `Int` |  |  |


#### `ValidProductRecommendation`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID!` |  |  |
| `description` | `String` |  |  |
| `imageUrl` | `[String]` |  |  |
| `isActive` | `Boolean!` |  |  |
| `name` | `String!` |  |  |
| `price` | `Float!` |  |  |
| `priority` | `Int` |  |  |
| `sku` | `String!` |  |  |
| `stock` | `Int` |  |  |


#### `VisitPlan`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `id` | `ID!` |  |  |
| `code` | `String!` |  |  |
| `salesRepCode` | `String!` |  |  |
| `customersCode` | `[String]` |  |  |
| `customersCodeToVisit` | `[String]` |  |  |
| `dateStart` | `String` |  |  |
| `dateEnd` | `String` |  |  |
| `customFields` | `JSON` |  |  |
| `isActive` | `Boolean` |  |  |


#### `VisitPlansReturned`
| Field | Type | Deprecated | Description |
|-------|------|-----------|-------------|
| `visitPlans` | `[VisitPlan]` |  |  |
| `pagination` | `Pagination` |  |  |


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

#### `AddOnAuthMethod`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `BEARER_TOKEN` |  |  |
| `JWT` |  |  |


#### `AddOnExecutionTime`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `AFTER` |  |  |
| `INSTEAD` |  |  |
| `VALIDATION` |  |  |


#### `AddOnMethod`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `DELETE` |  |  |
| `GET` |  |  |
| `PATCH` |  |  |
| `POST` |  |  |
| `PUT` |  |  |


#### `AddOnStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `DISABLED` |  |  |
| `ENABLED` |  |  |


#### `AddOnTypes`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CART_ADD_PRODUCT` |  |  |
| `CART_EMPTY` |  |  |
| `CART_REMOVE_PRODUCT` |  |  |
| `CATALOG` |  |  |
| `CATALOG_FLAT` |  |  |
| `CATEGORIES` |  |  |
| `CREATE_ORDER` |  |  |
| `CREATE_ORDERS` |  |  |
| `CREATE_SESSION` |  |  |
| `FREQUENTLY_BOUGHT_TOGETHER` |  |  |
| `GET_CHECKOUT_RULE` |  |  |
| `GET_PRODUCT_BY_SKU` |  |  |
| `GET_TOTAL_PROMOTIONS` |  |  |
| `LAST_ORDER` |  |  |
| `LINK` |  |  |
| `LINKED_PRODUCTS` |  |  |
| `ALTERNATIVE_PRODUCTS` |  |  |
| `LOYALTY_POINTS` |  |  |
| `PREFILL_CART` |  |  |
| `PREFILL_CART_MUTATION` |  |  |
| `PROMOTED_PRODUCTS` |  |  |
| `PROMOTION_ACTIVE_ENDPOINT` |  |  |
| `PROMOTION_FETCH_ENDPOINT` |  |  |
| `SEARCH_PRODUCT` |  |  |
| `SET_CHECKOUT_RULE` |  |  |
| `SUGGESTED_ITEMS` |  |  |
| `SUMMARY` |  |  |


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


#### `CheckMethod`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `PRE` |  |  |
| `POST` |  |  |


#### `CheckTypes`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `SKU` |  |  |
| `QUANTITY` |  |  |
| `EXTERNAL` |  |  |


#### `ComplexPromotionTypes`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `AMOUNT` |  |  |
| `DIRECT_PERCENTAGE` |  |  |
| `MIXED` |  |  |
| `PERCENTAGE` |  |  |
| `QUANTITY` |  |  |
| `QUANTITY_SELECTION` |  |  |


#### `ExecutionMode`
> The execution mode for the entity bulk creation.

| Value | Deprecated | Description |
|-------|-----------|-------------|
| `AUTOMATED` |  | The entity bulk creation will be executed automatically (by an integration or scheduled job). |
| `MANUAL` |  | The entity bulk creation will be executed manually (by a user through the UI). |


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


#### `InputStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `DATA` |  |  |
| `FILE_URL` |  |  |


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


#### `OriginatingEntityStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CATEGORIES` |  |  |
| `CUSTOMERS` |  |  |
| `PRICES` |  |  |
| `PRODUCTS` |  |  |
| `PROMOTIONS` |  |  |
| `STOCKS` |  |  |
| `STORES` |  |  |
| `SALES_REPS` |  |  |
| `SALES_REP_VISIT_PLANS` |  |  |


#### `PrefillCartTypeEnum`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `ML` |  |  |
| `LAST_ORDER` |  |  |
| `NONE` |  |  |


#### `ProcessResultStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `SUCCESS` |  |  |
| `ERROR` |  |  |
| `SUCCESS_WITH_WARNINGS` |  |  |


#### `ProcessStatus`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `NEW` |  |  |
| `PROCESSING` |  |  |
| `FINISHED` |  |  |
| `CANCELED` |  |  |


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
| `EXPECTED_DELIVERY_DATE` |  |  |


#### `SortByExtra`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `CREATED_AT` |  |  |
| `UPDATED_AT` |  |  |
| `PRIORITY` |  |  |


#### `SortByProcess`
| Value | Deprecated | Description |
|-------|-----------|-------------|
| `START_DATE` |  |  |
| `END_DATE` |  |  |
| `CREATED_AT` |  |  |
| `UPDATED_AT` |  |  |


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

