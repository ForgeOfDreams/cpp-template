# 🚀 C++ Project Template

A modern, structured, and easy-to-use template for C++ projects. This repository provides a solid foundation with best practices, build system integration, and CI/CD automation.

## 📁 Project Structure

```bash
cpp-template/
├── cmake/              # CMake files
├── examples/           # Examples
├── src/                # Source code
├── include/            # Header files
├── tests/              # Unit tests (GoogleTest, Catch2, etc.)
├── CMakePresets.json   # CMake presets
├── README.md           # Documentation
├── .gitignore          # Ignored files
├── .clang-format       # Code formatting settings
└── CMakeLists.txt      # CMake build system
```

## ⚡ Features

✅ CMake Support – Easy and portable build system
✅ GitHub Actions – Automated build and test workflows
✅ Unit Testing – GoogleTest, Catch2, or other frameworks
✅ .clang-format – Code style enforcement
✅ Modular Structure – Clean and maintainable project organization

## 🚀 Getting Started

### 1️⃣ Clone the repository

```sh
git clone https://github.com/ForgeOfDreams/cpp-template.git
cd cpp-template
```

### 2️⃣ Build the project

```sh

cmake -S . -B build/<preset dev-linux or dev-win>
cmake --build build/<preset dev-linux or dev-win> --config Release

```

## 🎯 Usage

This repository is a template repository. Click "Use this template" on GitHub to create a new repository with this structure.

## 🛠️ Customization

* Modify CMakeLists.txt to fit your project needs.
* Add dependencies using vcpkg or Conan.