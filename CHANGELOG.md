## 0.8.0 (February 08, 2023)

NOTES:

* This Go module has been updated to Go 1.18 per the [Go support policy](https://golang.org/doc/devel/release.html#policy). Any consumers building on earlier Go versions may experience errors. ([#95](https://github.com/hashicorp/terraform-plugin-log/issues/95))

BUG FIXES:

* tflog+tflogsdk: Prevented data race conditions when using SetField and other option functions ([#132](https://github.com/hashicorp/terraform-plugin-log/issues/132))

# 0.7.0 (July 25, 2022)

FEATURES:
 
* tflog: Added `MaskAllFieldValuesRegexes()`, `MaskAllFieldValuesStrings()`, `MaskLogRegexes()` and `MaskLogStrings()` functions, which extend further the log masking filtering, for the provider root logger ([#87](https://github.com/hashicorp/terraform-plugin-log/issues/87))
* tflog: Added `SubsystemMaskAllFieldValuesRegexes()`, `SubsystemMaskAllFieldValuesStrings()`, `SubsystemMaskLogRegexes()` and `SubsystemMaskLogStrings()` functions, which extend further the log masking filtering, for provider subsystem loggers ([#87](https://github.com/hashicorp/terraform-plugin-log/issues/87))
* tfsdklog: Same functions added to the `tflog` package ([#87](https://github.com/hashicorp/terraform-plugin-log/issues/87))

# 0.6.0 (July 15, 2022)

BREAKING CHANGES:

* tflog: renamed `With()` and `SubsystemWith()`, to `SetField()` and `SubsystemSetField()` respectively ([#78](https://github.com/hashicorp/terraform-plugin-log/issues/78))
* tflog: renamed `WithMaskFieldValueWithFieldKeys()` and `SubsystemWithMaskFieldValueWithFieldKeys()`, to `MaskFieldValuesWithFieldKeys()` and `SubsystemMaskFieldValuesWithFieldKeys()` respectively ([#78](https://github.com/hashicorp/terraform-plugin-log/issues/78))
* tflog: renamed `WithMaskLogMatchingString()` and `SubsystemWithMaskLogMatchingString()`, to `MaskMessageStrings()` and `SubsystemMaskMessageStrings()` respectively ([#78](https://github.com/hashicorp/terraform-plugin-log/issues/78))
* tflog: renamed `WithMaskMessageRegex()` and `SubsystemWithMaskMessageRegex()`, to `MaskMessageRegexes()` and `SubsystemMaskMessageRegexes()` respectively ([#78](https://github.com/hashicorp/terraform-plugin-log/issues/78))
* tflog: renamed `WithOmitLogMatchingString()` and `SubsystemWithOmitLogMatchingString()`, to `OmitLogWithMessageStrings()` and `SubsystemOmitLogWithMessageStrings()` respectively ([#78](https://github.com/hashicorp/terraform-plugin-log/issues/78))
* tflog: renamed `WithOmitLogWithFieldKeys()` and `SubsystemWithOmitLogWithFieldKeys()`, to `OmitLogWithFieldKeys()` and `SubsystemOmitLogWithFieldKeys()` respectively ([#78](https://github.com/hashicorp/terraform-plugin-log/issues/78))
* tflog: renamed `WithOmitLogWithMessageRegex()` and `SubsystemWithOmitLogWithMessageRegex()`, to `OmitLogWithMessageRegexes()` and `SubsystemOmitLogWithMessageRegexes()` respectively ([#78](https://github.com/hashicorp/terraform-plugin-log/issues/78))
* tfsdklog: same renaming as for the `tflog` package ([#78](https://github.com/hashicorp/terraform-plugin-log/issues/78))

# 0.5.0 (July 14, 2022)

FEATURES:

* tflog: Added `SubsystemWithOmitLogWithFieldKeys()`, `SubsystemWithOmitLogWithMessageRegex()`, `SubsystemWithOmitLogMatchingString()`, `SubsystemWithMaskFieldValueWithFieldKeys()`, `SubsystemWithMaskMessageRegex()` and `SubsystemWithMaskLogMatchingString()` functions, which provide log omission and log masking filtering, based on message and argument keys, for provider subsystem loggers ([#71](https://github.com/hashicorp/terraform-plugin-log/issues/71))
* tflog: Added `WithOmitLogWithFieldKeys()`, `WithOmitLogWithMessageRegex()`, `WithOmitLogMatchingString()`, `WithMaskFieldValueWithFieldKeys()`, `WithMaskMessageRegex()` and `WithMaskLogMatchingString()` functions, which provide log omission and log masking filtering, based on message and argument keys, for the provider root logger ([#71](https://github.com/hashicorp/terraform-plugin-log/issues/71))
* tfsdklog: Added `SubsystemWithOmitLogWithFieldKeys()`, `SubsystemWithOmitLogWithMessageRegex()`, `SubsystemWithOmitLogMatchingString()`, `SubsystemWithMaskFieldValueWithFieldKeys()`, `SubsystemWithMaskMessageRegex()`and `SubsystemWithMaskLogMatchingString()` functions, which provide log omission and log masking filtering, based on message and argument keys, for SDK subsystem loggers ([#71](https://github.com/hashicorp/terraform-plugin-log/issues/71))
* tfsdklog: Added `WithOmitLogWithFieldKeys()`, `WithOmitLogWithMessageRegex()`, `WithOmitLogMatchingString()`, `WithMaskFieldValueWithFieldKeys()`, `WithMaskMessageRegex()` and `WithMaskLogMatchingString()` functions, which provide log omission and log masking filtering, based on message and argument keys, for the SDK root logger ([#71](https://github.com/hashicorp/terraform-plugin-log/issues/71))

# 0.4.1 (June 6, 2022)

NOTES:

* The `gopkg.in/yaml.v3` dependency has been updated to address CVE-2022-28948 ([#69](https://github.com/hashicorp/terraform-plugin-log/issues/69))

# 0.4.0 (May 4, 2022)

NOTES:

* This Go module has been updated to Go 1.17 per the [Go support policy](https://golang.org/doc/devel/release.html#policy). Any consumers building on earlier Go versions may experience errors. ([#51](https://github.com/hashicorp/terraform-plugin-log/issues/51))

FEATURES:

* Added `tflogtest` package, which provides functionality for unit testing of provider logging ([#62](https://github.com/hashicorp/terraform-plugin-log/issues/62))
* Added `tfsdklogtest` package, which provides functionality for unit testing of SDK logging ([#62](https://github.com/hashicorp/terraform-plugin-log/issues/62))

ENHANCEMENTS:

* tflog: Added `WithRootFields()` function, which can copy root logger fields to a new subsystem logger during `NewSubsystem()` ([#60](https://github.com/hashicorp/terraform-plugin-log/issues/60))
* tfsdklog: Added `WithRootFields()` function, which can copy root logger fields to a new subsystem logger during `NewSubsystem()` ([#60](https://github.com/hashicorp/terraform-plugin-log/issues/60))

BUG FIXES:

* tflog+tfsdklog: Prevented `Unable to create logging subsystem with AdditionalLocationOffset due to missing root logger options` warning logs during acceptance testing ([#58](https://github.com/hashicorp/terraform-plugin-log/issues/58))

# 0.3.0 (March 10, 2022)

NOTES:

* The following Go modules, if used, must be also be updated when updating to this terraform-plugin-log version:
    * [terraform-plugin-framework](https://github.com/hashicorp/terraform-plugin-framework/blob/main/CHANGELOG.md): v0.6.0 or higher
    * [terraform-plugin-go](https://github.com/hashicorp/terraform-plugin-go/blob/main/CHANGELOG.md): v0.8.0 or higher
    * [terraform-plugin-mux](https://github.com/hashicorp/terraform-plugin-mux/blob/main/CHANGELOG.md): v0.6.0 or higher
    * [terraform-plugin-sdk](https://github.com/hashicorp/terraform-plugin-sdk/blob/main/CHANGELOG.md): v2.11.0 or higher

BREAKING CHANGES:

* tflog: The `Trace()`, `Debug()`, `Info()`, `Warn()`, and `Error()` functions and `Subsystem` equivalents now use `...map[string]interface{}` as the final optional parameter, where the `string` is the structured logging key, rather than expecting matched `key interface{}, value interface{}` pairs. If multiple maps contain the same key, the value is shallow merged. ([#34](https://github.com/hashicorp/terraform-plugin-log/issues/34))
* tfsdklog: The `Trace()`, `Debug()`, `Info()`, `Warn()`, and `Error()` functions and `Subsystem` equivalents now use `...map[string]interface{}` as the final optional parameter, where the `string` is the structured logging key, rather than expecting matched `key interface{}, value interface{}` pairs. If multiple maps contain the same key, the value is shallow merged. ([#34](https://github.com/hashicorp/terraform-plugin-log/issues/34))

ENHANCEMENTS:

* tflog: Added `WithAdditionalLocationOffset` function, which allows implementations to adjust the location offset when using helper functions ([#36](https://github.com/hashicorp/terraform-plugin-log/issues/36))
* tfsdklog: Added `WithAdditionalLocationOffset` function, which allows implementations to adjust the location offset when using helper functions ([#36](https://github.com/hashicorp/terraform-plugin-log/issues/36))

BUG FIXES:

* tfsdklog: Consolidated multiple invalid log level messages and added missing newline ([#35](https://github.com/hashicorp/terraform-plugin-log/issues/35))

# 0.2.1 (December 23, 2021)

BUG FIXES:

* Fixed a panic when logging to a subsystem when logging has not been set up on the context. Should only impact unit tests and other situations where an SDK isn't instantiating the logging context. ([#24](https://github.com/hashicorp/terraform-plugin-log/issues/24))

# 0.2.0 (December 07, 2021)

BREAKING CHANGES:

* Provider log outputs now default to being named "provider" unless another name is provided. ([#9](https://github.com/hashicorp/terraform-plugin-log/issues/9))
* The `tflog` package has been moved to `github.com/hashicorp/terraform-plugin-log/tflog` to make it work better with goimports and other tooling. ([#7](https://github.com/hashicorp/terraform-plugin-log/issues/7))
* The `tfsdklog` package has been moved to `github.com/hashicorp/terraform-plugin-log/tfsdklog` to make it work better with goimports and other tooling. ([#7](https://github.com/hashicorp/terraform-plugin-log/issues/7))
* With the release of Go 1.17, Go 1.16 is now the lowest supported version of Go to use with terraform-plugin-log. ([#8](https://github.com/hashicorp/terraform-plugin-log/issues/8))
* `tflog.New` has been moved to `tfsdklog.NewRootProviderLogger`. Provider developers should not need this functionality. ([#10](https://github.com/hashicorp/terraform-plugin-log/issues/10))
* `tflog.Option` has been moved to an internal package. Consumers can no longer reference the type. ([#10](https://github.com/hashicorp/terraform-plugin-log/issues/10))
* `tflog.WithLogName` has been removed. SDK developers should use `tfsdklog.WithLogName`. Provider developers should not need this functionality. ([#10](https://github.com/hashicorp/terraform-plugin-log/issues/10))
* `tflog.WithStderrFromInit` has been removed. SDK developers should use `tfsdklog.WithStderrFromInit`. Provider developers should not need this functionality. ([#10](https://github.com/hashicorp/terraform-plugin-log/issues/10))
* `tfsdklog.New` has been renamed `tfsdklog.NewRootLogger`. ([#10](https://github.com/hashicorp/terraform-plugin-log/issues/10))
* `tfsdklog.Option` has been moved to an internal package. Consumers can no longer reference the type. ([#10](https://github.com/hashicorp/terraform-plugin-log/issues/10))

FEATURES:

* Added a `tfsdklog.RegisterTestSink` function that will turn on a logging sink appropriate for use in testing. When a logging sink is activated, all downstream provider and SDK loggers (i.e., all loggers created after `tfsdklog.RegisterTestSink` is called) will be sub-loggers of the sink. The sink respects the `TF_LOG`, `TF_LOG_PATH`, `TF_ACC_LOG_PATH`, and `TF_LOG_PATH_MASK` environment variables, by default discards logs, and when only `TF_LOG` is set writes to stderr. It is meant to replicate Terraform's log aggregation and filtering capabilities for test frameworks. ([#9](https://github.com/hashicorp/terraform-plugin-log/issues/9))

# 0.1.0 (June 24, 2021)

FEATURES:

* Build out the beginnings of the module, allowing for providers, SDKs, and their subsystems to use an opinionated interface to log data about their execution. ([#2](https://github.com/hashicorp/terraform-plugin-log/issues/2))
