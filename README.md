# network_ios: network related commands for ios_system


<p align="center">
<img src="https://img.shields.io/badge/Platform-iOS%2011.0+-lightgrey.svg" alt="Platform: iOS">
<a href="https://travis-ci.org/holzschu/network_ios"><img src="https://travis-ci.org/holzschu/network_ios.svg?branch=master" alt="Build Status"/></a>
<br>
<a href="http://twitter.com/nholzschuch"><img src="https://img.shields.io/badge/Twitter-@nholzschuch-blue.svg?style=flat" alt="Twitter"/></a>
</p>

[ios_system](https://github.com/holzschu/ios_system) is a replacement for `system()` that is compatible with AppStore rules and the iOS programming API. Commands are provided as dynamic libraries and loaded as they are required by the user. 

[ios_system](https://github.com/holzschu/ios_system) itself contains basic commands, operating on files (ls, mv, rm, tar, curl, grep...) More advanced commands are provided separately. `network_ios` is one of these extensions. To use it, just compile it and add it to the list of embedded libraries in your app (on top of all the libraries generated by [ios_system](https://github.com/holzschu/ios_system), of course). There is no change to make to ios_system: if the `libnetwork_ios.dylib` is present, it will execute the commands. Otherwise, it won't (but that's hardly surprising). 

Commands available in this package: 
- ping
- nc (netcat)
- nslookup
- host
- dig
- telnet

If you run them inside [OpenTerm](https://github.com/louisdh/terminal), the interactive versions work. I can't speak for other applications. 

## How to compile:

- run the script `sh ./get_frameworks.sh`. This will download the `ios_system` framework.
- open `network_ios.xcodeproj` and compile
- place `libnetwork_ios.dylib` along with the other libraries generated by `ios_system`. 
