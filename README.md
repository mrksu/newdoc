# README: The newdoc tool

The `newdoc` tool generates pre-populated module and assembly files formatted with AsciiDoc, which are used in Red Hat and Fedora documentation. The generated files follow the template guidelines maintained by the Modular Documentation initiative: <https://redhat-documentation.github.io/modular-docs/>.

The tool is written in the Rust programming language.

It has not been tested on Microsoft Windows.


## Installing newdoc

* To install `newdoc` on Fedora, RHEL, or CentOS, use the Copr package repository:

    ```
    # dnf copr enable mareksu/newdoc-rs
    # dnf install newdoc
    ```

* On a different Linux distribution, on macOS, or on Microsoft Windows, use the `cargo` package manager:

    ```
    # cargo install newdoc
    ```

    For installing `cargo`, see <https://rustup.rs/>.

    Note that `newdoc` has not been tested on Microsoft Windows.

## Creating a new module

1. In the directory where modules are located, use `newdoc` to create a new file:

    ```
    modules-dir]$ newdoc --procedure "Setting up thing"
    ```

    The script also accepts the `--concept` and `--reference` options. You can use these short forms instead: `-p`, `-c`, and `-r`.

2. Rewrite the placeholders in the generated file with your docs.


## Creating a new assembly

1. In the directory where assemblies are located, use `newdoc` to create a new file:

    ```
    assemblies-dir]$ newdoc --assembly "Achieving thing"
    ```
    
    You can use the short form of the `--assembly` option instead: `newdoc -a "Achieving thing"`.
    
2. Rewrite the placeholders in the generated file with your docs.

    Add AsciiDoc include statements to include modules. See [Include Files](https://asciidoctor.org/docs/asciidoc-syntax-quick-reference/#include-files) in the AsciiDoc Syntax Quick Reference.



## Options


* To generate the file without the explanatory comments, add the `--no-comments` or `-C` option when creating documents.

* To create the file without the file-name prefix, add the `--no-prefixes` or `-P` option.

* To specify the directory where `newdoc` saves the generated file, add the `--target-dir=<directory>` or `-T <directory>` option.


## Additional resources

* [Modular Documentation Reference Guide](https://redhat-documentation.github.io/modular-docs/)
* [AsciiDoc Mark-up Quick Reference for Red Hat Documentation](https://redhat-documentation.github.io/asciidoc-markup-conventions/)
