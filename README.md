# Ethereum Formal Verification

This page tries to give an overview of the formal verification (and related) projects in the Ethereum ecosystem, extending and updating https://github.com/pirapira/ethereum-formal-verification-overview.

The focus here is formal verification and other types of analysis of smart contracts, while attempting to also gather information about formal verification of protocols and compilers.

The lists are not complete and you are encouraged to visit the project pages to know more about them.

Please do not hesitate and open an issue/PR if you have information not present here or if you find a mistake.

You might also want to visit the [Ethereum Formal Methods Gitter channel](https://gitter.im/ethereum/formal-methods).


## Compilers

### Solidity / Yul

* [Yul-ACL2](https://github.com/acl2/acl2/tree/master/books/kestrel/yul/language). The semantics of the IR Yul formalized in ACL2 framework.
* [Yul-Isabelle](https://github.com/ethereum/Yul-Isabelle). The semantics of the IR Yul formalized in Isabelle.
* [Yul-Lean](https://github.com/NethermindEth/Yul-Specification): A formal specification of the Yul IR semantics in the Lean proof assistant.
    - Article: [Securing Warp: A formal specification of the Yul IR](https://medium.com/nethermind-eth/securing-warp-a-formal-specification-of-the-yul-ir-85bb3bf51c62), Julian Sutherland.
* [Yul-K](https://github.com/ethereum/Yul-K): The semantics of the IR Yul formalized in the K framework.
* [Solidity Optimizer Transformations](https://github.com/acl2/acl2/tree/master/books/kestrel/yul/transformations). Formalizes in ACL2 and verifies correctness of some of the Yul optimizer transformations present in the Solidity compiler.

## Ethereum 2.0

### Phase 0

* [Deposit Contract (Runtime Verification) (part 1)](https://runtimeverification.com/blog/formal-verification-of-ethereum-2-0-deposit-contract-part-1/)
* [Deposit Contract (Runtime Verification) (part 2)](https://runtimeverification.com/blog/end-to-end-formal-verification-of-ethereum-2-0-deposit-smart-contract/)
* [Formal Verification of the Eth2.0 Specs in Dafny](https://github.com/ConsenSys/eth2.0-dafny): The objective of this project is to write a formal specification of the Eth2.0 specification in the verification-aware programming language [Dafny](https://github.com/dafny-lang/dafny/wiki).
	- Paper: [Formal Verification of the Ethereum 2.0 Beacon Chain](https://arxiv.org/abs/2110.12909), Franck Cassez, Joanne Fuller, Aditya Asgaonkar.
* [Fully Mechanised Proof of the Deposit Contract's Incremental Merkle tree algorithm in Dafny](https://github.com/ConsenSys/deposit-sc-dafny).


## Smart Contracts

### Projects / Tools

There are several projects aiming at formal specification and verification of smart contracts. The list given here is separated by target language and then sorted alphabetically. A few resource links are given with each project. For more resources on a specific project please visit the project's page.

There is also an overwhelming amount of papers describing techniques related to formal verification of smart contracts. For example, visit
https://ntu-srslab.github.io/smart-contract-publications/ and type `2020` into the search box. For that reason I am not listing anymore papers
describing techniques for which I could not find the actual tool.

#### Learning

* [Formal Methods for DeFi Developers](https://github.com/WilfredTA/formal-methods-curriculum/): a course sequence for training developers in the use & development of formal methods and formal tools.

#### Specification

* [Act](https://github.com/ethereum/act): Act allows specification of storage updates, pre/post conditions and contract invariants. Its tool suite also has proof backends able to prove many properties via Coq, SMT solvers, or hevm.
    - Article: [Act 0.1 Release & Tutorial](https://fv.ethereum.org/2021/08/31/act-0.1/), David Terry.
    - Talk: [Smart contracts as inductive systems](https://www.youtube.com/watch?v=WbL8U-nyhJE), Martin Lundfall.
* [Certora Specification Language](https://www.certora.com/pubs/QuickGuide.pdf): Used by the Certora verification tool to write properties about analyzed contracts.
* [Scribble](https://docs.scribble.codes/): Scribble is a runtime verification tool for Solidity that transforms annotations in the [Scribble specification language](https://docs.scribble.codes/language/introduction) into concrete assertions that check the specification.

#### Fuzzing

* [Echidna](https://github.com/crytic/echidna/): A fast smart contract fuzzer. It is designed for fuzzing and property-based testing.
* [Harvey](https://consensys.net/diligence/blog/2019/01/fuzzing-smart-contracts-using-multiple-transactions/): A fuzzer for Ethereum smart contracts.
* [hevm](https://github.com/dapphub/dapptools/tree/master/src/hevm): hevm is many things as you will see below, including a fuzzer. The fuzzer can also be used to try to break invariants.
    - Article: [Symbolic Execution With ds-test](https://fv.ethereum.org/2020/12/11/symbolic-execution-with-ds-test/), David Terry.
    
#### Economics / Game Theory

* [Clockwork Finance Framework](https://github.com/defi-formal/cff/): A general purpose formal verification framework and mechanized proof system for reasoning about economic security properties of composed DeFi contracts, using K framework's symbolic execution engine and model checker.
   - Paper: [Clockwork Finance: Automated Analysis of Economic Security in Smart Contracts](https://arxiv.org/pdf/2109.04347.pdf)
   - Talk: [Clockwork Finance: Automated Analysis of Economic Security in Smart Contracts - SBC22](https://www.youtube.com/watch?v=n52xBSk2TSs)
   - Slides: [Clockwork Finance](https://www.cs.cornell.edu/~babel/slides/cff_sbc_pdf.pdf)


#### EVM Bytecode

* [Certora](https://www.certora.com/)
   - Paper: [Finding Bugs Automatically in Smart Contracts with Parameterized Invariants](https://www.certora.com/pubs/sbc2020.pdf), Thomas Bernardi et al (2020)
* [EthBMC](https://github.com/RUB-SysSec/EthBMC): A Bounded Model Checker for Smart Contracts.
* [EtherTrust](https://www.netidee.at/ethertrust): Analysis tool for EVM bytecode.
    - Paper: [Foundations and Tools for the Static Analysis of Ethereum smart contracts](https://secpriv.tuwien.ac.at/fileadmin/t/secpriv/Papers/cav2018.pdf), Ilya Grishchenko et al. (2018).
* [EthIsabelle](https://github.com/pirapira/eth-isabelle): A Lem formalization of EVM and some Isabelle/HOL proofs.
    - Talk: [Formal Verification of Smart Contracts](https://yoichihirai.com/deedtalk.pdf), Yoichi Hirai.
* [eThor](https://secpriv.wien/ethor/): Static analysis for Ethereum smart contracts.
* [GASOL](https://github.com/costa-group/gasol-optimizer): A generic framework that optimizes smart contracts by applying the technique called "super-optimization" that consists in optimizing basic blocks.
	- Paper: A Max-SMT Superoptimizer for EVM handling Memory and Storage. Elvira Albert, Pablo Gordillo, Alejandro Hernández-Cerezo and Albert Rubio, TACAS 2022. To appear.
	- Paper: Super-Optimization of Smart Contracts. Elvira Albert, Pablo Gordillo, Alejandro Hernández-Cerezo, Albert Rubio and Maria A. Schett, 2022. To appear.
* [hevm](https://github.com/dapphub/dapptools/tree/master/src/hevm): Symbolic execution engine and equivalence checker for EVM code.
    - Article: [Symbolic Execution With ds-test](https://fv.ethereum.org/2020/12/11/symbolic-execution-with-ds-test/), David Terry.
    - Article: [Symbolic execution for hevm](https://fv.ethereum.org/2020/07/28/symbolic-hevm-release/), Martin Lundfall.
* [KEVM](https://github.com/kframework/evm-semantics): K Semantics of the Ethereum Virtual Machine (EVM).
    - Talk: [KEVM Overview](https://www.youtube.com/watch?v=tIq_xECoicQ).
    - Paper: [KEVM: A Complete Semantics of the Ethereum Virtual Machine](https://www.ideals.illinois.edu/handle/2142/97207), Everett Hildenbrandt et al. (2017).
* [KLab](https://github.com/dapphub/klab): K framework proof explorer and smart contract specification format.
    - Tutorial: [KLab](https://youtu.be/z4mIo38x1u8), Everett Hildenbrandt.
    - Workshop: Formal Verification Workshop Using KLab - Devcon IV. Could not find video/slides.
* [Manticore](https://github.com/trailofbits/manticore): EVM bytecode analysis tool based on symbolic execution.
    - Article: [Manticore: Symbolic execution for humans](https://blog.trailofbits.com/2017/04/27/manticore-symbolic-execution-for-humans/).
    - Workshop: [Using Manticore and Symbolic Execution to Find Smart Contracts Bugs - Devcon IV](https://github.com/trailofbits/publications/tree/master/workshops/Using%20Manticore%20and%20Symbolic%20Execution%20to%20Find%20Smart%20Contracts%20Bugs%20-%20Devcon%204).
* [MAIAN](https://github.com/MAIAN-tool/MAIAN): EVM bytecode analysis tool that checks whether a contract might be suicidal, prodigal or greedy.
    - Paper: [Finding The Greedy, Prodigal, and Suicidal Contracts at Scale](https://arxiv.org/pdf/1802.06038.pdf), Ivica Nikolic et al. (2018).
* [Mythril](https://github.com/ConsenSys/mythril-classic): EVM bytecode security analysis tool that uses concolic analysis, taint analysis and control flow checking.
    - Article: [Practical Smart Contract Security Analysis and Exploitation— Part 1](https://hackernoon.com/practical-smart-contract-security-analysis-and-exploitation-part-1-6c2f2320b0c), Bernhard Mueller.
* [Oyente](https://github.com/melonproject/oyente): EVM bytecode analysis tool based on symbolic execution.
    - Paper: [Making Smart Contracts Smarter](https://eprint.iacr.org/2016/633.pdf), Loi Luu et al. (2016).
* [Securify](https://github.com/eth-sri/securify2): Security scanner for Ethereum smart contracts.
    - Paper: [Securify: Practical Security Analysis of Smart Contracts](https://files.sri.inf.ethz.ch/website/papers/ccs18-securify.pdf), Petar Tsankov et al. (2018).
* [Verifereum](https://verifereum.org): Specification of the EVM and full functional verification of EVM bytecode in HOL4.
* [VerX](http://verx.ch/): Full functional verification for Ethereum smart contracts.
    - Paper: [VerX: Safety Verification of Smart Contracts](https://files.sri.inf.ethz.ch/website/papers/sp20-verx.pdf), Permenev et al. (2019).
* [EVM-Dafny](https://github.com/Consensys/evm-dafny): A formal and executable semantics of the EVM in Dafny.
    - Paper(FM23): [Formal and Executable Semantics of the Ethereum Virtual Machine in Dafny](https://link.springer.com/chapter/10.1007/978-3-031-27481-7_32),Franck Cassez et al.(2023).
    - Paper(Arxiv version): [Formal and Executable Semantics of the Ethereum Virtual Machine in Dafny](https://arxiv.org/abs/2303.00152), Franck Cassez et al.(2023).

#### Solidity

* [Slither](https://github.com/trailofbits/slither): Solidity static analysis framework that checks for specific vulnerabilities.
    - Article: [Slither – a Solidity static analysis framework](https://blog.trailofbits.com/2018/10/19/slither-a-solidity-static-analysis-framework/).
* [SmartAce](https://github.com/contract-ace/smartace): An automated framework for smart contract verification.
	- Paper: [Verifying Solidity Smart Contracts Via Communication Abstraction in SmartACE](https://mariachris.github.io/Pubs/VMCAI-2022.pdf), Scott Wesley et al. (2022).
* [SmartCheck](https://github.com/smartdec/smartcheck): Static analysis tool for discovering vulnerabilities in Solidity contracts.
    - Paper: [SmartCheck: static analysis of ethereum smart contracts](https://dl.acm.org/citation.cfm?id=3194113.3194115), Sergei Tikhomirov et al. (2018).
* [Solidifier](https://github.com/blockhousetech/research/tree/master/Solidifier): Bounded Model Checker for Solidity.
    - Paper: [Solidifier: bounded model checking solidity using lazy contract deployment and precise memory modelling](https://dl.acm.org/doi/10.1145/3412841.3442051), Pedro Antonino & A. W. Roscoe (2021).
* [Solidity's SMTChecker](https://github.com/ethereum/solidity): SMT and Horn-based model checker built-in the Solidity compiler which statically checks safety properties at compile-time, considering an unbounded number of transactions.
    - Slides: [Formally Verifying Ethereum Smart Contracts by Overwhelming Horn Solvers](https://raw.githubusercontent.com/leonardoalt/text/master/dagstuhl/talk.pdf), Dagstuhl Seminar on Rigorous Methods for Smart Contracts, Leonardo Alt.
    - Talk: [Fully Automated Formal Verification: How far can we go? - EthCC 4](https://www.youtube.com/watch?v=RunMhlTtdKw), Leonardo Alt & Martin Lundfall.
    - Slides: [Fully Automated Formal Verification: How far can we go? - EthCC 4](https://github.com/leonardoalt/ethcc/blob/master/talk/ethcc.pdf), Leonardo Alt & Martin Lundfall.
    - Article: [Automated Synthesis of External Unknown Functions](https://fv.ethereum.org/2021/01/18/smtchecker-and-synthesis-of-external-functions/), Leonardo Alt.
    - Talk: [Fully Automated Inductive Invariants Inference for Solidity Smart Contracts - Devcon V](https://www.youtube.com/watch?v=q40OrUZoG40), Leonardo Alt.
    - Slides: [Fully Automated Inductive Invariants Inference for Solidity Smart Contracts - Devcon V](https://github.com/leonardoalt/text/blob/master/chc_devcon_v/chc.pdf), Leonardo Alt.
    - Article: [SMTChecker Toward Completeness](https://medium.com/@leonardoalt/smtchecker-toward-completeness-1a99c02e0133), Leonardo Alt.
    - Paper: [Accurate Smart Contract Verification through Direct Modelling](https://github.com/leonardoalt/text/blob/master/smtchecker_chc/smtchecker_chc.pdf), Matteo Marescotti, Rodrigo Otoni, Leonardo Alt, Patrick Eugster, Antti E. J. Hyvärinen, and Natasha Sharygina (2020).
    - Paper: [SMT-Based Verification of Solidity Smart Contracts](https://github.com/leonardoalt/text/blob/master/solidity_isola_2018/main.pdf), Leonardo Alt and Christian Reitwiessner (2018).
* [solc-verify](https://github.com/SRI-CSL/solidity): Functional verification of Solidity code using annotations and modular program verification.
    - Paper: [solc-verify: A Modular Verifier for Solidity Smart Contracts](https://arxiv.org/abs/1907.04262), Á. Hajdu, D. Jovanović (2019).
    - Talk: [solc-verify, a source-level formal verification tool for Solidity smart contracts](https://www.youtube.com/watch?v=1q2gSm3NuQA), given by Á. Hajdu at Solidity Summit (2020)
    - Paper: [SMT-Friendly Formalization of the Solidity Memory Model](https://arxiv.org/abs/2001.03256), Á. Hajdu, D. Jovanović (2020).
    - Talk: [SMT-Friendly Formalization of the Solidity Memory Model](https://youtu.be/B3ML9vGituk?t=626), given by Á. Hajdu at SMT (2020)
    - Paper: [Formal Specification and Verification of Solidity Contracts with Events](https://arxiv.org/abs/2005.10382), Á. Hajdu, D. Jovanović, G. Ciocarlie (2020).
    - Talk: [Formal Specification and Verification of Solidity Contracts with Events](https://youtu.be/NNytwVBZ1no), given by Á. Hajdu at FMBC (2020).
* [VeriSmart](https://github.com/kupl/VeriSmart-public): Safety verified for Solidity smart contracts, based on automatic inference of contract invariants.
* [VeriSol](https://github.com/microsoft/verisol): Formal specification, verification and scalable refutation of Solidity smart contracts using code contracts, Boogie and Corral. 
    - Slides: [Formal Verification of Smart Contracts and Protocols: What, Why, How - Devcon V](https://github.com/microsoft/verisol/blob/master/Docs/devcon5-verisol.pptx), Shuvendu Lahiri et al.
    - Article: [Researchers work to secure Azure Blockchain smart contracts with formal verification ](https://www.microsoft.com/en-us/research/blog/researchers-work-to-secure-azure-blockchain-smart-contracts-with-formal-verification/), Microsoft Research Blog.
    - Paper: [Formal Specification and Verification of Smart Contracts for Azure Blockchain
](https://arxiv.org/abs/1812.08829), Yuepeng Wang, Shuvendu K. Lahiri, Shuo Chen, Rong Pan, Isil Dillig, Cody Born, Immad Naseer.

#### Vyper

* [Vyper-HOL](https://github.com/verifereum/vyper-hol): Semantics of Vyper and verified compilation of Vyper in HOL4.
* [2vyper](https://github.com/viperproject/2vyper): Automatic verifier for Vyper smart contracts, based on the [Viper](https://github.com/viperproject/2vyper) verification infrastructure.
* [FVyper](https://github.com/LayerXcom/verified-vyper-contracts): A collection of useful Vyper contracts developed with formal methods (KEVM).
* [KVyper](https://github.com/kframework/vyper-semantics): Semantics of Vyper in K.

## Arithmetic Circuits and Zero Knowledge Applications

* [ACL2 formalization of Semaphore](https://github.com/acl2/acl2/tree/master/books/kestrel/ethereum/semaphore)
	- [Semaphore](https://github.com/appliedzkp/semaphore)
	- [ACL2 Semaphore Docs](https://www.cs.utexas.edu/users/moore/acl2/manuals/latest/?topic=ZKSEMAPHORE____SEMAPHORE)
* [Cairo verification using Lean](https://github.com/starkware-libs/formal-proofs)
	- Paper: [A verified algebraic representation of Cairo program execution](https://github.com/starkware-libs/formal-proofs), Jeremy Avigad et al.
* [Ecne](https://github.com/franklynwang/EcneProject): An engine for verifying the soundness of R1CS constraints.
* [Leo](https://github.com/AleoHQ/leo)
	- Paper: [LEO: A Programming Language for Formally Verified, Zero-Knowledge Applications](https://eprint.iacr.org/2021/651.pdf)

# Other Lists

* [Crytic Awesome Ethereum Security](https://github.com/crytic/awesome-ethereum-security): Less focused on formal verification but has a broader scope of types of tools.
* [Consensys Security Best Practices](https://consensys.github.io/smart-contract-best-practices/): Best practices and list of security tools.
* [ethereum.org](https://ethereum.org/de/developers/docs/security/): Intro to security of smart contracts.
* [formalverification.xyz](Formal Verification in Crypto): Categorized list of companies doing crypto FV.
* [OpenZeppelin's list of Post-Mortems](https://forum.openzeppelin.com/t/list-of-ethereum-smart-contracts-post-mortems/1191)
