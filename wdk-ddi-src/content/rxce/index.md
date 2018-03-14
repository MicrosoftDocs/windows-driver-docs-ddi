---
UID: NA:rxce
ms.assetid: 21be7cda-22a7-31c2-8fd4-74b9d08f24bf
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Rxce.h header



This header is used by Installable file system. For more information, see
- [Installable file system](../_ifsk/index.md)

Rxce.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [RxCeAllocateIrpWithMDL function](nf-rxce-rxceallocateirpwithmdl.md) | RxCeAllocateIrpWithMDL allocates an IRP and associates it with an existing memory descriptor list. |
| [RxCeBuildAddress function](nf-rxce-rxcebuildaddress.md) | RxCeBuildAddress associates a transport address with a transport binding. |
| [RxCeBuildConnection function](nf-rxce-rxcebuildconnection.md) | RxCeBuildConnection establishes a connection between a local RDBSS connection address and a given remote address. |
| [RxCeBuildConnectionOverMultipleTransports function](nf-rxce-rxcebuildconnectionovermultipletransports.md) | RxCeBuildConnectionOverMultipleTransports establishes a connection between a local RDBSS connection address and a given remote address and supports multiple transports. |
| [RxCeBuildTransport function](nf-rxce-rxcebuildtransport.md) | RxCeBuildTransport binds an RDBSS transport object to a specified transport name. |
| [RxCeBuildVC function](nf-rxce-rxcebuildvc.md) | RxCeBuildVC adds a virtual circuit to a specified RDBSS connection.. |
| [RxCeCancelConnectRequest function](nf-rxce-rxcecancelconnectrequest.md) | RxCeCancelConnectRequest cancels a previously issued connection request. Note that this routine is not currently implemented. |
| [RxCeFreeIrp function](nf-rxce-rxcefreeirp.md) | RxCeFreeIrp frees an IRP. |
| [RxCeInitiateVCDisconnect function](nf-rxce-rxceinitiatevcdisconnect.md) | RxCeInitiateVCDisconnect initiates a disconnect on the virtual circuit. |
| [RxCeQueryAdapterStatus function](nf-rxce-rxcequeryadapterstatus.md) | RxCeQueryAdapterStatus returns the ADAPTER_STATUS structure for a given transport in a caller-allocated buffer. |
| [RxCeQueryInformation function](nf-rxce-rxcequeryinformation.md) | RxCeQueryInformation queries information about a connection in a caller-allocated buffer. |
| [RxCeQueryTransportInformation function](nf-rxce-rxcequerytransportinformation.md) | RxCeQueryTransportInformation queries transport information for a given transport. |
| [RxCeSend function](nf-rxce-rxcesend.md) | RxCeSend sends a transport service data unit (TSDU) along the specified connection on a virtual circuit. |
| [RxCeSendDatagram function](nf-rxce-rxcesenddatagram.md) | RxCeSendDatagram sends a transport service data unit (TSDU) along the specified connection on a virtual circuit. |
| [RxCeTearDownAddress function](nf-rxce-rxceteardownaddress.md) | RxCeTearDownAddress deregisters a transport address from a transport binding. |
| [RxCeTearDownConnection function](nf-rxce-rxceteardownconnection.md) | RxCeTearDownConnection tears down a given connection between a local RDBSS connection address and a remote address. |
| [RxCeTearDownTransport function](nf-rxce-rxceteardowntransport.md) | RxCeTearDownTransport unbinds an RDBSS transport object. |
| [RxCeTearDownVC function](nf-rxce-rxceteardownvc.md) | RxCeTearDownVC deregisters a virtual circuit from a specified RDBSS connection. |
