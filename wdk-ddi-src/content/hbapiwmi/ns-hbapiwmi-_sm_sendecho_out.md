---
UID: NS:hbapiwmi._SM_SendECHO_OUT
title: "_SM_SendECHO_OUT"
author: windows-driver-content
description: The SM_SendECHO_OUT structure is used to receive output parameters from the SM_SendECHO method.
old-location: storage\sm_sendecho_out.htm
old-project: storage
ms.assetid: b3f948e0-4066-487c-aaa9-de29c0023f10
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSM_SendECHO_OUT structure pointer [Storage Devices], hbapiwmi/SM_SendECHO_OUT, storage.sm_sendecho_out, PSM_SendECHO_OUT, *PSM_SendECHO_OUT, _SM_SendECHO_OUT, SM_SendECHO_OUT, SM_SendECHO_OUT structure [Storage Devices], hbapiwmi/PSM_SendECHO_OUT, structs-Fibre_54c4b9c6-e7c1-4125-9e76-0c3e271f5dea.xml
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
-	SM_SendECHO_OUT
product: Windows
targetos: Windows
req.typenames: SM_SendECHO_OUT, *PSM_SendECHO_OUT
---

# _SM_SendECHO_OUT structure


## -description


The SM_SendECHO_OUT structure is used to receive output parameters from the SM_SendECHO method.


## -syntax


````
typedef struct _SM_SendECHO_OUT {
  ULONG HBAStatus;
  ULONG OutRespBufferSize;
  UCHAR RespBuffer[1];
} SM_SendECHO_OUT, *PSM_SendECHO_OUT;
````


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


### -field OutRespBufferSize

The output response size.


### -field RespBuffer

The result of the operation.


## -remarks


The WMI tool suite generates a declaration of the SM_SendECHO_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.


