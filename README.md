ASU-Buffalo-SNU: Trilateral GPU Security Research
===
Paper collection for GPU Security

## Papar Information
- Title:  `Rendered Insecure: GPU Side Channel Attacks are Practical`
- Authors:  `Hoda Naghibijouybari ...`
- Conference/Journal: `CCS'18`
- Link: [https://dl.acm.org/doi/pdf/10.1145/3243734.3243831]()
- Abstract: Graphics Processing Units (GPUs) are commonly integrated with computing devices to enhance the performance and capabilities of graphical workloads. In addition, they are increasingly being integrated in data centers and clouds such that they can be used to accelerate data intensive workloads. Under a number of scenar- ios the GPU can be shared between multiple applications at a fine granularity allowing a spy application to monitor side channels and attempt to infer the behavior of the victim. For example, OpenGL and WebGL send workloads to the GPU at the granularity of a frame, allowing an attacker to interleave the use of the GPU to measure the side-effects of the victim computation through perfor- mance counters or other resource tracking APIs. We demonstrate the vulnerability using two applications. First, we show that an OpenGL based spy can fingerprint websites accurately, track user activities within the website, and even infer the keystroke timings for a password text box with high accuracy. The second application demonstrates how a CUDA spy application can derive the internal parameters of a neural network model being used by another CUDA application, illustrating these threats on the cloud. To counter these attacks, the paper suggests mitigations based on limiting the rate of the calls, or limiting the granularity of the returned information.

## Papar Information
- Title:  `LITE: A Low-Cost Practical Inter-Operable GPU TEE`
- Authors:  `Ardhi Wiratama Baskara Yudha ...`
- Conference/Journal: `ICS'22`
- Link: [https://dl.acm.org/doi/pdf/10.1145/3524059.3532361]()
- Abstract: There is a strong need for GPU trusted execution environ- ments (TEEs) as GPU is increasingly used in the cloud envi- ronment. However, current proposals either ignore memory security (i.e., not encrypting memory) or impose a separate memory encryption domain from the host TEE, causing a very substantial slowdown for communicating data from/to the host.
In this paper, we propose a flexible GPU memory encryp- tion design called LITE that relies on software memory en- cryption aided by small architecture support. LITE’s flexibil- ity allows GPU TEE to be co-designed with CPU to create a unified encryption domain. We show that GPU applications can be adapted to the use of LITE encryption APIs without major changes. Through various optimizations, we show that software memory encryption in LITE can produce negligible performance overheads (1.1%) for regular benchmarks and still-acceptable overheads (56%) for irregular benchmarks.

## Papar Information
- Title:  `GINN: Fast GPU-TEE Based Integrity for Neural Network Training`
- Authors:  `Aref Asvadishirehjini ...`
- Conference/Journal: `CODASPY'22`
- Link: [https://dl.acm.org/doi/pdf/10.1145/3508398.3511503]()
- Abstract: Machine learning models based on Deep Neural Networks (DNNs) are increasingly deployed in a wide variety of applications, ranging from self-driving cars to COVID-19 diagnosis. To support the computational power necessary to train a DNN, cloud environments with dedicated Graphical Processing Unit (GPU) hardware support have emerged as critical infrastructure. However, there are many integrity challenges associated with outsourcing the computation to use GPU power, due to its inherent lack of safeguards to ensure computational integrity. Various approaches have been developed to address these challenges, building on trusted execution environments (TEE). Yet, no existing approach scales up to support realistic integrity-preserving DNN model training for heavy workloads (e.g., deep architectures and millions of training examples) without sustaining a significant performance hit. To mitigate the running time difference between pure TEE (i.e., full integrity) and pure GPU (i.e., no integrity) , we combine random verification of selected computation steps with systematic adjustments of DNN hyperparameters (e.g., a narrow gradient clipping range), which limits the attacker's ability to shift the model parameters arbitrarily. Experimental analysis shows that the new approach can achieve a 2X to 20X performance improvement over a pure TEE-based solution while guaranteeing an extremely high probability of integrity (e.g., 0.999) with respect to state-of-the-art DNN backdoor attacks.


## Papar Information
- Title:  `StrongBox: A GPU TEE on Arm Endpoints`
- Authors:  `Yunjie Deng ...`
- Conference/Journal: `CCS'22`
- Link: [https://dl.acm.org/doi/pdf/10.1145/3548606.3560627]()
- Abstract: A wide range of Arm endpoints leverage integrated and discrete GPUs to accelerate computation such as image processing and numerical processing applications. However, in spite of these im- portant use cases, Arm GPU security has yet to be scrutinized by the community. By exploiting vulnerabilities in the kernel, attack- ers can directly access sensitive data used during GPU computing, such as personally-identifiable image data in computer vision tasks. Existing work has used Trusted Execution Environments (TEEs) to address GPU security concerns on Intel-based platforms, while there are numerous architectural differences that lead to novel technical challenges in deploying TEEs for Arm GPUs. In addition, extant Arm-based GPU defenses are intended for secure machine learning, and lack generality. There is a need for generalizable and efficient Arm-based GPU security mechanisms.
To address these problems, we present StrongBox, the first GPU TEE for secured general computation on Arm endpoints. During confidential computation on Arm GPUs, StrongBox provides an isolated execution environment by ensuring exclusive access to the GPU. Our approach is based in part on a dynamic, fine-grained memory protection policy as Arm-based GPUs typically share a unified memory with the CPU, a stark contrast with Intel-based platforms. Furthermore, by characterizing GPU buffers as secure and non-secure, StrongBox reduces redundant security introspec- tion operations to control access to sensitive data used by the GPU, ultimately reducing runtime overhead. Our design leverages the widely-deployed Arm TrustZone and generic Arm features, with- out hardware modification or architectural changes. We prototype StrongBox using an off-the-shelf Arm Mali GPU and perform an extensive evaluation. Our results show that StrongBox suc- cessfully ensures the GPU computing security with a low (4.70% - 15.26%) overhead across several indicative benchmarks.

## Papar Information
- Title:  `Honeycomb: Secure and Efficient GPU Executions via Static Validation`
- Authors:  `Haohui Mai ...`
- Conference/Journal: `USENIX Security'23`
- Link: [https://www.usenix.org/system/files/osdi23-mai.pdf]()
- Abstract: Graphics Processing Units (GPUs) unlock emerging use cases like large language models and autonomous driving. They process a large amount of sensitive data, where security is of critical importance. GPU Trusted Execution Environ- ments (TEEs) generally provide security to GPU applications with modest overheads. Recent proposals for GPU TEEs are promising, but many of them require hardware changes that have a long lead time to deploy in production environments.
This paper presents Honeycomb, a software-based, secure and efficient TEE for GPU applications. The key idea of Hon- eycomb is to leverage static analysis to validate the security of GPU applications at load time. Co-designing with the CPU TEE, as well as adding OS and driver support, Honeycomb is able to remove both the OS and the driver from the trusted computing base (TCB). Validation also ensures that all ap- plications inside the system are secure, enabling a concise and secure approach to exchange data in plaintext via shared device memory on the GPU.
We have prototyped Honeycomb targeting the AMD RX6900XT GPU. Honeycomb is evaluated on five repre- sentative benchmarks and 23 applications in total, covering workloads of high performance computing, deep learning, and image processing. The results show that Honeycomb is both practical and efficient to secure real-world GPU applica- tions. Validating applications to run on Honeycomb requires modest developer efforts. The TCB is 18× smaller than the Linux-based systems. Secure inter-process communication is up to 529× faster. Moreover, running large language model workloads like BERT and NanoGPT has ∼2% overheads.

## Papar Information
- Title:  `Spy in the GPU-box: Covert and Side Channel Attacks on Multi-GPU System`
- Authors:  `Sankha Baran Dutta ...`
- Conference/Journal: `ISCA'23`
- Link: [https://dl.acm.org/doi/pdf/10.1145/3579371.3589080]()
- Abstract: The deep learning revolution has been enabled in large part by GPUs, and more recently accelerators, which make it possible to carry out computationally demanding training and inference in ac- ceptable times. As the size of machine learning networks and work- loads continues to increase, multi-GPU machines have emerged as an important platform offered on High Performance Computing and cloud data centers. Since these machines are shared among multiple users, it becomes increasingly important to protect ap- plications against potential attacks. In this paper, we explore the vulnerability of Nvidia’s DGX multi-GPU machines to covert and side channel attacks. These machines consist of a number of discrete GPUs that are interconnected through a combination of custom interconnect (NVLink) and PCIe connections. We reverse engineer the interconnected cache hierarchy and show that it is possible for an attacker on one GPU to cause contention on the L2 cache of another GPU. We use this observation to first develop a covert channel attack across two GPUs, achieving the best bandwidth of around 4 MB/s. We also develop a prime and probe attack on a remote GPU allowing an attacker to recover the cache access pattern of another workload. This access pattern can be used in any number of side channel attacks: we demonstrate a proof of concept attack that fingerprints the application running on the remote GPU, with high accuracy. We also develop a proof of concept attack to extract hyperparameters of a machine learning workload. Our work establishes for the first time the vulnerability of these machines to microarchitectural attacks and can guide future research to improve their security.

## Papar Information
- Title:  `Side Channel Attacks in Computation Offloading Systems with GPU Virtualization`
- Authors:  `Sihang Liu ...`
- Conference/Journal: `SPW'19`
- Link: [https://www.cs.virginia.edu/~fs5ve/papers/conf/liu_SafeThings.pdf]()
- Abstract: Abstract—The Internet of Things (IoT) and mobile systems nowadays are required to perform more intensive computation, such as facial detection, image recognition and even remote gaming, etc. Due to the limited computation performance and power budget, it is sometimes impossible to perform these workloads locally. As high-performance GPUs become more common in the cloud, offloading the computation to the cloud becomes a possible choice. However, due to the fact that offloaded workloads from different devices (belonging to different users) are being computed in the same cloud, security concerns arise. Side channel attacks on GPU systems have been widely studied, where the threat model is the attacker and the victim are running on the same operating system. Recently, major GPU vendors have provided hardware and library support to virtualize GPUs for better isolation among users. This work studies the side channel attacks from one virtual machine to another where both share the same physical GPU. We show that it is possible to infer other user’s activities in this setup and can further steal others deep learning model.


## Papar Information
- Title:  `Simulee: Detecting CUDA Synchronization Bugs via Memory-Access Modeling`
- Authors:  `Mingyuan Wu ...`
- Conference/Journal: `ICSE'20`
- Link: [https://dl.acm.org/doi/pdf/10.1145/3377811.3380358]()
- Abstract: While CUDA has become a mainstream parallel computing plat- form and programming model for general-purpose GPU computing, how to effectively and efficiently detect CUDA synchronization bugs remains a challenging open problem. In this paper, we pro- pose the first lightweight CUDA synchronization bug detection framework, namely Simulee, to model CUDA program execution by interpreting the corresponding LLVM bytecode and collecting the memory-access information for automatically detecting gen- eral CUDA synchronization bugs. To evaluate the effectiveness and efficiency of Simulee, we construct a benchmark with 7 popular CUDA-related projects from GitHub, upon which we conduct an extensive set of experiments. The experimental results suggest that Simulee can detect 21 out of the 24 manually identified bugs in our preliminary study and also 24 previously unknown bugs among all projects, 10 of which have already been confirmed by the develop- ers. Furthermore, Simulee significantly outperforms state-of-the-art approaches for CUDA synchronization bug detection.


## Paper Information
- Title:  `GPUGuard: Mitigating Contention Based Side and Covert Channel Atacks on GPUs`
- Authors:  `Qiumin Xu ...`
- Conference/Journal: `ICS'19`
- Link: [https://dl.acm.org/doi/pdf/10.1145/3330345.3330389]()
- Abstract: Graphics processing units (GPUs) are moving towards support- ing concurrent kernel execution where multiple kernels may be co-executed on the same GPU and even on the same streaming multiprocessor (SM) core. While concurrent kernel execution im- proves hardware resource utilization, it opens up vulnerabilities to covert-channel and side-channel attacks. These attacks exploit information leakage across kernels that results from contention on shared resources; they have been shown to be a dangerous threat on CPUs, and are starting to be demonstrated on GPUs. The unique micro-architectural features of GPUs, such as specialized cache structures and massive parallel thread support, create opportunities for GPU-speciic channels to be formed. In this paper, we propose GPUGuard, a decision tree based detection and a hierarchical de- fense framework that can reliably close the covert channels. Our results show that GPUGuard can detect contention with 100% sen- sitivity and a small (8.5%) false positive rate. The timing channels are mitigated through Tangram, a GPU-speciic contention channel elimination scheme, with only 8% to 23% overhead when there is an attack and zero performance overhead when no attacks are detected. Compared to temporal partitioning, GPUGuard is 69%-96% faster in various architectures even when active, showing that it is possible to gain substantial performance from executing concurrent kernels on a single SM while securing GPUs against these attacks.

## Paper Information
- Title:  `Securing GPU via Region-based Bounds Checking`
- Authors:  `Jaewon Lee ...`
- Conference/Journal: `ISCA'22`
- Link: [https://dl.acm.org/doi/pdf/10.1145/3470496.3527420]()
- Abstract: Graphics processing units (GPUs) have become essential general- purpose computing platforms to accelerate a wide range of work- loads, such as deep learning, scientific, and high-performance com- puting (HPC) applications. However, recent memory corruption attacks, such as buffer overflow, exposed security vulnerabilities in GPUs. We demonstrate that out-of-bounds writes are reproducible on an Nvidia GPU, which can enable other security attacks.
We propose GPUShield, a hardware-software cooperative region- based bounds-checking mechanism, to improve GPU memory safety for global, local, and heap memory buffers. To achieve effective protection, we update the GPU driver to assign a random but unique ID to each buffer and local variable and store individual bounds information in the bounds table allocated in the global memory. The proposed hardware performs efficient bounds checking by indexing the bounds table with unique IDs. We further reduce the bounds-checking overhead by utilizing compile-time bounds analysis, workgroup/warp-level bounds checking, and GPU-specific address mode. Our performance evaluations show that GPUShield incurs little performance degradation across 88 CUDA benchmarks on the Nvidia GPU architecture and 17 OpenCL benchmarks on the Intel GPU architecture with a marginal hardware overhead.

## Paper Information
- Title:  `Piranha: A GPU Platform for Secure Computation`
- Authors:  `Jean-Luc Watson ...`
- Conference/Journal: `USENIX Secuiry'22`
- Link: [https://www.usenix.org/system/files/sec22-watson.pdf]()
- Abstract: Secure multi-party computation (MPC) is an essential tool for privacy-preserving machine learning (ML). However, secure training of large-scale ML models currently requires a pro- hibitively long time to complete. Given that large ML inference and training tasks in the plaintext setting are significantly accel- erated by Graphical Processing Units (GPUs), this raises the natural question: can secure MPC leverage GPU acceleration? A few recent works have studied this question in the context of accelerating specific components or protocols, but do not provide a general-purpose solution. Consequently, MPC devel- opers must be both experts in cryptographic protocol design and proficient at low-level GPU kernel development to achieve good performance on any new protocol implementation.
We present Piranha, a general-purpose, modular platform for accelerating secret sharing-based MPC protocols using GPUs. Piranha allows the MPC community to easily leverage the benefits of a GPU without requiring GPU expertise. Piranha contributes a three-layer architecture: (1) a device layer that can independently accelerate secret-sharing protocols by providing integer-based kernels absent in current general-purpose GPU libraries, (2) a modular protocol layer that allows developers to maximize utility of limited GPU memory with in-place computation and iterator-based support for non-standard memory access patterns, and (3) an application layer that allows applications to remain completely agnostic to the underlying protocols they use.
To demonstrate the benefits of Piranha, we implement 3 state-of-the-art linear secret sharing MPC protocols for secure NN training: 2-party SecureML (IEEE S&P ’17), 3-party Fal- con (PETS ’21), and 4-party FantasticFour (USENIX Security ’21). Compared to their CPU-based implementations, the same protocols implemented on top of Piranha’s protocol-agnostic acceleration exhibit a 16−48× decrease in training time. For the first time, Piranha demonstrates the feasibility of training a realistic neural network (e.g. VGG), end-to-end, using MPC in a little over one day. Piranha is open source and available at https://github.com/ucbrise/piranha. 

## Paper Information
- Title:  `Telekine: Secure Computing with Cloud GPUs`
- Authors:  `Tyler Hunt ...`
- Conference/Journal: `NSDI'20`
- Link: [https://www.usenix.org/system/files/nsdi20-paper-hunt.pdf]()
- Abstract: GPUs have become ubiquitous in the cloud due to the dramatic performance gains they enable in domains such as machine learning and computer vision. However, offloading GPU computation to the cloud requires placing enormous trust in providers and administrators. Recent proposals for GPU trusted execution environments (TEEs) are promising but fail to address very real side-channel concerns. To illustrate the severity of the problem, we demonstrate a novel attack that enables an attacker to correctly classify images from ImageNet [17] by observing only the timing of GPU kernel execution, rather than the images themselves.
Telekine enables applications to use GPU acceleration in the cloud securely, based on a novel GPU stream abstraction that ensures execution and interaction through untrusted com- ponents are independent of any secret data. Given a GPU with support for a TEE, Telekine employs a novel variant of API remoting to partition application-level software into components to ensure secret-dependent behaviors occur only on trusted components. Telekine can securely train modern image recognition models on MXNet [10] with 10%–22% per- formance penalty relative to an insecure baseline with a locally attached GPU. It runs graph algorithms using Galois [75] on one and two GPUs with 18%–41% overhead.

## Paper Information
- Title:  `On the Correctness of GPU Programs`
- Authors:  `Chao Peng ...`
- Conference/Journal: `ISSTA'19`
- Link: [https://dl.acm.org/doi/pdf/10.1145/3293882.3338989]()
- Abstract: Testing is an important and challenging part of software devel- opment and its effectiveness depends on the quality of test cases. However, there exists no means of measuring quality of tests de- veloped for GPU programs and as a result, no test case generation techniques for GPU programs aiming at high test effectiveness. Existing criteria for sequential and multithreaded CPU programs cannot be directly applied to GPU programs as GPU follows a completely different memory and execution model.
We surveyed existing work on GPU program verification and bug fixes of open source GPU programs. Based on our findings, we define barrier, branch and loop coverage criteria and propose a set of mutation operators to measure fault finding capabilities of test cases. CLTestCheck, a framework for measuring quality of tests developed for GPU programs by code coverage analysis, fault seeding and work-group schedule amplification has been developed and evaluated using industry standard benchmarks. Experiments show that the framework is able to automatically measure test effectiveness and reveal unusual behaviours. Our planned work includes data flow coverage adopted for GPU programs to probe the underlying cause of unusual kernel behaviours and a more comprehensive work-group scheduler. We also plan to design and develop an automatic test case generator aiming at generating high quality test suites for GPU programs.


## TODOs
 - Organize the papers by research category, this could be for example, TEE, Memory security (overflow, UAF), Side/Covert Channels, etc
