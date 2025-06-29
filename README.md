# cmate
[![DeepWiki](https://img.shields.io/badge/DeepWiki-rock--db%2Fcmate-blue.svg?logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAyCAYAAAAnWDnqAAAAAXNSR0IArs4c6QAAA05JREFUaEPtmUtyEzEQhtWTQyQLHNak2AB7ZnyXZMEjXMGeK/AIi+QuHrMnbChYY7MIh8g01fJoopFb0uhhEqqcbWTp06/uv1saEDv4O3n3dV60RfP947Mm9/SQc0ICFQgzfc4CYZoTPAswgSJCCUJUnAAoRHOAUOcATwbmVLWdGoH//PB8mnKqScAhsD0kYP3j/Yt5LPQe2KvcXmGvRHcDnpxfL2zOYJ1mFwrryWTz0advv1Ut4CJgf5uhDuDj5eUcAUoahrdY/56ebRWeraTjMt/00Sh3UDtjgHtQNHwcRGOC98BJEAEymycmYcWwOprTgcB6VZ5JK5TAJ+fXGLBm3FDAmn6oPPjR4rKCAoJCal2eAiQp2x0vxTPB3ALO2CRkwmDy5WohzBDwSEFKRwPbknEggCPB/imwrycgxX2NzoMCHhPkDwqYMr9tRcP5qNrMZHkVnOjRMWwLCcr8ohBVb1OMjxLwGCvjTikrsBOiA6fNyCrm8V1rP93iVPpwaE+gO0SsWmPiXB+jikdf6SizrT5qKasx5j8ABbHpFTx+vFXp9EnYQmLx02h1QTTrl6eDqxLnGjporxl3NL3agEvXdT0WmEost648sQOYAeJS9Q7bfUVoMGnjo4AZdUMQku50McDcMWcBPvr0SzbTAFDfvJqwLzgxwATnCgnp4wDl6Aa+Ax283gghmj+vj7feE2KBBRMW3FzOpLOADl0Isb5587h/U4gGvkt5v60Z1VLG8BhYjbzRwyQZemwAd6cCR5/XFWLYZRIMpX39AR0tjaGGiGzLVyhse5C9RKC6ai42ppWPKiBagOvaYk8lO7DajerabOZP46Lby5wKjw1HCRx7p9sVMOWGzb/vA1hwiWc6jm3MvQDTogQkiqIhJV0nBQBTU+3okKCFDy9WwferkHjtxib7t3xIUQtHxnIwtx4mpg26/HfwVNVDb4oI9RHmx5WGelRVlrtiw43zboCLaxv46AZeB3IlTkwouebTr1y2NjSpHz68WNFjHvupy3q8TFn3Hos2IAk4Ju5dCo8B3wP7VPr/FGaKiG+T+v+TQqIrOqMTL1VdWV1DdmcbO8KXBz6esmYWYKPwDL5b5FA1a0hwapHiom0r/cKaoqr+27/XcrS5UwSMbQAAAABJRU5ErkJggg==)](https://deepwiki.com/rock-db/cmate)

<!-- DeepWiki badge generated by https://deepwiki.ryoppippi.com/ -->

**cmate** is a tool to generate a Makefile from a TOML configuration file (`Cmate.toml`).

It simplifies project setup and build management for C projects through declarative configuration.

---

## Features

- Generate a `Makefile` from a TOML-based project description.
- Initialize a new project with `src/`, `include/`, and a working `main.c`.
- Support for `--build` to immediately generate and run `make`.
- Works cross-platform (POSIX + Windows with ANSI enabled).
- MIT licensed.

---

## Usage

```bash
cmate [options]
````

### Options

* `-h`, `--help` : Show help.
* `-v`, `--version` : Show version info.
* `-i`, `--init` : Generate sample `Cmate.toml` and project scaffold.
* `-o`, `--output <file>` : Output filename for Makefile (default: `Makefile`).
* `-t`, `--toml <file>` : Use custom TOML config (default: `Cmate.toml`).
* `-b`, `--build` : Immediately run `make` after generating Makefile.

---

## Example

1. Initialize a project:

   ```bash
   cmate --init
   ```

2. Edit the generated `Cmate.toml` to match your project settings.

3. Generate a Makefile:

   ```bash
   cmate
   ```

4. Or directly build:

   ```bash
   cmate --build
   ```

---

## Project Structure

After initialization:

```
project/
├── include/
├── src/
│   └── main.c
├── Cmate.toml
└── Makefile
```

---

## Dependencies

* **tomlc99**: used internally for TOML parsing
  (already bundled, no need for submodules or manual install)
* GNU Make (or compatible)

---

## Building cmate

```bash
git clone https://github.com/rock-db/cmate
cd cmate
./bootstrap.sh
make
```

---

## Notice for Windows Users

This software can be built on Windows, and a Windows binary is provided.  
However, **proper functionality on Windows is not guaranteed**.  

The main development and testing environment is Linux.  
The Windows version is provided as-is, and may not work as expected.

If it works for you, great.  
**It does not work properly on my environment.**  
If it does not work for you either, the cause may be your environment or Windows itself.

Pull Requests to improve Windows support are always welcome.  
However, simple Issues without proposed fixes may be ignored.

---

## License

[MIT License](./docs/LICENSE)

