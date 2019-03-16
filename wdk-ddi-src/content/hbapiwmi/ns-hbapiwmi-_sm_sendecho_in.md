---
UID: NS:hbapiwmi._SM_SendECHO_IN
title: _SM_SendECHO_IN (hbapiwmi.h)
description: The SM_SendECHO_IN structure is used to provide input parameters to the SM_SendECHO method.
old-location: storage\sm_sendecho_in.htm
tech.root: storage
ms.assetid: 0fce2e27-8705-4916-8c75-ecc2845c255c
ms.date: 03/29/2018
ms.keywords: "*PSM_SendECHO_IN, PSM_SendECHO_IN, PSM_SendECHO_IN structure pointer [Storage Devices], SM_SendECHO_IN, SM_SendECHO_IN structure [Storage Devices], _SM_SendECHO_IN, hbapiwmi/PSM_SendECHO_IN, hbapiwmi/SM_SendECHO_IN, storage.sm_sendecho_in, structs-Fibre_b5bcd1e0-9847-4425-8091-6b6dcf7581a0.xml"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- SM_SendECHO_IN
product:
- Windows
targetos: Windows
req.typenames: SM_SendECHO_IN, *PSM_SendECHO_IN
---

# _SM_SendECHO_IN structure


## -description


The SM_SendECHO_IN structure is used to provide input parameters to the SM_SendECHO method.


## -struct-fields




### -field HbaPortWWN

The local HBA port worldwide name (WWN).


### -field DestWWN

The remote HBA port worldwide name (WWN) to which the command will be sent.


### -field DestFCID

The address identifier of the remote port.


### -field InRespBufferMaxSize

The maximum response buffer size.


### -field ReqBufferSize

The request buffer size.


### -field ReqBuffer

The request buffer data.


## -remarks



The WMI tool suite generates a declaration of the SM_SendECHO_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.



