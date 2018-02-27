---
UID: NA:rxworkq
ms.assetid: a16d6b4d-e662-310b-8a4f-7845b1de062b
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Rxworkq.h header



This header is used by Installable file system. For more information, see
- [Installable file system](../_ifsk/index.md)

Rxworkq.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [RxDispatchToWorkerThread function](nf-rxworkq-rxdispatchtoworkerthread.md) | RxDispatchToWorkerThread invokes a routine in the context of a worker thread. The memory for the WORK_QUEUE_ITEM is allocated by this routine. |
| [RxPostToWorkerThread function](nf-rxworkq-rxposttoworkerthread.md) | RxPostToWorkerThread invokes a routine passed as a parameter in the context of a worker thread. Memory for the WORK_QUEUE_ITEM must be allocated by the caller. |
| [RxSpinDownMRxDispatcher function](nf-rxworkq-rxspindownmrxdispatcher.md) | RxSpinDownMRxDispatcher tears down the dispatcher context for a network mini-redirector. |
