# DuckDNS client

DuckDns Updater is a Windows tray application that allows you to keep your
dynamic hostname's IP address up-to-date (and in sync) with the DuckDNS service
at <https://www.duckdns.org>.

## Building

1.  Open the repository in the provided Visual Studio Code devcontainer. (If
    not using vscode then you'll need to ensure that Java and Maven are
    configured in your environment, and that you have Launch4j and `wixl` or
    the WiX Toolset installed in order to create native EXEs and installers.)
2.  Run `mvn package` from the repository root to compile the source and
    generate a JAR file. This can be run (in Windows) by either double-clicking
    it or by running `java -jar duckdns-0.1.jar` from the command line.
3.  Run `/usr/bin/launch4j/launch4j installer/launch4j.xml` (or equivalent) to
    create a Windows executable in the `target` directory.
4.  Run `wixl installer/msi.wsx -o target/duckdns.msi` (or equivalent) to
    generate an installer in the `target` directory.

## License

This project is released under the terms of the GNU General Public License,
Version 2. See [LICENSE](LICENSE) for the full terms.

## TODO

-   Add license page to the installer and have it create a Start menu entry.
-   Automate builds.

## Author / Contact

-   @JozefJarosciak
    -   [ETX Software Inc.](http://www.etx.ca)
    -   [Blog](http://www.joe0.com)
    -   [LinkedIn Contact](https://www.linkedin.com/in/jozefj)
-   Additional work by [Chris Cunningham](https://github.com/thumperward)
