# CS-Fundamentals lab: one image with the C++, Java and Python toolchains
# plus the low-level inspection tools used across the repository.
FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive \
    LANG=C.UTF-8 \
    LC_ALL=C.UTF-8

RUN apt-get update && apt-get install -y --no-install-recommends \
        # C / C++ — compiler, debugger, binary inspection, memory checking
        build-essential \
        g++ \
        gdb \
        valgrind \
        binutils \
        # Java — JDK 21 (javac, javap, java)
        openjdk-21-jdk-headless \
        # Python — CPython 3.12
        python3 \
        python3-venv \
        python-is-python3 \
        # System inspection — syscalls, library calls, processes, ASLR toggle
        strace \
        ltrace \
        procps \
        util-linux \
        hyperfine \
        file \
        # Quality of life
        git \
        less \
        ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# The base image ships a non-root "ubuntu" user (uid 1000); work as that user.
USER ubuntu
WORKDIR /workspace

CMD ["bash"]
