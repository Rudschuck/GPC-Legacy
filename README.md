# GPC-Legacy /  GNU Pascal Compiler (GPC) — Binary Archive Repository

This repository hosts **precompiled binary distributions** of the **GNU Pascal Compiler (GPC)** for archival and legacy use.  
No source code is included here — the focus is on preserving **functional binaries** for systems and projects that still depend on GPC.


Further information regarding GPC can be found at:

* [>>> GNU Pascal Homepage <<<](https://www.gnu-pascal.de)


---

## 🏛️ Background and Motivation

The **GNU Pascal Compiler (GPC)** was once an official front end for the **GNU Compiler Collection (GCC)**, providing ISO-compliant Pascal support tightly integrated with GCC’s backend.  
Development of GPC effectively ceased around **2005**, and since then, no maintained or modernized binary packages have been available for most platforms.

Nevertheless, a considerable number of **legacy systems and scientific, industrial, or academic projects** still rely on GPC for building and maintaining their Pascal codebases.  
In many of these cases, recompiling with modern compilers (such as Free Pascal or modern GCC versions) is not feasible due to **incompatibilities or strict reproducibility requirements**.

This repository exists to **preserve functional GPC binaries** and make them easily available for legacy maintenance, historical research, and software archiving.


Original binaries can be found at:

* [>>> GNU GPC Binaries for Linux <<<](https://www.bndhep.net/Software/Pascal/Pascal.html)
* [>>> GNU GPC Binaries for Cygwin <<<](http://www.foyeh.org/gpc.htm)



---

## ⚙️ Technical Characteristics

The binaries included here are compiled with specific options to ensure **maximum compatibility** and **linking flexibility**.  
Notably, they are built to produce **relocatable code**, enabling use in **shared libraries** and dynamic linking scenarios — a feature that many older GPC builds lacked.

### Key build properties:
- ✅ Compiled with `-fPIC` or equivalent flags for **position-independent code**  
- ✅ Fully compatible with **shared object generation** and dynamic linking  
- ✅ Based on stable GCC backends (e.g., GCC 3.x series) for reproducibility  
- ✅ Includes runtime libraries necessary for GPC-based builds  
- ✅ Tested to support **cross-compilation scenarios** (in selected builds)  

These characteristics make the provided binaries particularly suitable for:
- Building **legacy scientific applications**  
- Maintaining **embedded or industrial systems** dependent on old Pascal code  
- **Reverse-engineering** or **rebuilding historical software** that relied on GPC  
- Ensuring **build reproducibility** in long-term archival environments


---

## 📦 Repository Contents

Each release folder or tag contains precompiled binary distributions for specific platforms.

Typical contents include:
- Precompiled GPC executables for selected platforms  
- Associated `libgpc` runtime libraries
- Header and include files (`*.h`, `*.gpi`, etc.)
- Example scripts or configuration files for integration with GCC
- Licensing information (`COPYING`, `README.gpc`)


All binary distributions are released as tar-packed files.


### 🚫 No Source Code
To avoid redundancy and confusion, **no GPC source code** is included in this repository.  
The official source (historically hosted on GNU mirrors) is publicly available through the **GNU archives** or **SourceForge snapshots**.


* [>>> GNU Pascal Homepage <<<](https://www.gnu-pascal.de/gpc/h-index.html)

---

## 🧩 Platform Compatibility

| Platform | Architecture | Binary Format | Tested | Notes |
|-----------|---------------|----------------|---------|--------|
| GNU/Linux     | x86_64      | ELF | ✅ | gpc-20070904-slc-6.5-64bit.tar.gz Recommended and most complete |
| GNU/Linux     | i686        | ELF | ✅ | gpc-20070904-slc-3.0-32bit.tar.gz Legacy 32-bit systems only |
| Windows       | x86 (MinGW) | PE  | ✅ | gpc-20070904-windows-7-32bit.tar.gzTested with MinGW32 environments |



If your system’s `glibc` or `libstdc++` versions differ significantly from those used during compilation, **dynamic linking issues** may occur.  
In such cases, static linking or containerized environments are recommended.

---

## 🧰 Usage

### Basic invocation



Example for an installation of the 64 bit GPC binary:

```bash
# Download from GitHub:
curl 'https://raw.githubusercontent.com/Rudschuck/GPC-Legacy/master/gpc-20070904-slc-6.5-64bit.tar.gz' --output gpc-master-64.tar.gz

# Extract into local directory:
tar -zxvf gpc-master-64.tar.gz

# Start from local directory:
./usr/local/bin/gpc myprogram.pas -o ./myprogram

```


## 📜 License & Copyright

GNU Pascal Compiler (GPC) and its runtime components are distributed under the **GNU General Public License (GPL)**.  
See the `COPYING` file included with the binaries for full details.


For issues related to using these binaries (installation, linking, etc.), please open an **Issue** in this repository.  
For historical or source-related information, refer to the archived GPC project pages or the GNU mailing lists.

(c) Dr. Michael Rudschuck
   

---

## Rev:
* 0.1: First release.
