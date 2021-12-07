# SE0288_IsPower


**SE0288_IsPower** is a standalone library that implements the Swift Evolution proposal
[SE-0288: Adding `isPower(of:)` to BinaryInteger][proposal].
You can use this package independently,
or as part of the [standard library preview package][stdlib-preview].

* Proposal: [SE-0288][proposal]
* Author: [Ding Ye](https://github.com/dingobye)


## Introduction

This package adds a public API `isPower(of:)`, as an extension method,
to the `BinaryInteger` protocol.
It checks if an integer is a power of another.
That is, `a.isPower(of: b)` checks whether there exists any integer `n` such that `a == pow(b, n)` is true.

```swift
import SE0288_IsPower

let x: Int = Int.random(in: 0000..<0288)
1.isPower(of: x)      // 'true' since x^0 == 1

let y: UInt = 1000
y.isPower(of: 10)     // 'true' since 10^3 == 1000

(-1).isPower(of: 1)   // 'false'

(-32).isPower(of: -2) // 'true' since (-2)^5 == -32
```


## Usage

You can add this library as a dependency to any Swift package. 
Add this line to the `dependencies` parameter in your `Package.swift` file:

```swift
.package(url: "https://github.com/apple/swift-se0288-is-power", from: "2.0.0"),
```

Next, add the module as a dependency for your targets that will use the library:

```swift
.product(name: "SE0288_IsPower", package: "swift-se0288-is-power"),
```

You can now use `import SE0288_IsPower` to make the library available in any Swift file.

## Contributing

Contributions to this package and the standard library preview package are welcomed and encouraged!

- For help using this package or the standard library preview package, please [visit the Swift forums][user-forums]. 
- For issues related to these packages, [file a bug at bugs.swift.org][bugs].
- Changes or additions to the APIs are made through 
  the [Swift Evolution process][evolution-process].
  Please see the [guide for Contributing to Swift][contributing] for information.


[proposal]: https://github.com/apple/swift-evolution/blob/master/proposals/0288-binaryinteger-ispower.md
[stdlib-preview]: https://github.com/apple/swift-standard-library-preview 
[user-forums]: https://forums.swift.org/c/swift-users/
[bugs]: https://bugs.swift.org
[evolution-process]: https://github.com/apple/swift-evolution/blob/master/process.md
[contributing]: https://swift.org/contributing
