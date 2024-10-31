# eBPF-Learnings
eBPF playground

# Dev/Test Enviroinment
VERSION: Ubuntu 22.04
KERNEL: 5.15.0-112-generic

# Build libbpf and install header files
cd libbpf/src;
make install;
cd ../..

# Build bpftool
cd ..;
git clone --recurse-submodules https://github.com/libbpf/bpftool.git;
cd bpftool/src;
make install 