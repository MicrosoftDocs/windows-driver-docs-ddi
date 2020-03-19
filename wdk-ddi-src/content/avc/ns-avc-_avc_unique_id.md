---
UID: NS:avc._AVC_UNIQUE_ID
title: _AVC_UNIQUE_ID (avc.h)
description: The AVC_UNIQUE_ID describe the unique ID of the AV/C unit.
old-location: stream\avc_unique_id.htm
tech.root: stream
ms.assetid: d2a355e2-e5ff-4d20-ae8c-cdee3f5ddb76
ms.date: 04/23/2018
keywords: ["_AVC_UNIQUE_ID structure"]
ms.keywords: "*PAVC_UNIQUE_ID, AVC_UNIQUE_ID, AVC_UNIQUE_ID structure [Streaming Media Devices], PAVC_UNIQUE_ID, PAVC_UNIQUE_ID structure pointer [Streaming Media Devices], _AVC_UNIQUE_ID, avc/AVC_UNIQUE_ID, avc/PAVC_UNIQUE_ID, avcref_c7dadbdc-3227-4462-b2e3-5064e8f96e1a.xml, stream.avc_unique_id"
f1_keywords:
 - "avc/AVC_UNIQUE_ID"
req.header: avc.h
req.include-header: Avc.h
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
- avc.h
api_name:
- AVC_UNIQUE_ID
product:
- Windows
targetos: Windows
req.typenames: AVC_UNIQUE_ID, *PAVC_UNIQUE_ID
---

# _AVC_UNIQUE_ID structure


## -description


The AVC_UNIQUE_ID describe the unique ID of the AV/C unit.


## -struct-fields




### -field DeviceID

A GUID representing the unit as a whole. All subunits within the same unit share the same GUID. No two units share the same GUID.


## -remarks



This structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-unique-id">AVC_FUNCTION_GET_UNIQUE_ID</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/using-avc-sys">How to Use Avc.sys</a> For information about building and sending an AV/C command.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-unique-id">AVC_FUNCTION_GET_UNIQUE_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>
 

 


