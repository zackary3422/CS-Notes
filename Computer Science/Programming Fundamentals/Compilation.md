Compiling is the process of converting source code(High-Level Language) into machine code(Binary).


### 1. **Preprocessing:**
   - **Objective:**
     - Prepare the source code for compilation by handling directives and including header files.
     -  Basically some parts of code are analyzed before anything else

   - **Steps:**
     1. **File Inclusion:**
        - Process `#include` directives, incorporating contents of header files into the source code.
     2. **Macro Expansion:**
        - Replace macros with their respective definitions.
     3. **Conditional Compilation:**
        - Evaluate `#if`, `#ifdef`, and `#ifndef` directives to include or exclude portions of code based on conditions.
     4. **Comments Removal:**
        - Remove comments from the code.

   - **Tool:**
     - Preprocessor (`cpp`): Often runs as a separate step before the actual compilation.

### 2. **Compiling:**
   - **Objective:**
     - Translate the preprocessed source code into assembly code specific to the target architecture.

   - **Steps:**
     1. **Lexical Analysis:**
        - Break the code into tokens (individual units like keywords, identifiers, and operators).
     2. **Syntax Analysis (Parsing):**
        - Analyze the syntax and structure of the code, generating a parse tree or abstract syntax tree.
     3. **Semantic Analysis:**
        - Check for semantic errors, enforce language rules, and generate an intermediate code.
     4. **Intermediate Code Generation:**
        - Translate the code into an intermediate representation, which is a platform-independent form.
     5. **Code Optimization:**
        - Apply optimizations to improve the efficiency of the intermediate code.

   - **Tool:**
     - Compiler proper: Takes preprocessed code and produces assembly code.

### 3. **Assembling:**
   - **Objective:**
     - Convert the assembly code into machine code (object code) for a specific computer architecture.

   - **Steps:**
     1. **Assembly:**
        - Translate assembly code mnemonics into binary machine code.
     2. **Object File Generation:**
        - Produce an object file containing machine code and information about symbols.

   - **Tool:**
     - Assembler (`as`): Converts assembly code to object code.

### 4. **Linking:**
   - **Objective:**
     - Combine multiple object files and libraries into a single executable file. 
     - Basically takes your linked libraries and add their code(binary) into your executable file.

   - **Steps:**
     1. **Symbol Resolution:**
        - Resolve symbolic references between different object files.
     2. **Address Binding:**
        - Assign final memory addresses to variables and functions.
     3. **Relocation:**
        - Adjust addresses in the code to reflect the final memory layout.
     4. **Library Linking:**
        - Incorporate external libraries into the executable.

   - **Tool:**
     - Linker (`ld`): Combines object files into an executable.

### Additional Considerations:
- **Optimizations:**
  - Optimizations may occur at various stages, including during the preprocessing, compiling, and linking phases.
- **Debug Information:**
  - Debug information is often generated to aid debugging tools.
- **Executable Output:**
  - The final output is an executable file that can be run on the target platform.
