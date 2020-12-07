---
UID: NS:hbapiwmi._SM_SendTEST_IN
title: _SM_SendTEST_IN (hbapiwmi.h)
description: The SM_SendTEST_IN structure is used to provide input parameters to the SM_SendTEST method.
old-location: storage\sm_sendtest_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SM_SendTEST_IN structure"]
ms.keywords: "*PSM_SendTEST_IN, PSM_SendTEST_IN, PSM_SendTEST_IN structure pointer [Storage Devices], SM_SendTEST_IN, SM_SendTEST_IN structure [Storage Devices], _SM_SendTEST_IN, hbapiwmi/PSM_SendTEST_IN, hbapiwmi/SM_SendTEST_IN, storage.sm_sendtest_in, structs-Fibre_6d12c9e2-88bd-4803-893a-bb4e54604fad.xml"
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
targetos: Windows
req.typenames: SM_SendTEST_IN, *PSM_SendTEST_IN
f1_keywords:
 - _SM_SendTEST_IN
 - hbapiwmi/_SM_SendTEST_IN
 - PSM_SendTEST_IN
 - hbapiwmi/PSM_SendTEST_IN
 - SM_SendTEST_IN
 - hbapiwmi/SM_SendTEST_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SM_SendTEST_IN
---

# _SM_SendTEST_IN structure


## -description

The SM_SendTEST_IN structure is used to provide input parameters to the SM_SendTEST method.

## -struct-fields

### -field HbaPortWWN

The local HBA port worldwide name (WWN).

### -field DestWWN

The remote HBA port worldwide name (WWN) to which the command will be sent.

### -field DestFCID

The address identifier of the remote port.

### -field ReqBufferSize

The request buffer size.

### -field ReqBuffer

The request buffer data.

## -remarks

The WMI tool suite generates a declaration of the SM_SendTEST_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.

