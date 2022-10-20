Ocarina of Time: Randomizer Development
========================================
Ocarina of Time Randomizer is a rom hack of regular Ocarina 
of Time, which involves utilizing a combination of C and 
Python to place items randomly throughout the world. The main 
repository being used for development is managed by 
`TestRunner <https://github.com/TestRunnerSRL/OoT-Randomizer>`_, 
but a lot of heavy development is being managed by a repository 
managed by `Roman971 <https://github.com/Roman971/OoT-Randomizer>`_.

Compiling
---------------
The project is split into two unique parts: the C code and the 
Python code.

Compiling Assembly and C on macOS
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Getting the N64 development tools is required, see 
:ref:`n64_development_tools` for more details on obtaining the tools.

An `assembly program <https://github.com/Kingcom/armips>`_ for 
MIPS is also required for the assembly code. The build 
instructions work completely fine on macOS, just make sure 
CMake is installed (brew).

A base uncompressed rom is required to compile the assembly and C 
code. A decompressor program is included in the repository at 
``bin/Decompress``. After decompressing the rom, put it at 
``ASM/roms/base.z64``.

Once all of this is configured, run 
``python3 ASM/build.py --compile-c``.

Running Python on macOS
~~~~~~~~~~~~~~~~~~~~~~~~
Everything works as described in the README, minus the GUI. 
The GUI requires electron 4.x, which released in 2019. M1 Macs 
began releasing publicly in late 2020. Oops. *Maybe* possible to 
build this release from source for Apple Silicon? But frankly, the 
real solution is to just update dependencies.

Other than that, the CLI program works perfectly fine, at least 
through what I've been testing.
