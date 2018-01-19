---
UID: NS:hbapiwmi._SM_SendRPS_OUT
title: _SM_SendRPS_OUT
author: windows-driver-content
description: The SM_SendRPS_OUT structure is used to receive output parameters from the SM_SendRPS method.
old-location: storage\sm_sendrps_out.htm
old-project: storage
ms.assetid: e202a292-df26-4829-be51-b8427d2dee20
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SM_SendRPS_OUT, *PSM_SendRPS_OUT, SM_SendRPS_OUT
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
req.alt-api: SM_SendRPS_OUT
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
req.typenames: *PSM_SendRPS_OUT, SM_SendRPS_OUT
---

# _SM_SendRPS_OUT structure



## -description
The SM_SendRPS_OUT structure is used to receive output parameters from the SM_SendRPS method.



## -syntax

````
typedef struct _SM_SendRPS_OUT {
  ULONG HBAStatus;
  ULONG TotalRespBufferSize;
  ULONG OutRespBufferSize;
  UCHAR RespBuffer[1];
} SM_SendRPS_OUT, *PSM_SendRPS_OUT;
````


## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


### -field TotalRespBufferSize

The size, in bytes, of the results common transport (CT) command.


### -field OutRespBufferSize

The size, in bytes, of the data that was actually retrieved.


### -field RespBuffer

The results of the common transport command.


## -remarks
The WMI tool suite generates a declaration of the SM_SendRPS_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.</p>