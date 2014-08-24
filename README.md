ClangFormat-on-RHEL6
====================

if you want to use clang-format or want to build clang and llvm on RHEL6(Red Hat Enterprise Linux 6), Welcome!


Code in industry should be well readable and formated. clang-format is a tool which can automatically fix the C++ lint errors in your code. With its help, you can focus on what really matters in your code, rather than dealing with some minor lint errors such as additional white spaces or extra empty lines. 

Install
----

clang-format is part of the clang project and there are compiled binary files you can directly use from clang official site(http://llvm.org/releases/download.html). But there are no RHEL 6 version to download. So, I download and compile the clang project on RHEL 6 and provide the binary for you to use. After you install it, 
clang-format --help will let you know how to use it. You can specify the coding style to be LLVM, Google or Mozilla. 

The binary is here on dropbox: https://www.dropbox.com/s/wcr47njy29p9kt3/clang-format.

Integrate clang-format with vim
----

There is a vim plugin here which can format your entiry file with one shot. 
https://github.com/rhysd/vim-clang-format

Compile clang and llvm with gcc 4.7 at RHEL 6(Optional)
----

Compile clang and llvm on RHEL 6 is not a easy work. Mainly because the gcc version on RHEL 6 is lower than the compilation requirements. Here is how I compile the project if you are interested or wanna play with it:

* Setup devtools set package. Gcc 4.7 is part of this package. 

```sh
sudo wget -O /etc/yum.repos.d/slc6-devtoolset.repo http://linuxsoft.cern.ch/cern/devtoolset/slc6-devtoolset.repo
```
```sh
sudo yum install --nogpgcheck devtoolset-1.1
```
* Switch to devtoolset bash. After you setup devtoolset, you can play with gcc 4.7 with a simple command:

```sh
scl enable devtoolset-1.1 bash
```

After this, if you run gcc -v you can see the change of the version number. If you want to switch back, simply run exit. Then it will go back to your original bash. And if you run gcc -v at this time, you can tell the difference.

* Compile clang and llvm

Once we get gcc 4.7, we can follow the clang install tutorials and everything should be fine.
http://clang.llvm.org/get_started.html
