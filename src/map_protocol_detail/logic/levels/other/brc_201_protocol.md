# BRC-201协议

* MAP协议中的 
  * BRC-201协议 = mapo-brc201协议 
    * 背景 
      * BRC-20代币的局限性 
        * 概述 
          * 尽管BRC-20为使用比特币网络的新方式铺平了道路，但这是一个非常早期的项目，有很多缺点。有限的互操作性和实用性是阻碍BRCV-20代币发展的两个主要缺点。 
        * 有限的互操作性 
          * BRC-20代币标准是专门为在比特币区块链生态系统中发挥作用而量身定制的。这方面导致了互操作性挑战，特别是对于希望使用替代区块链系统的用户而言。由于BTC网络上没有该功能，因此出现了此限制。 
          * 链之间的互操作性很重要，因为它促进了加密生态系统内跨不同区块链网络的无缝代币转移。这允许用户在方便的时候使用更便宜、更高效的网络。 
        * 效用有限 
          * BRC-20标准主要用于同质化资产的代币化，不适合非同质化资产的代币化或复杂代币功能的实现，如代币化的所有权或有条件的转让 
          * 因此，需要超出 BRC-20 标准能力的更专业的代币化功能的项目可能会寻求功能更丰富的代币标准。 
    * 是什么： 
      * BRC-20 代币的 跨链标准 / 跨链协议 / 跨链扩展协议 
        * BRC-201 proposes an extension protocol to the BRC-20 standard 
      * 它有一个增强的索引器，支持 BRC-201 来解析其他扩展操作 
    * 作用：用于 BRC-20 代币与图灵完备链上的代币交换 
      * It is aimed to be backward compatible with BRC-20 
      * brc201是brc20扩展协议 
        * 这个只是用来对接中继链的 
        * 中继链其实就是桥 
          * 对应的是 MAP中的ROUP
            * [ROUP](../../../../map_protocol_detail/logic/levels/dapp_level/roup.md)
    * 目的：支持以太坊、BNB 链和 MAP 中继链等智能合约的链 
      * It is aimed to improve scalability, especially to bridge BRC-20 tokens to chains with smart contract support, such as Ethereum, BNB Chain, Near, etc. 
    * 特点 
      * 该跨链标准与 BRC-20 兼容 
        * 这意味着它可用于将 BRC-20 代币桥接到以太坊、BNB Chain、NEAR 等智能合约支持链，从而实现 BRC-20 资产集成到 DeFi 和其他金融场景和应用中 
    * 更多用例 
      * 还可用于交易所和其他机构存入和提取 BRC-20 资产 
    * 官方文档 
      * brc-201 - 脉波开发者文档 (gitbook.io)
        * https://mapo.gitbook.io/docs-zh/ji-chu-zhu-ti/index-2/brc201
      * BRC-201: Cross-Chain Extension Protocol to BRC-20 Tokens | BRC-201 Protocol (mapsat.io)
        * https://docs.mapsat.io
    * 技术细节对比 
      * BRC-20 token transfer
        ```json
        { 
          "p": "brc-20", 
          "op": "transfer", 
          "tick": "ordi", 
          "amt": "100" 
        }
        ```
      * BRC-201 extend operation
        ```json
        { 
          "p": "brc-20", 
          "op": "transfer", 
          "tick": "ordi", 
          "amt": "100", 
          "chain": "eth", 
          "ext": "bridge-out/in", 
          "ref": "address/txhash" 
        }
        ```
        * BRC-201 introduces three additional fields: "chain", "ext", and "ref".
