---
UID: NA:prefix
ms.assetid: 40e93800-fca3-3d55-8a33-71ad08228385
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Prefix.h header



This header is used by Installable file system. For more information, see
- [Installable file system](../_ifsk/index.md)

Prefix.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [RxPrefixTableLookupName function](nf-prefix-rxprefixtablelookupname.md) | RxPrefixTableLookupName looks up a name in a prefix table used to catalog SRV_CALL, NET_ROOT, and V_NET_ROOT names and converts the underlying pointer to a structure that contains the name. |
| [RxpAcquirePrefixTableLockExclusive function](nf-prefix-rxpacquireprefixtablelockexclusive.md) | RxpAcquirePrefixTableLockExclusive acquires the prefix table lock exclusively. |
| [RxpAcquirePrefixTableLockShared function](nf-prefix-rxpacquireprefixtablelockshared.md) | RxpAcquirePrefixTableLockShared acquires the prefix table lock shared. |
| [RxpReleasePrefixTableLock function](nf-prefix-rxpreleaseprefixtablelock.md) | RxpReleasePrefixTableLock releases a previously acquired shared or exclusive prefix table lock. |
