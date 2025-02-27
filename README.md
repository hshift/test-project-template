# test-project-template
A template repository for creating new C projects with built-in testing.

### 🔧 Setup Reminder
**Replace every occurrence of `test_template` with your new project name.**

**Always install pre-commit hooks after cloning!**

**Always build and install CppUTest after cloning!**

---

## 🚀 Pre-commit Hooks

Pre-commit helps catch simple issues before code is submitted. It manages and
runs hooks automatically before every commit. This repository is pre-configured
for C code.

### 📌 Installation

First, install the `pre-commit` package:

```sh
pip install pre-commit
```

### ▶️ Running

To install pre-commit into your Git hooks, run:

```sh
pre-commit install
```

This ensures pre-commit runs on every commit. Always do this after cloning a
project that uses pre-commit.

To manually run all hooks on the repository:

```sh
pre-commit run --all-files
```

To run a specific hook:

```sh
pre-commit run <hook_id>
```

### ⚙️ Configuration

The configuration file is located in the root directory as
`.pre-commit-config.yaml`.

---

## 🧪 Test-Driven Development (TDD)

This template follows a **TDD** approach. The project includes **CppUTest** as
a submodule for unit testing. All test-related files (framework, mocks, etc.)
are located in the `Test/` directory.

After cloning, initialize the submodule:

```sh
git submodule update --init
```

### 🔨 Installing CppUTest

To compile **CppUTest**, install the following dependencies:

- `gcc`
- `g++`
- `make`
- `git`
- `autoconf`
- `libtool`

For **Debian-based systems**, install them with:

```sh
sudo apt update && sudo apt install -y gcc g++ make git autoconf libtool
```

Then, compile CppUTest:

```sh
cd cpputest
./autogen.sh
./configure
make
```

Once compiled, you should see two files in the `lib/` folder:

- `libCppUTest.a`
- `libCppUTestExt.a`

### 🛠 Fixing "dirty" submodule issues

If Git complains about a **"dirty"** submodule, run:

```sh
git config --global diff.ignoreSubmodules dirty
```

---

## 🏃 Running Tests

After installing CppUTest, execute tests with:

```sh
make -C test
```

Run this from the project root directory.
