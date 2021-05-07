# Arcadia SwiftLint config

Adding SwiftLint as an SPM dependency:
```swift
let package = Package(
    name: "ProjectName",
    dependencies: [
        .package(url: "https://github.com/Realm/SwiftLint", .upToNextMinor(from: "0.42.0")),
        .package(url: "https://github.com/SwiftGen/SwiftGen", .exact("6.4.0")),
    ],
    targets: [
        .target(
            name: "<ProjectName>",
            path: "<ProjectName>"
        )
    ]
)
```

Adding swiftLint as a Cocoapods dependency:
```
pod 'SwiftLint', '0.42.0'
```

Shared SwiftLint config

To include it, create a `.swiftlint.yml` with the following content:
```
included:
  - <ProjectFolder>
parent_config: https://raw.githubusercontent.com/SoftwareCountry/arcadia-swiftlint-config/main/.swiftlint.yml
```

To include autocorrection config, create a `.swiftlint.auto.yml` with the following content:
```
included:
  - <ProjectFolder>
parent_config: https://raw.githubusercontent.com/SoftwareCountry/arcadia-swiftlint-config/main/.swiftlint.auto.yml
```

Add Swiftlint build phase (before Compile Sources):
```
SWIFTLINT="${PODS_ROOT}/SwiftLint/swiftlint"
"$SWIFTLINT" autocorrect --config ".swiftlint.auto.yml" && "$SWIFTLINT"
```
