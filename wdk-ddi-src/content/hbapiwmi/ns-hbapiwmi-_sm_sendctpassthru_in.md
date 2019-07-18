---
UID: NS:hbapiwmi._SM_SendCTPassThru_IN
title: _SM_SendCTPassThru_IN (hbapiwmi.h)
description: The SM_SendCTPassThru_IN structure is used to provide input parameters to the SM_SendCTPassThru method.
old-location: storage\sm_sendctpassthru_in.htm
tech.root: storage
ms.assetid: a6dfb1a2-bfc2-4117-8a4e-f52979818289
ms.date: 03/29/2018
ms.keywords: "*PSM_SendCTPassThru_IN, PSM_SendCTPassThru_IN, PSM_SendCTPassThru_IN structure pointer [Storage Devices], SM_SendCTPassThru_IN, SM_SendCTPassThru_IN structure [Storage Devices], _SM_SendCTPassThru_IN, hbapiwmi/PSM_SendCTPassThru_IN, hbapiwmi/SM_SendCTPassThru_IN, storage.sm_sendctpassthru_in, structs-Fibre_87514826-5f0e-4b59-a514-a4e14f60c4bb.xml"
ms.topic: struct
f1_keywords:
 - "hbapiwmi/SM_SendCTPassThru_IN"
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
- SM_SendCTPassThru_IN
product:
- Windows
targetos: Windows
req.typenames: SM_SendCTPassThru_IN, *PSM_SendCTPassThru_IN
---

# _SM_SendCTPassThru_IN structure


## -description


The SM_SendCTPassThru_IN structure is used to provide input parameters to the SM_SendCTPassThru method.


## -struct-fields




### -field HbaPortWWN

The HBA port worldwide name (WWN) to which pass-through commands will be sent.


### -field InRespBufferMaxSize

The maximum response buffer size.


### -field ReqBufferSize

The size, in bytes, of the buffer that will hold the results of the common transport command.


### -field ReqBuffer


## -remarks



The WMI tool suite generates a declaration of the SM_SendCTPassThru_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.



