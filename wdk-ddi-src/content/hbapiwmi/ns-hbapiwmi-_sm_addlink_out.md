---
UID: NS:hbapiwmi._SM_AddLink_OUT
title: "_SM_AddLink_OUT"
author: windows-driver-content
description: The SM_AddLink_OUT structure is used to receive output parameters from the SM_AddLink WMI method.
old-location: storage\sm_addlink_out.htm
old-project: storage
ms.assetid: 1c69b8b0-fe73-4e13-be09-70b99e0e3f32
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PSM_AddLink_OUT, ,, A, L, M, O, P, PSM_AddLink_OUT, PSM_AddLink_OUT structure pointer [Storage Devices], S, SM_AddLink_OUT, SM_AddLink_OUT structure [Storage Devices], T, U, _, _SM_AddLink_OUT, d, hbapiwmi/PSM_AddLink_OUT, hbapiwmi/SM_AddLink_OUT, i, k, n, storage.sm_addlink_out, structs-Fibre_a02f38fd-ea37-42cb-9c3d-387ffb097893.xml"
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
-	SM_AddLink_OUT
product: Windows
targetos: Windows
req.typenames: SM_AddLink_OUT, *PSM_AddLink_OUT
---

# _SM_AddLink_OUT structure


## -description


The SM_AddLink_OUT structure is used to receive output parameters from the SM_AddLink WMI method.


## -syntax


````
typedef struct _SM_AddLink_OUT {
  ULONG HBAStatus;
} SM_AddLink_OUT, *PSM_AddLink_OUT;
````


## -struct-fields




### -field HBAStatus

A value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation.


## -remarks



The WMI tool suite generates a declaration of the SM_AddLink_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.



