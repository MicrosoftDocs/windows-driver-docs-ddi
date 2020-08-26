---
UID: NS:hbapiwmi._SM_SendRNID_IN
title: _SM_SendRNID_IN (hbapiwmi.h)
description: The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.
old-location: storage\sm_sendrnid_in.htm
tech.root: storage
ms.assetid: 7d94fc94-bfc6-4666-a321-71a0643f3140
ms.date: 03/29/2018
keywords: ["SM_SendRNID_IN structure"]
ms.keywords: "*PSM_SendRNID_IN, PSM_SendRNID_IN, PSM_SendRNID_IN structure pointer [Storage Devices], SM_SendRNID_IN, SM_SendRNID_IN structure [Storage Devices], _SM_SendRNID_IN, hbapiwmi/PSM_SendRNID_IN, hbapiwmi/SM_SendRNID_IN, storage.sm_sendrnid_in, structs-Fibre_61452dff-7706-4a0a-838a-5220f7117668.xml"
f1_keywords:
 - "hbapiwmi/SM_SendRNID_IN"
 - "SM_SendRNID_IN"
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
- SM_SendRNID_IN
targetos: Windows
req.typenames: SM_SendRNID_IN, *PSM_SendRNID_IN
---

# _SM_SendRNID_IN structure


## -description


The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.


## -struct-fields




### -field HbaPortWWN

The worldwide name (WWN) of the local port.


### -field DestWWN

The worldwide name (WWN) of the destination port.


### -field DestFCID

The address identifier of the destination port.


### -field NodeIdDataFormat

The node identification data format.


### -field InRespBufferMaxSize

The maximum response buffer size.


## -remarks



The WMI tool suite generates a declaration of the SM_SendRNID_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.



