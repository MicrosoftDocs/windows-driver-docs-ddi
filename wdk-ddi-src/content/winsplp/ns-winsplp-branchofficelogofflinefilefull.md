---
UID: NS:winsplp.BranchOfficeLogOfflineFileFull
title: BranchOfficeLogOfflineFileFull
author: windows-driver-content
description: Contains the necessary data for logging that the offline log archive on the current client overflowed at some point.
old-location: print\branchofficelogofflinefilefull.htm
old-project: print
ms.assetid: 41190CE8-8779-477C-BFB0-6410DF096EFD
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: BranchOfficeLogOfflineFileFull, *PBranchOfficeLogOfflineFileFull, BranchOfficeLogOfflineFileFull
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BranchOfficeLogOfflineFileFull
req.alt-loc: Winsplp.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PBranchOfficeLogOfflineFileFull, BranchOfficeLogOfflineFileFull
req.product: Windows 10 or later.
---

# BranchOfficeLogOfflineFileFull structure



## -description
Contains the necessary data for logging that the offline log archive on the current client overflowed at some point.



## -syntax

````
typedef struct {
  LPWSTR pMachineName;
} BranchOfficeLogOfflineFileFull, *PBranchOfficeLogOfflineFileFull;
````


## -struct-fields

### -field pMachineName

Specifies the name of the print client.


## -remarks
