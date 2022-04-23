# Summary
NuGetDefense.Lib provides programmatic access to all the features of NuGetDefense. The main use is in the Scanner.Scan method which returns the number of vulnerabilities found.

## Scanner

### Scan(Scanoptions)
Scan is the main method and performs the same scan as NuGetDefense

### GetNonSensitivePackages(out Dictionary<string, NuGetPackage[]>)
Reads SensitivePackages in Settings and escapes all characters for Regex, then replaces `*` with `.*` (Regex wild Card for 0 or more of any character). Then returns a list of packages that do not match the wild card strings in SensitivePackages.

## Scanoptions

### Cache
Currently this only accepts a SQLLitVulnerabilityCache (with `Path` and `Enabled`) fields. Future versions will include a Type field to support non-local caches.