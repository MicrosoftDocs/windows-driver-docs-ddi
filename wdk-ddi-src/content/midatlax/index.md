---
UID: NA:midatlax
ms.assetid: e8c80790-7ec0-3fdc-83c7-699e2f78cdb7
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Midatlax.h header



This header is used by Installable file system. For more information, see
- [Installable file system](../_ifsk/index.md)

Midatlax.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [RxAssociateContextWithMid function](nf-midatlax-rxassociatecontextwithmid.md) | RxAssociateContextWithMid associates the supplied opaque context with an available multiplex ID (MID) from a MID_ATLAS. |
| [RxCreateMidAtlas function](nf-midatlax-rxcreatemidatlas.md) | RxCreateMidAtlas allocates a new instance of MID_ATLAS data structure and initializes it. |
| [RxDestroyMidAtlas function](nf-midatlax-rxdestroymidatlas.md) | RxDestroyMidAtlas destroys an existing instance of a MID_ATLAS data structure and frees the allocated memory. |
| [RxMapAndDissociateMidFromContext function](nf-midatlax-rxmapanddissociatemidfromcontext.md) | RxMapAndDissociateMidFromContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure and then disassociates the MID from the context. |
| [RxMapMidToContext function](nf-midatlax-rxmapmidtocontext.md) | RxMapMidToContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure. |
| [RxReassociateMid function](nf-midatlax-rxreassociatemid.md) | RxReassociateMid reassociates a Multiplex ID (MID) with an alternate context. |
