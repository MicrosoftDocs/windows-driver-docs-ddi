---
UID: NS:avc._AVC_PRECONNECT_INFO
title: _AVC_PRECONNECT_INFO (avc.h)
description: The AVC_PRECONNECT_INFO structure specifies the preconnection information for the specified pin ID (zero-based offset) on an AV/C subunit device.
old-location: stream\avc_preconnect_info.htm
tech.root: stream
ms.assetid: 823713de-16d4-45cd-936e-1af4a8425c94
ms.date: 04/23/2018
keywords: ["AVC_PRECONNECT_INFO structure"]
ms.keywords: "*PAVC_PRECONNECT_INFO, AVC_PRECONNECT_INFO, AVC_PRECONNECT_INFO structure [Streaming Media Devices], PAVC_PRECONNECT_INFO, PAVC_PRECONNECT_INFO structure pointer [Streaming Media Devices], _AVC_PRECONNECT_INFO, avc/AVC_PRECONNECT_INFO, avc/PAVC_PRECONNECT_INFO, avcref_86ee1545-848a-4186-9b6a-bee1c689fa68.xml, stream.avc_preconnect_info"
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
targetos: Windows
req.typenames: AVC_PRECONNECT_INFO, *PAVC_PRECONNECT_INFO
f1_keywords:
 - _AVC_PRECONNECT_INFO
 - avc/_AVC_PRECONNECT_INFO
 - PAVC_PRECONNECT_INFO
 - avc/PAVC_PRECONNECT_INFO
 - AVC_PRECONNECT_INFO
 - avc/AVC_PRECONNECT_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avc.h
api_name:
 - AVC_PRECONNECT_INFO
---

# _AVC_PRECONNECT_INFO structure


## -description

The AVC_PRECONNECT_INFO structure specifies the preconnection information for the specified pin ID (zero-based offset) on an AV/C subunit device.

## -struct-fields

### -field PinId

Specifies the offset (or ID) of the pin for which information is to be retrieved.

### -field ConnectInfo

The AVCPRECONNECTINFO values for the specified pin.

## -remarks

This structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-connectinfo">AVC_FUNCTION_GET_CONNECTINFO</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/using-avc-sys">How to Use Avc.sys</a> for information about building and sending an AV/C command.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-connectinfo">AVC_FUNCTION_GET_CONNECTINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>

