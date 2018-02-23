---
UID: NS:winsplp.BranchOfficeJobDataContainer
title: BranchOfficeJobDataContainer
author: windows-driver-content
description: This structure defines a container for one or more BranchOfficeJobData structures to sent to a server.
old-location: print\branchofficejobdatacontainer.htm
old-project: print
ms.assetid: 5C6D2FFC-DBFF-4C44-8757-ED87593A584F
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PBranchOfficeJobDataContainer structure pointer [Print Devices], print.branchofficejobdatacontainer, BranchOfficeJobDataContainer, LPBranchOfficeJobDataContainer structure pointer [Print Devices], *PBranchOfficeJobDataContainer, *LPBranchOfficeJobDataContainer, BranchOfficeJobDataContainer structure [Print Devices], winsplp/PBranchOfficeJobDataContainer, LPBranchOfficeJobDataContainer, winsplp/BranchOfficeJobDataContainer, winsplp/LPBranchOfficeJobDataContainer, PBranchOfficeJobDataContainer
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winsplp.h
apiname:
-	BranchOfficeJobDataContainer
product: Windows
targetos: Windows
req.typenames: BranchOfficeJobDataContainer, *PBranchOfficeJobDataContainer, *LPBranchOfficeJobDataContainer
req.product: Windows 10 or later.
---

# BranchOfficeJobDataContainer structure


## -description


This structure defines a container for one or more <a href="https://docs.microsoft.com/en-us/dotnet/core/rid-catalog">BranchOfficeJobData</a> structures to sent to a server.


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

