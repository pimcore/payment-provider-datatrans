# Upgrade Notes

## Upgrade to 2026.1.0

### PHP & Pimcore Version Requirements
- Added support for `PHP` `8.5`.
- Removed support for `PHP` `8.3`.

### Return Type and Method Signature Changes
- `Datatrans::getName()`: Added native return type `string`.
- `Datatrans::handleResponse()`: Parameter type changed from untyped to `StatusInterface|array`; added native return type `StatusInterface`.
- `Datatrans::executeDebit()`: Parameters changed to nullable types (`?PriceInterface`, `?string`); added native return type `StatusInterface`.
- `Datatrans::processOptions()`: Added native return type `void`.
- `Datatrans::setAuthorizedData()`: Added native return type `void`.
- `Datatrans::setRecurringPaymentSourceOrderData()`: Return type changed from `bool` to `void` — method no longer returns `true` on success or `false` on failure; it now always logs an error and returns nothing if `setSourceOrder` is not available on the brick.
- `Datatrans::applyRecurringPaymentCondition()`: Return type changed from `Concrete` to `void` — method no longer returns the listing object.
- `Installer::$bricksPath`: Added native type `string`.
- `Installer::$bricksToInstall`: Added native type `array`.

### Bug Fixes
- `Datatrans::xmlRequest()`: `CURLOPT_POST` and `CURLOPT_RETURNTRANSFER` curl options are now passed as `true` (boolean) instead of `1` (integer), aligning with PHP best practices.
