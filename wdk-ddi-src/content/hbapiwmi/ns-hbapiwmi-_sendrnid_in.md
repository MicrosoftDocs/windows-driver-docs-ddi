---
UID: NS:hbapiwmi._SendRNID_IN
title: _SendRNID_IN (hbapiwmi.h)
description: The SendRNID_IN structure is used to deliver input parameter data to the SendRNID WMI method.
old-location: storage\sendrnid_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SendRNID_IN structure"]
ms.keywords: "*PSendRNID_IN, PSendRNID_IN, PSendRNID_IN structure pointer [Storage Devices], SendRNID_IN, SendRNID_IN structure [Storage Devices], _SendRNID_IN, hbapiwmi/PSendRNID_IN, hbapiwmi/SendRNID_IN, storage.sendrnid_in, structs-Fibre_506226e9-45f1-40d3-bd41-7b30fe16673e.xml"
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
req.typenames: SendRNID_IN, *PSendRNID_IN
f1_keywords:
 - _SendRNID_IN
 - hbapiwmi/_SendRNID_IN
 - PSendRNID_IN
 - hbapiwmi/PSendRNID_IN
 - SendRNID_IN
 - hbapiwmi/SendRNID_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SendRNID_IN
---

# _SendRNID_IN structure


## -description

The SendRNID_IN structure is used to deliver input parameter data to the <a href="/windows-hardware/drivers/storage/sendrnid">SendRNID</a> WMI method.

## -struct-fields

### -field wwn

Contains a worldwide name for the port to which the request node identification data (RNID) command is sent.

### -field wwntype

Deprecated. Do not use.

## -remarks

The WMI tool suite generates a declaration of the SendRNID_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/sendrnid">SendRNID</a>
