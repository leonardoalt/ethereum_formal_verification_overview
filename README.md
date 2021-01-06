# Ethereum Formal Verification

This page tries to give an overview of the formal verification (and related) projects in the Ethereum ecosystem, extending and updating https://github.com/pirapira/ethereum-formal-verification-overview.

The focus here is formal verification of smart contracts, while attempting to also gather information about formal verification of protocols and compilers.

The lists are not complete and you are encouraged to visit the project pages to know more about them.

Please do not hesitate and open an issue/PR if you have information not present here or if you find a mistake.

You might also want to visit the [Ethereum Formal Methods Gitter channel](https://gitter.im/ethereum/formal-methods).


## Compilers

### Solidity

* [Yul-Semantics](https://github.com/ethereum/yul-semantics): Yul is an IR language used by the Solidity compiler
that provides several different optimizers. Yul formal semantics enables equivalence checking between nonoptimized and
optimized versions of the same program.
* [Yul-Isabelle](https://github.com/mmalvarez/Yul-Isabelle). The semantics of the IR Yul formalized in Isabelle.

## Ethereum 2.0

### Phase 0

* [Deposit Contract (Runtime Verification) (part 1)](https://runtimeverification.com/blog/formal-verification-of-ethereum-2-0-deposit-contract-part-1/)
* [Deposit Contract (Runtime Verification) (part 2)](https://runtimeverification.com/blog/end-to-end-formal-verification-of-ethereum-2-0-deposit-smart-contract/)
* [Formal Verification of the Eth2.0 Specs in Dafny](https://github.com/ConsenSys/eth2.0-dafny): The objective of this project is to write a formal specification of the Eth2.0 specification in the verification-aware programming language [Dafny](https://github.com/dafny-lang/dafny/wiki).
* [Fully Mechanised Proof of the Deposit Contract's Incremental Merkle tree algorithm in Dafny](https://github.com/ConsenSys/deposit-sc-dafny).

## Smart Contracts

### Projects / Tools

There are several projects aiming at formal verification of smart contracts. The list given here is separated by target language and then sorted alphabetically. A few resource links are given with each project. For more resources on a specific project please visit the project's page.

#### EVM Bytecode

* [EtherTrust](https://www.netidee.at/ethertrust): Analysis tool for EVM bytecode.
    - Paper: [Foundations and Tools for the Static Analysis of Ethereum smart contracts](https://secpriv.tuwien.ac.at/fileadmin/t/secpriv/Papers/cav2018.pdf), Ilya Grishchenko et al. (2018).
* [EthIsabelle](https://github.com/pirapira/eth-isabelle): A Lem formalization of EVM and some Isabelle/HOL proofs.
    - Talk: [Formal Verification of Smart Contracts](https://yoichihirai.com/deedtalk.pdf), Yoichi Hirai.
* [HEVM](https://github.com/dapphub/dapptools): Symbolic execution engine and equivalence checker for EVM code.
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
* [VerX](http://verx.ch/): Full functional verification for Ethereum smart contracts.
    - Paper: [VerX: Safety Verification of Smart Contracts](https://files.sri.inf.ethz.ch/website/papers/sp20-verx.pdf), Permenev et al. (2019).

#### Solidity

* [Certora](https://www.certora.com/)
   - Paper: [Finding Bugs Automatically in Smart Contracts with Parameterized Invariants](https://www.certora.com/pubs/sbc2020.pdf), Thomas Bernardi et al (2020)
* [Scribble](https://docs.scribble.codes/): Scribble is a runtime verification tool for Solidity that transforms annotations in the [Scribble specification language](https://docs.scribble.codes/language/introduction) into concrete assertions that check the specification.
* [Slither](https://github.com/trailofbits/slither): Solidity static analysis framework that checks for specific vulnerabilities.
    - Article: [Slither – a Solidity static analysis framework](https://blog.trailofbits.com/2018/10/19/slither-a-solidity-static-analysis-framework/).
* [SmartCheck](https://github.com/smartdec/smartcheck): Static analysis tool for discovering vulnerabilities in Solidity contracts.
    - Paper: [SmartCheck: static analysis of ethereum smart contracts](https://dl.acm.org/citation.cfm?id=3194113.3194115), Sergei Tikhomirov et al. (2018).
* [Solidity's SMTChecker](https://github.com/ethereum/solidity): SMT-based model checker built-in the Solidity compiler which statically checks safety properties at compile-time, considering an unbounded number of transactions.
    - Talk: [Using Solidity's SMTChecker - Devcon IV](https://www.youtube.com/watch?v=QQbWpN76HEg), Leonardo Alt.
    - Slides: [Fully Automated Inductive Invariants Inference for Solidity Smart Contracts - Devcon V](https://github.com/leonardoalt/text/blob/master/chc_devcon_v/chc.pdf), Leonardo Alt.
    - Article: [Formal Verification in Solidity](https://medium.com/@leonardoalt/formal-verification-in-solidity-5cbff7b7ff8), Leonardo Alt.
    - Article: [SMTChecker Toward Completeness](https://medium.com/@leonardoalt/smtchecker-toward-completeness-1a99c02e0133), Leonardo Alt.
    - Paper: [SMT-Based Verification of Solidity Smart Contracts](https://github.com/leonardoalt/text/blob/master/solidity_isola_2018/main.pdf), Leonardo Alt and Christian Reitwiessner (2018).
* [solc-verify](https://github.com/SRI-CSL/solidity): Functional verification of Solidity code using annotations and modular program verification.
    - Paper: [solc-verify: A Modular Verifier for Solidity Smart Contracts](https://arxiv.org/abs/1907.04262), Á. Hajdu, D. Jovanović (2019).
    - Talk: [solc-verify, a source-level formal verification tool for Solidity smart contracts](https://www.youtube.com/watch?v=1q2gSm3NuQA), given by Á. Hajdu at Solidity Summit (2020)
    - Paper: [SMT-Friendly Formalization of the Solidity Memory Model](https://arxiv.org/abs/2001.03256), Á. Hajdu, D. Jovanović (2020).
    - Talk: [SMT-Friendly Formalization of the Solidity Memory Model](https://youtu.be/B3ML9vGituk?t=626), given by Á. Hajdu at SMT (2020)
    - Paper: [Formal Specification and Verification of Solidity Contracts with Events](https://arxiv.org/abs/2005.10382), Á. Hajdu, D. Jovanović, G. Ciocarlie (2020).
    - Talk: [Formal Specification and Verification of Solidity Contracts with Events](https://youtu.be/NNytwVBZ1no), given by Á. Hajdu at FMBC (2020).
* [VeriSol](https://github.com/microsoft/verisol): Formal specification, verification and scalable refutation of Solidity smart contracts using code contracts, Boogie and Corral. 
    - Slides: [Formal Verification of Smart Contracts and Protocols: What, Why, How - Devcon V](https://github.com/microsoft/verisol/blob/master/Docs/devcon5-verisol.pptx), Shuvendu Lahiri et al.
    - Article: [Researchers work to secure Azure Blockchain smart contracts with formal verification ](https://www.microsoft.com/en-us/research/blog/researchers-work-to-secure-azure-blockchain-smart-contracts-with-formal-verification/), Microsoft Research Blog.
    - Paper: [Formal Specification and Verification of Smart Contracts for Azure Blockchain
](https://arxiv.org/abs/1812.08829), Yuepeng Wang, Shuvendu K. Lahiri, Shuo Chen, Rong Pan, Isil Dillig, Cody Born, Immad Naseer.

#### Vyper

* [FVyper](https://github.com/LayerXcom/verified-vyper-contracts): A collection of useful Vyper contracts developed with formal methods (KEVM).
* [KVyper](https://github.com/kframework/vyper-semantics): Semantics of Vyper in K.

### Papers without project pages
* [Debugging Smart Contract's Business Logic Using Symbolic Model-Checking](https://arxiv.org/abs/1812.00619), Evgeniy Shishkin (2018).
* [Computing Exact Worst-Case Gas Consumption for Smart Contracts](https://www.inf.usi.ch/postdoc/hyvarinen/publications/MarescottiBHAS_ISOLA2018.pdf), Matteo Marescotti et al. (2018).
* [Towards Verification of Ethereum Smart Contracts: A Formalization of Core of Solidity](https://www.researchgate.net/publication/329147546_Towards_Verification_of_Ethereum_Smart_Contracts_A_Formalization_of_Core_of_Solidity_10th_International_Conference_VSTTE_2018_Oxford_UK_July_18-19_2018_Revised_Selected_Papers), Jakub Zakrzewski (2018).
* [Online Detection of Effectively Callback Free Objects with Applications to Smart Contracts](https://arxiv.org/pdf/1801.04032.pdf), Shelly Grossman et al. (2018).
* [ZEUS: Analyzing Safety of Smart Contracts](http://wp.internetsociety.org/ndss/wp-content/uploads/sites/25/2018/02/ndss2018_09-1_Kalra_paper.pdf), Sukrit Kalra et al. (2018).
* [Formal Verification of Smart Contracts](https://hal.inria.fr/hal-01400469/document), Karthikeyan Bhargavan et al. (2016).
