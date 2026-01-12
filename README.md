# Libft

Short Description
-----------------

`libft` is a small C library implementing commonly used functions from the C standard library and a set of utility functions. It is intended as a reusable static library for low-level projects and as an exercise in implementing standard behaviors with consistent error handling and style.

Key Features
------------

- Implementations of common C functions (strings, memory, character checking, conversions).
- List utilities and linked-list helpers matching common 42-school requirements.
- Portable POSIX C, buildable with `make` and usable as a static library (`libft.a`).
- Clean header (`include/libft.h`) exposing a simple API for consumers.

Tech Stack
----------You are a senior software engineer and technical writer.

Create a professional, clean, and recruiter-friendly README.md for the following project.

Target audience:
- Technical recruiters
- Hiring managers
- Software engineers

Tone & style:
- Clear, concise, and professional
- No emojis
- No marketing fluff
- Focus on technical clarity and value

README structure (use this order):

1. Project Title
2. Short Description (2–3 lines explaining what the project does and why it exists)
3. Key Features (bullet points, action-oriented)
4. Tech Stack (grouped by category: Frontend, Backend, Database, DevOps, etc.)
5. Architecture & Design (brief explanation if applicable)
6. Getting Started
   - Prerequisites
   - Installation
   - Running the project
7. Usage (how to interact with the app or API)
8. What I Learned / Technical Challenges
9. Future Improvements
10. Author & Contact

Additional rules:
- Use Markdown formatting
- Include code blocks where appropriate
- Assume the reader has basic technical knowledge
- If information is missing, make reasonable technical assumptions and clearly state them
- Keep the README concise but complete

Project details:
[PASTE PROJECT DESCRIPTION, GOALS, AND TECHNOLOGIES HERE]

- Language: C (C89/C99 compatible where appropriate)
- Build: `Makefile` (GCC toolchain)
- Platform: Unix-like (Linux, macOS)

Architecture & Design
---------------------

The project builds a static archive `libft.a` from object files compiled from `src/`. Public API declarations are in `include/libft.h`. Consumers include the header and link against the produced archive. The implementation favors small, well-tested units: one source file per function.

Getting Started
---------------

Prerequisites

- `gcc` (or another C compiler compatible with the used flags)
- `make`
- Standard Unix shell environment

Installation

1. Clone the repository.
2. Run `make` in the project root to build the library.

Build commands

```sh
make         # builds libft.a
make clean   # removes object files
make fclean  # removes object files and libft.a
make re      # fclean && make
```

Running the project

The library itself does not produce a runnable program. To use it, link against `libft.a` from your project.

Usage
-----

Example: compile and link an example program that uses `libft`.

Create `example.c`:

```c
#include "libft.h"
#include <stdio.h>

int main(void)
{
    const char *s = "hello";
    printf("len=%zu\n", ft_strlen(s));
    return 0;
}
```

Build and link:

```sh
make
gcc -Wall -Wextra -Werror -I include -L. example.c -lft -o example
./example
```

Notes:
- `-I include` tells the compiler where to find `libft.h`.
- `-L.` and `-lft` link the static library `libft.a` in the project root.

What I Learned / Technical Challenges
------------------------------------

- Re-implementing edge cases of standard functions (e.g., `ft_strlcpy`, `ft_memmove`) reinforced careful pointer and boundary handling.
- Managing memory ownership and error cases for `ft_split` and `ft_itoa` required careful allocation and cleanup strategies.
- Designing a minimal public API while keeping internal helpers simple and testable.

Future Improvements
-------------------

- Add a test suite (e.g., unit tests using a small test harness or Criterion) and CI integration.
- Extend documentation with function-level usage and complexity notes.
- Provide optional POSIX extensions and more utility functions (with feature flags).

Author & Contact
-----------------

Author: schamizo

Contact: salvadorchamizo@gmail.com

