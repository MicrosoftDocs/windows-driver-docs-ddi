---
UID: NA:rxstruc
ms.assetid: 65762d53-73cb-3de7-a883-98912cb2a1da
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Rxstruc.h header



This header is used by Installable file system. For more information, see
- [Installable file system](../_ifsk/index.md)

Rxstruc.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [RxGetRDBSSProcess function](nf-rxstruc-rxgetrdbssprocess.md) | RxGetRDBSSProcess returns a pointer to the process of the main thread used by the RDBSS kernel process. |
| [RxUnregisterMinirdr function](nf-rxstruc-rxunregisterminirdr.md) | RxUnregisterMinirdr is an inline routine called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table. |
