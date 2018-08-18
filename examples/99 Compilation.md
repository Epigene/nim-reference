## Compiling Nim

### Common complication examples

```
# complie a release build into bin
nim c -d:release -o:bin/app --nimcache:. src/app.nim 

# Crosscompilation!
  --os:SYMBOL               set the target operating system (cross-compilation)
  --cpu:SYMBOL              set the target processor (cross-compilation)
  
# compile for 64 bit Mac
nim c -d:release -o:bin/app --nimcache:. src/app.nim 
# compile for 64 bit Linux
nim c -d:release -o:bin/app --nimcache:. src/app.nim 
# compile for 64 bit Windows
nim c -d:release -o:bin/app --nimcache:. src/app.nim 

# GC optimization!
  --gc:refc|v2|markAndSweep|boehm|go|none|regions  select the GC to use; default is 'refc'

```

### Output of default help

```nim
$ nim -h
Nim Compiler Version 0.18.0 [Linux: amd64]
Copyright (c) 2006-2018 by Andreas Rumpf

    nim command [options] [projectfile] [arguments]

Command:
  compile, c                compile project with default code generator (C)
  doc                       generate the documentation for inputfile

Arguments:
  arguments are passed to the program being run (if --run option is selected)
Options:
  -p, --path:PATH           add path to search paths
  -d, --define:SYMBOL(:VAL)
                            define a conditional symbol
                            (Optionally: Define the value for that symbol)
  -u, --undef:SYMBOL        undefine a conditional symbol
  -f, --forceBuild          force rebuilding of all modules
  --stackTrace:on|off       turn stack tracing on|off
  --lineTrace:on|off        turn line tracing on|off
  --threads:on|off          turn support for multi-threading on|off
  -x, --checks:on|off       turn all runtime checks on|off
  --objChecks:on|off        turn obj conversion checks on|off
  --fieldChecks:on|off      turn case variant field checks on|off
  --rangeChecks:on|off      turn range checks on|off
  --boundChecks:on|off      turn bound checks on|off
  --overflowChecks:on|off   turn int over-/underflow checks on|off
  -a, --assertions:on|off   turn assertions on|off
  --floatChecks:on|off      turn all floating point (NaN/Inf) checks on|off
  --nanChecks:on|off        turn NaN checks on|off
  --infChecks:on|off        turn Inf checks on|off
  --nilChecks:on|off        turn nil checks on|off
  --deadCodeElim:on|off     whole program dead code elimination on|off
  --opt:none|speed|size     optimize not at all or for speed|size
                            Note: use -d:release for a release build!
  --debugger:native|endb    use native debugger (gdb) | ENDB (experimental)
  --app:console|gui|lib|staticlib
                            generate a console app|GUI app|DLL|static library
  -r, --run                 run the compiled program with given arguments
  --advanced                show advanced command line switches
  -h, --help                show this help
```

### Output of advanced options

```
nim --advanced
Nim Compiler Version 0.18.0 [Linux: amd64]
Copyright (c) 2006-2018 by Andreas Rumpf

Advanced commands:
  compileToC, cc          compile project with C code generator
  compileToCpp, cpp       compile project to C++ code
  compileToOC, objc       compile project to Objective C code
  js                      compile project to Javascript
  e                       run a Nimscript file
  rst2html                convert a reStructuredText file to HTML
  rst2tex                 convert a reStructuredText file to TeX
  jsondoc                 extract the documentation to a json file
  jsondoc2                extract the documentation to a json file (uses doc2)
  ctags                   create a tags file
  buildIndex              build an index for the whole documentation
  run                     run the project (with Tiny C backend; buggy!)
  genDepend               generate a DOT file containing the
                            module dependency graph
  dump                    dump all defined conditionals and search paths
  check                   checks the project for syntax and semantic

Advanced options:
  -o:FILE, --out:FILE       set the output filename
  --stdout                  output to stdout
  --colors:on|off           turn compiler messages coloring on|off
  --listFullPaths           list full paths in messages
  -w:on|off|list, --warnings:on|off|list
                            turn all warnings on|off or list all available
  --warning[X]:on|off       turn specific warning X on|off
  --hints:on|off|list       turn all hints on|off or list all available
  --hint[X]:on|off          turn specific hint X on|off
  --lib:PATH                set the system library path
  --import:PATH             add an automatically imported module
  --include:PATH            add an automatically included module
  --nimcache:PATH           set the path used for generated files
  --header:FILE             the compiler should produce a .h file (FILE
                            is optional)
  -c, --compileOnly         compile only; do not assemble or link
  --noLinking               compile but do not link
  --noMain                  do not generate a main procedure
  --genScript               generate a compile script (in the 'nimcache'
                            subdirectory named 'compile_$project$scriptext')
  --genDeps                 generate a '.deps' file containing the dependencies
  --os:SYMBOL               set the target operating system (cross-compilation)
  --cpu:SYMBOL              set the target processor (cross-compilation)
  --debuginfo               enables debug information
  -t, --passC:OPTION        pass an option to the C compiler
  -l, --passL:OPTION        pass an option to the linker
  --cincludes:DIR           modify the C compiler header search path
  --clibdir:DIR             modify the linker library search path
  --clib:LIBNAME            link an additional C library
                            (you should omit platform-specific extensions)
  --genMapping              generate a mapping file containing
                            (Nim, mangled) identifier pairs
  --project                 document the whole project (doc2)
  --docSeeSrcUrl:url        activate 'see source' for doc and doc2 commands
                            (see doc.item.seesrc in config/nimdoc.cfg)
  --lineDir:on|off          generation of #line directive on|off
  --embedsrc                embeds the original source code as comments
                            in the generated output
  --threadanalysis:on|off   turn thread analysis on|off
  --tlsEmulation:on|off     turn thread local storage emulation on|off
  --taintMode:on|off        turn taint mode on|off
  --implicitStatic:on|off   turn implicit compile time evaluation on|off
  --patterns:on|off         turn pattern matching on|off
  --memTracker:on|off       turn memory tracker on|off
  --excessiveStackTrace:on|off
                            stack traces use full file paths
  --oldNewlines:on|off      turn on|off the old behaviour of "\n"
  --skipCfg                 do not read the general configuration file
  --skipUserCfg             do not read the user's configuration file
  --skipParentCfg           do not read the parent dirs' configuration files
  --skipProjCfg             do not read the project's configuration file
  --gc:refc|v2|markAndSweep|boehm|go|none|regions
                            select the GC to use; default is 'refc'
  --index:on|off            turn index file generation on|off
  --putenv:key=value        set an environment variable
  --NimblePath:PATH         add a path for Nimble support
  --noNimblePath            deactivate the Nimble path
  --noCppExceptions         use default exception handling with C++ backend
  --excludePath:PATH        exclude a path from the list of search paths
  --dynlibOverride:SYMBOL   marks SYMBOL so that dynlib:SYMBOL
                            has no effect and can be statically linked instead;
                            symbol matching is fuzzy so
                            that --dynlibOverride:lua matches
                            dynlib: "liblua.so.3"
  --dynlibOverrideAll       makes the dynlib pragma have no effect
  --listCmd                 list the commands used to execute external programs
  --parallelBuild:0|1|...   perform a parallel build
                            value = number of processors (0 for auto-detect)
  --verbosity:0|1|2|3       set Nim's verbosity level (1 is default)
  --experimental            enable experimental language features
  -v, --version             show detailed version information

```
