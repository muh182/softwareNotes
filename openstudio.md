# Build Environments - Mac (2020)
* Follow the instructions [here](https://github.com/NREL/OpenStudio/wiki/Configuring-OpenStudio-Build-Environments). The `CMake` version specific is not compatible for symlinks in newer OS. The steps specified [here](https://stackoverflow.com/questions/30668601/installing-cmake-command-line-tools-on-a-mac) do not work. Please follow the next step. 
* Install CMake [here](https://cmake.org/download/).
* Configure the build with typing `cmake ..` in the `build` folder
* You may need to install `conan`. You can use `pip install conan`. There are good instructions [here](https://docs.conan.io/en/latest/installation.html)


# Build Environments (2019)
* Follow the instructions [here](https://github.com/NREL/OpenStudio/wiki/Configuring-OpenStudio-Build-Environments)
* Make sure to use Ruby 2.2.4. More details [here](https://github.com/NREL/OpenStudio-extension-gem#mac-installation)
  * Check ruby version with 'ruby --version'
  * You should see `ruby 2.2.4p230 (2015-12-16 revision 53155) [x86_64-darwin17]`
  * You can have multiple versions of ruby using `rvm`. This package allows you to switch between different ruby version. More details are accessible [here](https://rvm.io/)
  * You can install `rvm` with `rvm install ruby-2.2.4` or reinstall with `rvm reinstall ruby-2.2.4`


## Common Errors

* The following error is due to missing `aclocal` packge:
\
`./autogen.sh: line 11: aclocal: command not found`
\
The solution is to install `automake` and add it to the path.

* If you receive the following error, you need to make sure to have a `RUBYLIB` environment in `bash_profile`.

```
2.2.4 :001 > require 'openstudio'
LoadError: cannot load such file -- openstudio
	from /Users/Mohammad/.rvm/rubies/ruby-2.2.4/lib/ruby/site_ruby/2.2.0/rubygems/core_ext/kernel_require.rb:54:in `require'
	from /Users/Mohammad/.rvm/rubies/ruby-2.2.4/lib/ruby/site_ruby/2.2.0/rubygems/core_ext/kernel_require.rb:54:in `require'
	from (irb):1
	from /Users/Mohammad/.rvm/rubies/ruby-2.2.4/bin/irb:11:in `<main>'
```
\
The `RUBYLIB` points to the OpenStudio Application version installed on the system: `export RUBYLIB=/Applications/OpenStudio-2.8.0/Ruby`

