# Arcadia SwiftLint config

Shared SwiftLint config

To include it, create a `.swiftlint.yml` with the following content:
```
included:
  - <ProjectFolder>
parent_config: https://raw.githubusercontent.com/SoftwareCountry/arcadia-swiftlint-config/main/.swiftlint.yml
```

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
