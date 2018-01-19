---
UID: NS:winsplp.BranchOfficeJobDataContainer
title: BranchOfficeJobDataContainer
author: windows-driver-content
description: This structure defines a container for one or more BranchOfficeJobData structures to sent to a server.
old-location: print\branchofficejobdatacontainer.htm
old-project: print
ms.assetid: 5C6D2FFC-DBFF-4C44-8757-ED87593A584F
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: BranchOfficeJobDataContainer, *PBranchOfficeJobDataContainer, *LPBranchOfficeJobDataContainer, BranchOfficeJobDataContainer
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
req.alt-api: BranchOfficeJobDataContainer
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
req.typenames: *PBranchOfficeJobDataContainer, *LPBranchOfficeJobDataContainer, BranchOfficeJobDataContainer
req.product: Windows 10 or later.
---

# BranchOfficeJobDataContainer structure



## -description
This structure defines a container for one or more <a href="RID">BranchOfficeJobData</a> structures to sent to a server.



## -syntax

````
typedef struct {
  DWORD               cJobDataEntries;
  BranchOfficeJobData JobData[1];
} BranchOfficeJobDataContainer, *PBranchOfficeJobDataContainer, *LPBranchOfficeJobDataContainer;
````


## -struct-fields

### -field cJobDataEntries

Describes the <b>DWORD</b> type member <b>cJobDataEntries</b>.


### -field JobData

Describes the <b>BranchOfficeJobData</b> type member <b>JobData</b>.


## -remarks
