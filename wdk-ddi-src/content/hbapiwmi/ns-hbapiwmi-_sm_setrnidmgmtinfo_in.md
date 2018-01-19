---
UID: NS:hbapiwmi._SM_SetRNIDMgmtInfo_IN
title: _SM_SetRNIDMgmtInfo_IN
author: windows-driver-content
description: The SM_SetRNIDMgmtInfo_IN structure is used to provide input parameters to the SM_SetRNIDMgmtInfo method.
old-location: storage\sm_setrnidmgmtinfo_in.htm
old-project: storage
ms.assetid: 4b248886-8f1d-42c3-89dc-f6f0cd9ae683
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SM_SetRNIDMgmtInfo_IN, *PSM_SetRNIDMgmtInfo_IN, SM_SetRNIDMgmtInfo_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SM_SetRNIDMgmtInfo_IN
req.alt-loc: hbapiwmi.h
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
req.typenames: *PSM_SetRNIDMgmtInfo_IN, SM_SetRNIDMgmtInfo_IN
---

# _SM_SetRNIDMgmtInfo_IN structure



## -description
The SM_SetRNIDMgmtInfo_IN structure is used to provide input parameters to the SM_SetRNIDMgmtInfo method.



## -syntax

````
typedef struct _SM_SetRNIDMgmtInfo_IN {
  HBAFC3MgmtInfo MgmtInfo;
} SM_SetRNIDMgmtInfo_IN, *PSM_SetRNIDMgmtInfo_IN;
````


## -struct-fields

### -field MgmtInfo

A structure of type HBAFC3MgmtInfo that holds FC3 management information. This information is used to configure the fibre channel adapter.


## -remarks
The WMI tool suite generates a declaration of the SM_SetRNIDMgmtInfo_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.</p>