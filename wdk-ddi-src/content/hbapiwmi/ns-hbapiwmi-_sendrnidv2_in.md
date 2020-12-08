---
UID: NS:hbapiwmi._SendRNIDV2_IN
title: _SendRNIDV2_IN (hbapiwmi.h)
description: The SendRNIDV2_IN structure is used to deliver input parameter data to the SendRNIDV2 WMI method.
old-location: storage\sendrnidv2_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SendRNIDV2_IN structure"]
ms.keywords: "*PSendRNIDV2_IN, PSendRNIDV2_IN, PSendRNIDV2_IN structure pointer [Storage Devices], SendRNIDV2_IN, SendRNIDV2_IN structure [Storage Devices], _SendRNIDV2_IN, hbapiwmi/PSendRNIDV2_IN, hbapiwmi/SendRNIDV2_IN, storage.sendrnidv2_in, structs-Fibre_5411860d-c8c8-4f4d-b4cc-751973c3d02e.xml"
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
req.typenames: SendRNIDV2_IN, *PSendRNIDV2_IN
f1_keywords:
 - _SendRNIDV2_IN
 - hbapiwmi/_SendRNIDV2_IN
 - PSendRNIDV2_IN
 - hbapiwmi/PSendRNIDV2_IN
 - SendRNIDV2_IN
 - hbapiwmi/SendRNIDV2_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SendRNIDV2_IN
---

# _SendRNIDV2_IN structure


## -description

The SendRNIDV2_IN structure is used to deliver input parameter data to the <a href="/windows-hardware/drivers/storage/sendrnidv2">SendRNIDV2</a> WMI method.

## -struct-fields

### -field PortWWN

Contains a worldwide name for the local port through which the version 2 request node identification data (RNIDV2) command is sent.

### -field DestWWN

Contains a worldwide name for the destination port.

### -field DestFCID

Contains an address identifier of the destination port. For a description of the values that this member can have, see the T11 committee's specification for <i>Fibre Channel HBA API</i>.

### -field NodeIdDataFormat

Indicates the node identification data format. For a description of the values that this member can have, see the T11 committee's specification for <i>Fibre Channel HBA API</i>.

## -remarks

The WMI tool suite generates a declaration of the SendRNIDV2_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/sendrnidv2">SendRNIDV2</a>
