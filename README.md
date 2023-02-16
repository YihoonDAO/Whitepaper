---
description: >-
  Didao is the gateway to the Web3 network world, just like your account
  credentials in the traditional network.
---

# Overview

Didao is a blockchain-based, open-source, cross-chain decentralized account system. Didao provides a global unique naming system with the suffix '.dao', which can be used for scenarios such as transferring encrypted assets, domain name resolution, identity authentication, etc. As a decentralized account system, only the user has complete control and usage rights of the Didao account. At the same time, Didao is the first decentralized account system with wide compatibility, which can use any public chain address or even email to register and manage the Didao account.

The core elements of the Didao account are the owner/manager and the resolution record (i.e. its associated data). Unlike ENS, the owner/manager of Didao can be any public chain private key or even an email; unlike DNS, Didao supports any type of resolution record.

.dao is a decentralized application running on the Ethereum Mainnet. The .dao account and its transaction records are stored on the blockchain.

.dao offers a complete set of components in an open-source manner, including:

Core Protocol

This refers to a series of lock scripts and type scripts deployed on the Ethereum Mainnet, which define the standards for .dao account and its related operations, and are the concrete implementation of the .dao core protocol.

Presser

Presser is a smart program that can be run by anyone without permission, responsible for triggering a series of transactions that comply with the core protocol. It is a key module of the .dao system, and running Presser can earn system rewards from .dao.

Resolution Service

It analyzes the global state of .dao based on the transactions on Ethereum Mainnet, and provides account resolution services in the form of an interface.

Client SDK

This includes SDKs in various languages, designed to simplify the integration work of mobile wallets, web wallets, server wallets, and other .dao-related applications.

Dapp UI

Users finally use the various functions of .dao through various application interfaces. These applications can be used directly in the browser or integrated into popular wallet software.

The source code for all components can be found in our Github repository. Additionally, developers can implement their own Presser, Resolution Service, Client SDK, Dapp UI based on the Core Protocol.
