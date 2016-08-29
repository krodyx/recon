recon-config
============

Recon configuration management.

### Configuration

All projects hoping to use Recon should have a `.reconrc` file at their root.

- `files` *(required)* - [Glob](https://en.wikipedia.org/wiki/Glob_(programming)) pattern telling which files
recon should parse. This should be pretty much all js files in your application which are likely to
be used by or use a component. It is recommended to exclude any meta files such as tests.
- `resolve` - Namespace to help recon resolve require/import paths correctly
  - `roots` - An array of paths (relative to working directory) from which to resolve paths.
  Eg. `require('components/button')` and `roots: [core]` would look in `core/components/button`
  - `extensions` - An array of extensions to resolve. Default: `['.js', '.jsx']`

##### Example configuration

```json
{
	"files": "src/**/!(*-test|*-tests|*.manifest).js*",
  "resolve": {
    "roots": [
      "src/core",
      "src"
    ]
  }
}
```