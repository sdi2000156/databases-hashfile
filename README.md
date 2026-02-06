# Databases Hash File

Implementation of a hash file structure for database-style storage.
The project focuses on file-based hashing, record insertion,
lookup, and basic storage management.

# My Contribution
- Implemented the hash file structure
- Handled file I/O and record placement
- Focused on correctness and efficiency

# Notes / Design Decisions

- The hash table is created in memory during the 'create' operation, then stored on disk and       freed.
  Every time the file is opened, the hash table is reloaded from disk.When the file is closed,     it is stored again by overwriting the existing blocks and allocating new blocks if required.
  A second file is NOT used; all data is stored within the same file.
- We assume that the same file is not opened concurrently more than once.
  This assumption follows the constraints discussed during the course lectures (eClass).
- For convenience during the build process, C++ is used (mainly for 'std::string' support).
  However, the actual implementation of the interface is essentially written in C.
- The codebase contains extensive inline comments explaining design choices and implementation     details.

# Execution:
- Run the program with: 'make run'
- Memory checking with Valgrind: 'make debug'
