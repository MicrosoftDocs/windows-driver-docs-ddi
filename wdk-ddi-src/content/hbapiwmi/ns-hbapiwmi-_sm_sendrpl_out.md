---
UID: NS:hbapiwmi._SM_SendRPL_OUT
title: "_SM_SendRPL_OUT"
author: windows-driver-content
description: The SM_SendRPL_OUT structure is used to receive output parameters from the SM_SendRPL method.
old-location: storage\sm_sendrpl_out.htm
old-project: storage
ms.assetid: c8dfc30a-81ac-4342-9996-0c04db80e5e7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "_SM_SendRPL_OUT, hbapiwmi/PSM_SendRPL_OUT, SM_SendRPL_OUT structure [Storage Devices], PSM_SendRPL_OUT structure pointer [Storage Devices], PSM_SendRPL_OUT, *PSM_SendRPL_OUT, hbapiwmi/SM_SendRPL_OUT, structs-Fibre_831fc75d-cdee-4fba-9dd1-22204e814d50.xml, storage.sm_sendrpl_out, SM_SendRPL_OUT"
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
-	hbapiwmi.h
apiname:
-	SM_SendRPL_OUT
product: Windows
targetos: Windows
req.typenames: "*PSM_SendRPL_OUT, SM_SendRPL_OUT"
---

# _SM_SendRPL_OUT structure


## -description


The SM_SendRPL_OUT structure is used to receive output parameters from the SM_SendRPL method.


## -syntax


````
typedef struct _SM_SendRPL_OUT {
  ULONG HBAStatus;
  ULONG TotalRespBufferSize;
  ULONG OutRespBufferSize;
  UCHAR RespBuffer[1];
} SM_SendRPL_OUT, *PSM_SendRPL_OUT;
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


The WMI tool suite generates a declaration of the SM_SendRPL_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.


