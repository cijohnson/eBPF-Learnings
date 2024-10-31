# Build
make

# Dump byte code
llvm-objdump -S hello.bpf.o

# Load Program
bpftool prog load hello_xdp.bpf.o /sys/fs/bpf/hello

# List Programs
bpftool prog list

# Pretty Print the Program
bpftool prog show id <programID> --pretty

# Dump byte code
bpftool prog dump xlated name hello

# Dump Machine code

bpftool prog dump jited name hello

# Attach
bpftool net attach xdp id <programID> dev <netDevice>

# List attached network programs
bpftool net list

# Trace logs
cat /sys/kernel/debug/tracing/trace_pipe

# Trace logs using bpftool
bpftool prog tracelog

# List maps
bpftool map list

# view Map content
bpftool map dump name hello.bss

# Detach
bpftool net detach xdp dev eth0

# Unload
rm /sys/fs/bpf/hello; bpftool prog show name hello