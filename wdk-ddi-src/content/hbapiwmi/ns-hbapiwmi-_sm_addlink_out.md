---
UID: NS:hbapiwmi._SM_AddLink_OUT
title: _SM_AddLink_OUT (hbapiwmi.h)
description: The SM_AddLink_OUT structure is used to receive output parameters from the SM_AddLink WMI method.
old-location: storage\sm_addlink_out.htm
tech.root: storage
ms.assetid: 1c69b8b0-fe73-4e13-be09-70b99e0e3f32
ms.date: 03/29/2018
ms.keywords: "*PSM_AddLink_OUT, PSM_AddLink_OUT, PSM_AddLink_OUT structure pointer [Storage Devices], SM_AddLink_OUT, SM_AddLink_OUT structure [Storage Devices], _SM_AddLink_OUT, hbapiwmi/PSM_AddLink_OUT, hbapiwmi/SM_AddLink_OUT, storage.sm_addlink_out, structs-Fibre_a02f38fd-ea37-42cb-9c3d-387ffb097893.xml"
ms.topic: struct
f1_keywords:
 - "hbapiwmi/SM_AddLink_OUT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- SM_AddLink_OUT
product:
- Windows
targetos: Windows
req.typenames: SM_AddLink_OUT, *PSM_AddLink_OUT
---

# _SM_AddLink_OUT structure


## -description


The SM_AddLink_OUT structure is used to receive output parameters from the SM_AddLink WMI method.


## -struct-fields




### -field HBAStatus

A value associated with the WMI class qualifier <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a> that indicates the result of an HBA query operation.


## -remarks



The WMI tool suite generates a declaration of the SM_AddLink_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.



