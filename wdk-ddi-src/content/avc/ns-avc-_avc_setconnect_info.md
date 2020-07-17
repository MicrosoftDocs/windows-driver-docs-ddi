---
UID: NS:avc._AVC_SETCONNECT_INFO
title: _AVC_SETCONNECT_INFO (avc.h)
description: The AVC_SETCONNECT_INFO structure is used to initialize a subunit driver and establish pin connections.
old-location: stream\avc_setconnect_info.htm
tech.root: stream
ms.assetid: 16672908-6f1f-471b-b82e-d548e3efeb20
ms.date: 04/23/2018
keywords: ["_AVC_SETCONNECT_INFO structure"]
ms.keywords: "*PAVC_SETCONNECT_INFO, AVC_SETCONNECT_INFO, AVC_SETCONNECT_INFO structure [Streaming Media Devices], PAVC_SETCONNECT_INFO, PAVC_SETCONNECT_INFO structure pointer [Streaming Media Devices], _AVC_SETCONNECT_INFO, avc/AVC_SETCONNECT_INFO, avc/PAVC_SETCONNECT_INFO, avcref_eec9cff7-6ae3-49d3-a649-349b8284630b.xml, stream.avc_setconnect_info"
f1_keywords:
 - "avc/AVC_SETCONNECT_INFO"
 - "AVC_SETCONNECT_INFO"
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
- AVC_SETCONNECT_INFO
product:
- Windows
targetos: Windows
req.typenames: AVC_SETCONNECT_INFO, *PAVC_SETCONNECT_INFO
---

# _AVC_SETCONNECT_INFO structure


## -description


The AVC_SETCONNECT_INFO structure is used to initialize a subunit driver and establish pin connections.


## -struct-fields




### -field PinId

Specifies the offset (or ID) of the pin for which information is to be set.


### -field ConnectInfo

The AVCCONNECTINFO values for the specified pin.


## -remarks



This structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-set-connectinfo">AVC_FUNCTION_SET_CONNECTINFO</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/using-avc-sys">How to Use Avc.sys</a> For information about building and sending an AV/C command.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-set-connectinfo">AVC_FUNCTION_SET_CONNECTINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>
 

 


