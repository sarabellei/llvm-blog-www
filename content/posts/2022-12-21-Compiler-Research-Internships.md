---
author: "Sara Bellei"
date: "2022-12-21"
tags: ["Compiler Research", "internships", "Google Summer of Code 2022", "clang", "llvm", "Clang-Repl", "Incremental C++", "JITLink", "Clad"]
title: "Interactive programming in C++ internships — LLVM 
Blog Post"
----------------------------------------------------------------


Another program year is ending and we are extremely happy to share the hard 
work and the results of our interns contributors!


This year the <a href="https://compiler-research.org/">Compiler Research</a> 
group had six participants who worked on seven projects, covering a wide 
range of topics, from LLVM’s new JIT linker 
(<a href="https://llvm.org/docs/JITLink.html#jit-linking">JITLink</a>) to 
<a href="https://clang.llvm.org/docs/ClangRepl.html">Clang-Repl</a>, 
an interactive C++ interpreter for incremental compilation integrated 
in <a href="https://clang.llvm.org/">Clang</a>. All projects rise toward a 
common, ambitious goal: **to establish a proficient workflow in LLVM, 
where <a href="https://compiler-research.org/interactive_cpp">interactive 
development in C++</a> is possible, and exploratory C++ becomes an accessible 
experience to a wider audience.**

Below you can find the list of projects from our interns, an overview of the 
objectives and results. We invite you to follow the links to access a more 
detailed description of each project.

<a href="https://compiler-research.org/assets/docs/Sunho_Kim_GSoC22_Report.pdf">JITLink support for a new format/architecture (ELF/AARCH64)</a>
------------------------------------------------------------------------------------------------------------------------------------------------
Developer: **<a href="https://github.com/sunho">Sunho Kim</a>** 
(*Computer Science, De Anza College, Cupertino, California*)

Mentors: **Stefan Gränitz** (*Freelance Compiler Developer, Berlin, 
Deutschland*), 
**Lang Hames** (*Apple*), **Vassil Vassilev** (*Princeton University/CERN*)

Founding: **Google Summer of Code 2022**

Suhno developed a <a href="https://llvm.org/docs/JITLink.html#jit-linking">JITLink</a> 
specialization that extends JITLink’s generic linker algorithm, allowing 
JITLink to support ELF/aarch64 target and provides full support of all advanced 
PE/COFF object file features. By supporting the ELF/aarch64 target, JITLink can 
now be used in Julia, while COFF/X86_64 enables Microsoft Visual C++ (MSCV) 
target in <a href="https://clang.llvm.org/docs/ClangRepl.html">Clang-Repl</a>. 
Here you can find Sunho’s GSoC 
<a href="https://compiler-research.org/assets/docs/Sunho_Kim_GSoC22_Report.pdf">final report</a>.

**Hurray!** This project has been accepted as a Tutorial at the 
<a href="https://llvm.swoogo.com/2022devmtg/speakers">2022 LLVM Developers’ Meeting</a>! 
The conference took place in San Jose, California, from 7th to 10th November 
2022. 
Here you can find the 
<a href="https://www.youtube.com/watch?v=UwHgCqQ2DDA&list=PL_R5A0lGi1ACZDCQw533fo2dBljmOqIYx&index=42">video</a> 
and the <a href="https://llvm.org/devmtg/2022-11/slides/Tutorial2-JITLink.pdf">slides</a> 
of Sunho’s presentation. 

The project was also presented at the Compiler As a Service (CaaS) monthly 
meeting. Here you can find the <a href="https://www.youtube.com/watch?v=_5_gm58sQIg">video</a> 
and the <a href="https://compiler-research.org/assets/presentations/S_Kim-Jitlink_Coff.pdf">slides</a> 
of Sunho’s presentation. 

<a href="https://compiler-research.org/blogs/gsoc22_izvekov_experience_blog/">Extend Clang to resugar template specialization accesses</a>
------------------------------------------------------------------------------------------------------------------------------------------
Developer: **<a href="https://github.com/mizvekov">Matheus Izvekov</a>**

Mentors: **Richard Smith** (*Google*), **Vassil Vassilev** (*Princeton 
University/CERN*)

Funding: **Google Summer of Code 2022**

<a href="https://clang.llvm.org/">Clang</a>’s type system was optimized by 
pushing type-syntactic-sugar on the arguments of a template specialization into 
those member accesses. This was achieved by: 1. creating a new type node into 
the Abstract Syntax Tree (AST) that represents the sugar of a member access in 
a template specialization; and 2. implementing single step desugaring logic 
which will perform the substitution of template parameter sugar into the 
corresponding specialization argument sugar. As a result, we improved Clang’s 
diagnostic system by enabling other constructs to preserve type sugar, allowing 
both for their representation when present in the specialization argument.

**Hurray!** This project has been accepted as a Lightning Talk at the 
<a href="https://llvm.swoogo.com/2022devmtg/speakers">2022 LLVM Developers’ Meeting</a>! 
The conference took place in San Jose, California, from 7th to 10th November 
2022.
Here you can find the <a href="https://www.youtube.com/watch?v=bZ2HPrSkTZI">video</a> 
and the 
<a href="https://llvm.org/devmtg/2022-11/slides/Lightning9-TypeResugaringInClang%20.pdf">slides</a>
 of Matheus’s presentation. 


<a href="https://compiler-research.org/blogs/gsoc22_zhang_chaudhari_experience_blog/">Recovering from Errors in Clang-Repl and Code Undo</a>
--------------------------------------------------------------------------------------------------------------------------------------------
Developers: **<a href="https://github.com/junaire">Jun Zhang</a>** 
(*Software Engineering, Anhui Normal University, WuHu, China*) and 
**<a href="https://github.com/Purva-Chaudhari">Purva Chaudhari</a>** 
(*California State University Northridge, Northridge CA, USA*)

Mentors: **Vassil Vassilev** (*Princeton University/CERN*)

<a href="https://clang.llvm.org/docs/ClangRepl.html">Clang-Repl</a> is an 
interactive C++ interpreter integrated in Clang, which enables incremental 
compilation. It supports interactive programming for C++ in a 
Read-Eval_Print Loop 
(<a href="https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop">REPL</a>) 
style, compiling the code just-in-time with a JIT approach that reduces the 
compile-run cycles. We added the “undo” functionality to Clang-REPL, and we 
improved error-recovery by adding the possibility to recover the low-level 
execution infrastructure. As a result, Clang-REPL now supports reversal 
execution and recovery actions on behalf of a user in an automatic and 
convenient way.

**Hurray!** This project has been accepted as a Lightning Talk at the
 <a href="https://llvm.swoogo.com/2022devmtg/speakers">2022 LLVM Developers’ Meeting</a>! 
 The conference took place in San Jose, California, from 7th to 10th November
  2022.
Here you can find the <a href="https://www.youtube.com/watch?v=LSPBPC2av54">video</a> 
and the 
<a href="https://llvm.org/devmtg/2022-11/slides/Lightning6-RecoveringFromErrorsInClang-ReplAndCodeUndo.pdf">slides</a>
 of Purva and Jun’s presentation. 

<a href="https://compiler-research.org/blogs/gsoc22_ghosh_experience_blog/">Shared Memory Based JITLink Memory Manager</a>
--------------------------------------------------------------------------------------------------------------------------

Developer: **<a href="https://github.com/argentite">Anubhab Ghosh</a>** 
(*Computer Science and Engineering, Indian Institute of Information Technology, Kalyani, India*)

Mentors: **Stefan Gränitz** (*Freelance Compiler Developer, Berlin, Deutschland*), 
**Lang Hames** (*Apple*), **Vassil Vassilev** (*Princeton University/CERN*)

Funding: **Google Summer of Code 2022**

Anubhab introduced a new <a href="https://llvm.org/docs/JITLink.html">JITLinkMemoryManager</a> 
based on a MemoryMapper abstraction that is capable of allocating JIT code 
(and data) using shared memory. The following advantages should arise from the 
implemented strategy: 1. a faster transport (and access) for code and data when 
running JIT’d code in a separate process on the same machine, and 2. the 
guarantee that all allocations are close together in memory and meet the 
constraints of the default code model allowing the use of outputs from regular 
compilers.
Here you can find Anubhab’s GSoC 
<a href="https://compiler-research.org/assets/docs/Anubhab_Ghosh_GSoC2022_Report.pdf">final report</a>.

**Hurray!** This project has been accepted as a Lightning Talk at the 
<a href="https://llvm.swoogo.com/2022devmtg/speakers">2022 LLVM Developers’ Meeting</a>! 
The conference took place in San Jose, California, from 7th to 10th November 
2022. 
Here you can find the <a href="https://www.youtube.com/watch?v=dosXtBAFWiE">video</a> 
and the 
<a href="https://llvm.org/devmtg/2022-11/slides/Lightning4-EfficientJIT-basedRemoteExecution.pdf">slides</a>
 of Anubhab’s presentation. 


<a href="https://hepsoftwarefoundation.org/gsoc/blogs/2022/blog_ROOT_JunZhang.html">Optimize ROOT use of modules for large codebases</a>
-----------------------------------------------------------------------------------------------------------------------------------------
Developer: **<a href="https://github.com/junaire">Jun Zhang</a>**
(*Software Engineering, Anhui Normal University, WuHu, China*)

Mentors: **David Lange** (*Princeton University*), **Alexander Penev** 
(*University of Plovdiv Paisii Hilendarski, Bulgaria*), **Vassil Vassilev** 
(*Princeton University/CERN*)

Funding: **Google Summer of Code 2022**

The current performance of the modules usage in <a href="https://root.cern/">ROOT</a> 
was evaluated, and a strategy for optimizing the memory footprint was developed. 
This strategy includes reducing unnecessary symbol-lookups and module-loading, 
and is especially useful for very large codebases like <a href="https://cms-sw.github.io/">CMSSW</a>, 
where Jun reduced the amount of memory by half (from 1.1GB to 600MB) for simple 
workflows like hsimple.C, and the number of loaded from 180 to 52. 
Here you can find Jun’s GSoC 
<a href="https://compiler-research.org/assets/docs/Jun_Zhang_GSoC22_Report.pdf">final report</a>.



<a href="https://hepsoftwarefoundation.org/gsoc/blogs/2022/blog_CompilerResearch-ManishKausik.html">Add Initial Integration of Clad with Enzyme</a>
---------------------------------------------------------------------------------------------------------------------------------------------------
Developer: **<a href="https://github.com/Nirhar">Manish Kausik H</a>** 
(*.Tech and M.Tech in Computer Science and Engineering(Dual Degree), 
Indian Institute of Technology Bhubaneswar*)

Mentors: **David Lange** (*Princeton University*), **William Moses** 
(*Massachusetts Institute of Technology*), **Vassil Vasilev** (*Princeton University/CERN*)

Funding: **Google Summer of Code 2022**

<a href="https://clad.readthedocs.io/en/latest/index.html">Clad</a> is an open 
source plugin to the Clang compiler that enables <a href="https://en.wikipedia.org/wiki/Automatic_differentiation">Automatic Differentiation</a> 
for C++. Clad receives an Abstract Syntax Tree (AST) from the underlying  
compiler platform (Clang), decides whether a derivative is requested and 
produces it, and modifies the AST to insert the generated code.
<a href="https://enzyme.mit.edu/">Enzyme AD</a> is an LLVM based AD plugin. 
It works by taking existing code as LLVM IR and computing the derivative 
(and gradient) of that function. 
In this project, Manish integrated Enzyme within Clad, giving a Clad user the 
option of selecting Enzyme for Automatic Differentiation on demand. The 
integration of Clad and Enzyme t results in a new tool that offers an optimized 
and flexible implementation of automatic differentiation. 
Here you can find Manish’s GSoC 
<a href="https://compiler-research.org/assets/docs/Manish_Kausik_H_GSoC22_Report.pdf">final report</a>.

Thank you, developers!
----------------------

We hope our interns contributors enjoyed our community. Our best reward is to 
know that we  supported your early steps into the world of open-source software 
development and compiler construction. We hope that this experience motivated 
you to continue to be involved with the broad LLVM ecosystem.
We express our gratitude to the <a href="https://summerofcode.withgoogle.com/">Google Summer of Code</a> 
Program and to the Institute for Research and Innovation in Software for High 
Energy Physics (<a href="https://iris-hep.org/">IRIS-HEP</a>) for supporting our 
research and providing six young developers this wonderful opportunity.
A special thanks goes to the LLVM community for being supportive and for sharing 
their knowledge and introducing our community to the new contributors. Thank you 
so much!
Thanks for choosing Compiler-Research for your internship! We were lucky to 
have you!


