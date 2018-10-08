# C++ STL header files for code completion in vim

This is a modified version of the C++ STL header files for use with vim and ctags. 

### Requirements

- vim Version 7 and higher
- ctags
- OmniCppComplete https://github.com/yeti01/OmniCppComplete

### Installation

1. Put the header files into your vim folder

        $ cd $VIM
        $ git clone https://github.com/yeti01/vim-cpp-stl

2. Run ctags

        $ cd $VIM/vim-cpp-stl
        $ ctags -R --c++-kinds=+p --fields=+iaS --extra=+q --language-force=C++

3. Add the following lines to your `vimrc`

        set tags+=$VIM/vim-cpp-stl/tags
        let OmniCpp_DefaultNamespaces=["std"]

### Usage

Omni completion should work for STL classes now.

        string str;
        str.<CTRL-X>>CTRL-O>
           +------------------------------+
           | append(    std::basic_string |
           | assign(    std::basic_string |
           | at(        std::basic_string |
           | ...        std::basic_string |
           +------------------------------+
