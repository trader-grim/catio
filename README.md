
# Catio — Local-First, Bounded Linux Runtimes for AI Agents

<p align="center">
  <img width="1024" height="506" alt="catio_github_watermarked_img_8966606370108936522" src="https://github.com/user-attachments/assets/5318af2a-5b8d-43b9-ad35-221f02da5d09"  alt="Catio OS - Fenced Linux AI Runtimes" width="100%"/>
</p>

> **Reasoning Proposes. Determinism Commits.**  
> Catio is an open-source architecture and local-first Linux runtime designed to eliminate ambient authority hazards in autonomous AI agents.

---

## 📌 The Problem: Ambient Authority in Agent Workflows

Granting autonomous AI agents unconstrained shell access, broad file system privileges, or arbitrary tool-calling capability exposes host systems to severe operational hazards:
* **Unbounded System Access:** Discretionary scope expansion and privilege escalation.
* **Context Poisoning:** Uncurated retrieval memory leading to hallucinated or adversarial tool calls.
* **State Corruption:** Non-atomic system modifications leaving host configurations broken.

---

## 🛡️ Core Architectural Thesis

**Deterministic workflows provide the only practical, OS-wide solution for safe AI integration today.** 

Rather than relying on non-deterministic LLMs to enforce their own safety boundaries, Catio decouples reasoning from execution:
1. **LLMs Act as Proposers:** Models generate structured task DAGs inside isolated environments.
2. **PREMIS(X) Enforces Capabilities:** Signed contract ceilings evaluate permissions via $\text{Effective Permission} = \min(\text{Role}, \text{Requester})$.
3. **Kernel Gates Enforce Execution:** eBPF LSM hooks drop unauthorized syscalls (`EPERM`) at hardware speeds before state changes occur.

---

## 🚦 Project Status & Development Roadmap

We are rolling out Catio incrementally, using our own commercial workloads as an active "eat-your-own-catfood" testbed.

| Component | Domain / Role | Status |
| :--- | :--- | :--- |
| **PREMIS(X)** | Contract-based capability permission engine | **PoC / Active Stub** |
| **Ratter** | Isolated container build & runtime harness | **PoC / Active** |
| **The Librarian (Dewey)** | Scoped Recoll search indexes ("The Stacks") | **PoC / Active** |
| **The Claw** | eBPF LSM kernel syscall enforcement gates | **Specification / Benchmarking** |
| **Meowster** | Schema-first backward-chaining DAG planner | **In Progress** |

---

## 🤝 Getting Involved & Support

Catio is an independent open-source digital infrastructure initiative. To maintain our development momentum while operating under strict budget constraints, we actively welcome support across several avenues:

* **Hardware & Build Node Donations:** Dedicated mini PCs, bare-metal server instances, or low-spec x86/ARM hardware (e.g., Raspberry Pi 4/5, Intel NUCs, repurposed enterprise nodes) to expand our physical testing matrix and host continuous build nodes.
* **Developer & Infrastructure Grants:** Non-profit digital infrastructure funding (e.g., NLnet, Sovereign Tech Fund) and cloud hosting allocations to cover target VPS nodes and public benchmarks.
* **API Credit & Service Sponsorships:** Model access and API credit allocations to evaluate low-latency classification engines (e.g., TypeSafe Jev) against live kernel map updates.
* **Technical Collaborators:** Systems engineers interested in eBPF LSM, Go runtime safety, POSIX capability models, and deterministic agent containment.

For hardware shipping details, architectural briefs, technical specifications, or collaboration inquiries, please reach out via [GitHub Issues](../../issues) or contact the maintainers directly.
