# System programming notes

by Christopher J. Brody AKA @brodybits (Chris Brody)

LICENSE: CC BY 4.0 (<https://creativecommons.org/licenses/by/4.0/legalcode>, <https://creativecommons.org/licenses/by/4.0/>)

## What

Lower-level programming of software components that are used by other systems programmers, higher-level applications programmers, and other experienced software systems engineers.

General reference with other characteristics: <https://en.wikipedia.org/wiki/System_programming>

Major characteristics:
- designed for certain types of hardware
- limited run-time library requirements
- direct memory access
- needs careful resource management
- not always easy to debug

## Comparison

General types of software, with limited overlap:
- Application software (designed for specific tasks, SHOULD deal with UX)
- System software
- Enterprise software

General ref: <https://en.wikipedia.org/wiki/Programmer>

Additional (various levels of overlap):
- Embedded programming is generally a subset of systems programming.
- Game programming (possible overlap with system programming)
- Scalable software (overlap with other areas)
- Financial software (using languages such as C++ to achieve competitive efficiency)
- machine learning, neural networks, and other forms of AI

## Kinds of system software

Some kinds of system software:
- kernel
- system libraries
- system services
- I/O and concurrency libraries
- other commonly-used libraries such as string manipulation, collections, etc.
- parallel software libraries and frameworks
- compilers
- VM
- interpreters
- other low-level application libraries

## System programming languages

General-purpose:
- C
- C++
- Rust
- Java
- Objective-C and Swift
- Go
- AssemblyScript (<https://github.com/AssemblyScript>)

Middle:
- Haskel
- Erlang

Limited:
- Python
- JavaScript

## Application stacks

Some application stacks using system programming:
- Jakarta EE née Java 2 EE
- Vert.x
- Node.js
- Cordova
- Jasonette to build native Android and iOS apps using JSON

## Bridging

- N-API (Node.js, etc.)
- Nan (C++ wrapper for Node.js addons)
- libffi
- Cordova

## Virtualization

- VMs
- LLVM
- Web assembly (revolutionary)

## Transpilers

- Emscripten

## Middleware

- OpenMQ, Zero MQ, etc.

## Tools

- <http://klee.github.io/> - LLVM-based tool that creates test cases from all possible paths through code

## Important tips

### Undefined behavior

Undefined behavior in C:

- <https://hackernoon.com/so-you-think-you-know-c-8d4e2cd6f6a6>
- <https://kukuruku.co/post/i-do-not-know-c/>
- <http://blog.llvm.org/2011/05/what-every-c-programmer-should-know.html>
- <https://blog.regehr.org/archives/213>

### ptrdiff_t

As taught in a Safer C (<http://www.saferc.com/>) course (Eindhoven, NL in September 2011):

In C and C++ `ptrdiff_t` is the safest way to convert between pointers and integer values. NULL is usually but NOT required to be `(void *)(0)`. To convert pointer to `ptrdiff_t`:

    ptrdiff_t mydiff = (unsigned char *)myptr - (unsigned char *)NULL;

To convert stored `ptrdiff_t` value to pointer:

    mytype_t * myptr = (mytype_t *)((unsigned char *)NULL + mydiff);

Recommended reading: <https://www.viva64.com/en/a/0050/>

Counterpoint: <https://blogs.msdn.microsoft.com/david_leblanc/2008/09/02/ptrdiff_t-is-evil/>

Other resources:

- <https://www.codeguru.com/cpp/cpp/cpp_mfc/general/article.php/c16465/About-sizet-and-ptrdifft.htm>
- <https://software.intel.com/en-us/forums/intel-c-compiler/topic/534769>
- <http://cpgotchas.blogspot.com/2008/02/sizet-ptrdifft-and-offt.html>

## Storage

Non-replicated:

- SQLite

Replicated:

- Redis

## Other

Financial software sometimes uses low-level languages such as C++ to be competitive in terms of computational efficiency, low latency, etc.

## Recommended resources

Some recommended resources:

- <http://www.stroustrup.com/Programming/25_embedded.ppt>
- other <http://www.stroustrup.com/Programming/lecture-slides.html>
- other results of <https://www.google.com/search?q=stroustrup+systems+programming>
- <http://www.stroustrup.com/abstraction-and-machine.pdf>
- <http://www.modernescpp.com/index.php/requirements-of-embedded-programming>
- <http://www.modernescpp.com/index.php/component/jaggyblog/objectoriented-generic-and-functional-programming>
- <http://www.saferc.com/> (book and training)
