# eBPF & Linux Kernel Development Portfolio

A comprehensive learning project building production-grade eBPF and XDP programs to master Linux kernel development, kernel networking, and systems programming. This portfolio demonstrates expertise in kernel instrumentation, packet processing, network protocols (OSI/TCP-IP), and systems observability—designed to showcase readiness for senior Linux Kernel Developer roles.

## 🎯 Project Goals

1. **Master Linux Kernel Development**: Deep understanding of kernel architecture, memory models, synchronization primitives, and subsystems
2. **Expert Networking Knowledge**: OSI model, TCP/IP stack, packet processing, network protocols at kernel level
3. **eBPF Mastery**: From basic socket filters to advanced tracing, load balancing, and traffic control
4. **Production-Grade Portfolio**: Build tools demonstrating real-world kernel development and optimization skills
5. **Career Goal**: Land a remote Linux Kernel Developer role with strong salary through demonstrable expertise

## 📋 Learning Path

### Phase 1: Foundation & Setup (Weeks 1–2)
**Objectives**: Set up development environment, document learning path, understand kernel and networking basics

- [ ] Document Linux kernel architecture (process, memory, scheduling, syscall interface)
- [ ] Document OSI model layers with kernel implementation details
- [ ] Document TCP/IP stack (protocols, state machines, kernel data structures)
- [ ] Set up development environment (kernel headers, LLVM/Clang, build tools)
- [ ] Create Makefile and build system for kernel and userspace programs
- [ ] Configure Git workflow and project structure

**Deliverables**:
- `/docs/kernel-architecture.md` - Kernel internals overview
- `/docs/osi-model.md` - OSI layers with kernel mapping
- `/docs/tcp-ip-stack.md` - TCP/IP stack architecture
- Functional build system with `make kernel` and `make userspace` targets

---

### Phase 2: Networking Fundamentals & Basic eBPF (Weeks 3–4)
**Objectives**: Learn eBPF basics, XDP fundamentals, implement simple packet processing

**Project 1: Packet Counter (XDP)**
- Simple XDP program counting packets per source IP
- Kernel: packet counting using BPF map
- Userspace (Go): Load eBPF program, read map data, display statistics
- Learning: XDP basics, BPF maps, ringbuffers, kernel-userspace communication

**Project 2: Packet Filter (XDP)**
- XDP program filtering packets by IP/port (whitelist/blacklist)
- Kernel: packet inspection, return codes (XDP_PASS, XDP_DROP)
- Userspace (Go): Configuration interface, rule management
- Learning: Protocol headers, packet inspection, performance implications

**Deliverables**:
- `/kernel/xdp_packet_counter.c` - Basic XDP program
- `/kernel/xdp_packet_filter.c` - Filtering logic
- `/userspace/cmd/packet-counter/` - Go loader and stats tool
- `/userspace/cmd/packet-filter/` - Go filtering CLI
- `/docs/phase2-learning.md` - XDP concepts, BPF maps, design decisions

---

### Phase 3: Advanced XDP & Packet Processing (Weeks 5–7)
**Objectives**: Advanced packet manipulation, performance optimization, complex data structures

**Project 3: XDP Load Balancer**
- Round-robin and consistent hash-based load balancing
- Kernel: packet rewriting (destination IP/MAC), connection tracking
- Userspace (Go): Backend management, statistics, performance monitoring
- Learning: Packet header rewriting, state tracking, performance optimization, kernel memory models

**Project 4: Network Flow Tracker**
- Track TCP connections at kernel level with XDP
- Kernel: Connection state tracking, flow state machine
- Userspace (Go): Flow visualization, statistics, persistence
- Learning: TCP handshake, connection states, kernel data structures, flow analysis

**Deliverables**:
- `/kernel/xdp_load_balancer.c` - LB with header rewriting
- `/kernel/xdp_flow_tracker.c` - Connection tracking
- `/userspace/cmd/load-balancer/` - Load balancer CLI
- `/userspace/pkg/maps/` - Shared BPF map utilities
- `/docs/phase3-learning.md` - Advanced XDP, optimization techniques
- Benchmarks and performance analysis reports

---

### Phase 4: Tracing & System Observability (Weeks 8–10)
**Objectives**: Kernel tracing, syscall instrumentation, system-wide observability

**Project 5: Network Syscall Tracer**
- Trace all network-related syscalls (socket, connect, send, recv, etc.)
- Kernel: kprobes on syscall entry/exit points
- Userspace (Go): Syscall filtering, data aggregation, statistics
- Learning: kprobes/kretprobes, syscall interface, kernel hooks, tracing infrastructure

**Project 6: TCP Connection Analyzer**
- Comprehensive TCP connection tracking and analysis
- Kernel: tracepoints on TCP state transitions
- Userspace (Go): Connection state visualization, latency analysis, anomaly detection
- Learning: TCP state machine, kernel tracepoints, perf events, flame graphs

**Deliverables**:
- `/kernel/kprobe_network_syscalls.c` - Syscall instrumentation
- `/kernel/tracepoint_tcp_analyzer.c` - TCP tracing
- `/userspace/cmd/syscall-tracer/` - Syscall analysis tool
- `/userspace/cmd/tcp-analyzer/` - TCP analysis tool
- `/docs/phase4-learning.md` - Tracing concepts, kprobes, tracepoints
- Flame graph generation and analysis tools

---

### Phase 5: Advanced Kernel Concepts (Weeks 11–12)
**Objectives**: Advanced kernel subsystems, production features, optimization

**Project 7: Socket Filter Load Balancer**
- SO_REUSEPORT-based load balancing at socket level
- Kernel: BPF program for socket filtering
- Userspace (Go): Multi-process server with load distribution
- Learning: Socket layer programming, SO_REUSEPORT semantics, kernel scheduling

**Project 8: Traffic Control (TC) Tool**
- Rate limiting, queuing discipline, traffic shaping
- Kernel: TC eBPF programs (egress/ingress)
- Userspace (Go): QoS configuration and management
- Learning: Qdisc layer, traffic control, scheduling algorithms, QoS

**Deliverables**:
- `/kernel/so_reuseport_lb.c` - Socket filter load balancer
- `/kernel/tc_traffic_shaper.c` - Traffic control
- `/userspace/cmd/socket-lb/` - Socket-level LB
- `/userspace/cmd/traffic-control/` - TC management
- `/docs/phase5-learning.md` - Advanced kernel subsystems

---

### Phase 6: Integration & Portfolio Polish (Weeks 13–14)
**Objectives**: Create cohesive portfolio, documentation, CI/CD, and interview preparation

**Consolidation**:
- [ ] Unified Go CLI tool integrating all projects
- [ ] Comprehensive README with architecture diagrams
- [ ] Decision rationale documentation for each project
- [ ] Performance benchmarks and comparisons
- [ ] Setup and troubleshooting guides

**Documentation**:
- [ ] Blog-style technical posts (6-8 posts covering key concepts)
- [ ] Architecture decision records (ADRs)
- [ ] Lessons learned and trade-offs
- [ ] Interview talking points

**Quality Assurance**:
- [ ] Unit tests for all Go code
- [ ] Integration tests with packet generation
- [ ] Performance benchmarks
- [ ] Memory safety and correctness validation

**Career Preparation**:
- [ ] Polished GitHub repository with excellent documentation
- [ ] Portfolio summary highlighting kernel expertise
- [ ] Technical blog posts demonstrating deep knowledge
- [ ] Performance optimization case studies

**Deliverables**:
- Unified CLI: `ebpf-study [command] [subcommand] [options]`
- `/docs/architecture.md` - System design overview
- `/docs/decisions.md` - Key design decisions
- `/docs/lessons-learned.md` - Knowledge gained
- CI/CD pipeline (GitHub Actions)
- Blog posts in `/docs/blog/`

---

## 📁 Repository Structure

```
ebpf_study/
├── README.md                          # This file
├── Makefile                           # Build orchestration
├── go.mod, go.sum                     # Go module files
├── .github/
│   └── workflows/
│       └── ci.yml                     # GitHub Actions CI/CD
├── docs/
│   ├── kernel-architecture.md         # Kernel fundamentals
│   ├── osi-model.md                   # OSI model with kernel details
│   ├── tcp-ip-stack.md               # TCP/IP stack architecture
│   ├── phase2-learning.md            # Phase 2 concepts & decisions
│   ├── phase3-learning.md            # Phase 3 optimization & design
│   ├── phase4-learning.md            # Phase 4 tracing concepts
│   ├── phase5-learning.md            # Phase 5 advanced subsystems
│   ├── architecture.md               # Overall system architecture
│   ├── decisions.md                  # Design decision records
│   ├── lessons-learned.md            # Key learnings
│   └── blog/                          # Technical blog posts
├── kernel/                            # eBPF kernel programs (C)
│   ├── xdp_packet_counter.c
│   ├── xdp_packet_filter.c
│   ├── xdp_load_balancer.c
│   ├── xdp_flow_tracker.c
│   ├── kprobe_network_syscalls.c
│   ├── tracepoint_tcp_analyzer.c
│   ├── so_reuseport_lb.c
│   ├── tc_traffic_shaper.c
│   └── Makefile                       # Kernel program build rules
├── userspace/                         # Go userspace tools
│   ├── cmd/                           # CLI commands
│   │   ├── packet-counter/
│   │   ├── packet-filter/
│   │   ├── load-balancer/
│   │   ├── flow-tracker/
│   │   ├── syscall-tracer/
│   │   ├── tcp-analyzer/
│   │   ├── socket-lb/
│   │   └── traffic-control/
│   ├── pkg/                           # Shared libraries
│   │   ├── ebpf/                      # BPF program loading
│   │   ├── maps/                      # BPF map utilities
│   │   ├── parser/                    # Packet/data parsing
│   │   ├── stats/                     # Statistics & aggregation
│   │   └── cli/                       # CLI utilities
│   └── main.go                        # Unified CLI entry point
├── examples/                          # Example programs & tutorials
│   ├── basic-xdp/
│   ├── packet-processing/
│   └── tracing/
├── test/                              # Tests & benchmarks
│   ├── integration/
│   ├── benchmarks/
│   └── fixtures/
└── scripts/                           # Setup & utility scripts
    ├── setup-dev.sh                   # Dev environment setup
    ├── check-kernel.sh                # Kernel capability check
    └── test.sh                        # Test runner
```

---

## 🛠️ Prerequisites & Setup

### System Requirements
- **Linux Kernel**: 5.10+ (check: `uname -r`)
- **Kernel Config**: BPF enabled (`CONFIG_BPF=y`, `CONFIG_BPF_SYSCALL=y`, etc.)
- **Build Tools**: LLVM/Clang 10+, GCC, Make
- **Go**: 1.19+ (https://golang.org/doc/install)
- **Kernel Headers**: `linux-headers-*` package for your kernel

### Initial Setup

```bash
# Clone and enter repository
cd /home/cuongbtq/ebpf_study

# Run setup script (installs dependencies)
bash scripts/setup-dev.sh

# Verify kernel support
bash scripts/check-kernel.sh

# Build everything
make clean
make all
```

### Verify Setup
```bash
# Check kernel BPF support
cat /boot/config-$(uname -r) | grep BPF

# Check LLVM/Clang
clang --version

# Check Go
go version
```

---

## 🚀 Getting Started

### Build Kernel Programs
```bash
make kernel          # Build all kernel eBPF programs
make kernel-clean    # Clean kernel builds
```

### Build Userspace Tools
```bash
make userspace       # Build all Go tools
make userspace-clean # Clean userspace builds
```

### Run Tests
```bash
make test            # Run all tests
make benchmark       # Run performance benchmarks
```

### Example: Run Packet Counter
```bash
# Build
make all

# Load and run the packet counter
sudo ./bin/packet-counter --interface eth0

# In another terminal, generate traffic
ping google.com

# See packet statistics updating in real-time
```

---

## 📚 Learning Objectives

### By End of Phase 1
- [ ] Understand Linux kernel architecture and subsystems
- [ ] Know OSI model with kernel-level implementation
- [ ] Understand TCP/IP stack design
- [ ] Successfully build and load eBPF programs

### By End of Phase 2
- [ ] Master XDP basics and packet processing
- [ ] Understand BPF maps and kernel-userspace communication
- [ ] Implement basic packet filtering and counting
- [ ] Write efficient kernel code with memory constraints

### By End of Phase 3
- [ ] Advanced packet manipulation and rewriting
- [ ] Performance optimization techniques
- [ ] Complex BPF data structures and algorithms
- [ ] Load balancing and connection tracking

### By End of Phase 4
- [ ] Deep understanding of Linux tracing infrastructure
- [ ] kprobe/kretprobe and tracepoint usage
- [ ] Syscall instrumentation and analysis
- [ ] System-wide observability and profiling

### By End of Phase 5
- [ ] Socket-level programming and SO_REUSEPORT
- [ ] Traffic control and QoS implementation
- [ ] Kernel synchronization and locking
- [ ] Production-grade feature implementation

### By End of Phase 6
- [ ] Full-stack kernel development expertise
- [ ] Production-quality documentation and code
- [ ] Strong portfolio demonstrating kernel mastery
- [ ] Interview-ready explanations of complex kernel concepts

---

## 🎓 Key Topics Covered

### Kernel Architecture
- Process and memory management
- System call interface
- Interrupt and exception handling
- Kernel subsystems and module loading

### Networking (OSI/TCP-IP)
- **Layer 1-2**: Ethernet, MAC addressing
- **Layer 3**: IPv4/IPv6, routing, ICMP
- **Layer 4**: TCP/UDP, port multiplexing, connection state
- **Layer 5-7**: Application protocols, socket interface
- **Kernel Implementation**: sk_buff, network stack traversal

### eBPF Technology
- BPF maps (hash, array, ringbuffer, etc.)
- XDP programs (packet processing before network stack)
- kprobes/kretprobes (dynamic tracing)
- Tracepoints (static instrumentation)
- TC programs (traffic control)
- Socket filters

### Systems Programming (Go)
- ebpf-go library usage
- Safe BPF program loading and verification
- Kernel-userspace data passing
- Performance monitoring and optimization
- Error handling and debugging

---

## 🔗 Resources

### Official Documentation
- [kernel.org - Linux Kernel Documentation](https://www.kernel.org/doc/)
- [eBPF.io - eBPF Documentation](https://ebpf.io/)
- [Cilium ebpf-go - GitHub](https://github.com/cilium/ebpf)
- [Linux TCP/IP Stack - Kernel Docs](https://www.kernel.org/doc/html/latest/networking/)

### Learning Materials
- "Linux Kernel Development" by Robert Love
- "TCP/IP Illustrated" by W. Richard Stevens
- "BPF Performance Tools" by Brendan Gregg
- Brendan Gregg's blog: http://www.brendangregg.com/
- LPC Conference talks: https://www.youtube.com/user/LinuxPlumbersConf

### Community
- eBPF Mailing List
- Cilium Community Slack
- Linux Kernel Mailing Lists (LKML)

---

## 🤝 Contributing

This is a learning project. Feel free to:
- [ ] Add more example programs
- [ ] Improve documentation
- [ ] Optimize implementations
- [ ] Add tests and benchmarks
- [ ] Create blog posts explaining concepts

---

## 📝 License

Educational project - MIT License

---

## 🎯 Career Goals

This portfolio is specifically designed to demonstrate:
1. **Deep kernel expertise** through multiple production-grade tools
2. **Networking mastery** from protocol design to kernel implementation
3. **Systems optimization** with performance-focused implementations
4. **Production readiness** with comprehensive documentation and testing
5. **Communication skills** through blog posts and clear code documentation

Target positions: Senior Linux Kernel Developer, Systems Engineer, Networking Engineer, Site Reliability Engineer (SRE)

---

## 📌 Current Status

**Phase**: 1 (Foundation & Setup)
**Progress**: Starting
**Last Updated**: January 7, 2026

Track progress by checking off learning objectives and deliverables in each phase section above.