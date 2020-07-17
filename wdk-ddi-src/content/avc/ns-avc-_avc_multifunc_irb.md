---
UID: NS:avc._AVC_MULTIFUNC_IRB
title: _AVC_MULTIFUNC_IRB (avc.h)
description: The AVC_MULTIFUNC_IRB structure contains other AV/C related structures in a union.
old-location: stream\avc_multifunc_irb.htm
tech.root: stream
ms.assetid: cd8090b1-47d7-4d82-86b3-757b0642c5fe
ms.date: 04/23/2018
keywords: ["_AVC_MULTIFUNC_IRB structure"]
ms.keywords: "*PAVC_MULTIFUNC_IRB, AVC_MULTIFUNC_IRB, AVC_MULTIFUNC_IRB structure [Streaming Media Devices], PAVC_MULTIFUNC_IRB, PAVC_MULTIFUNC_IRB structure pointer [Streaming Media Devices], _AVC_MULTIFUNC_IRB, avc/AVC_MULTIFUNC_IRB, avc/PAVC_MULTIFUNC_IRB, avcref_99cf5d79-48d7-4b86-80a7-9de22cc2f29e.xml, stream.avc_multifunc_irb"
f1_keywords:
 - "avc/AVC_MULTIFUNC_IRB"
 - "AVC_MULTIFUNC_IRB"
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
- AVC_MULTIFUNC_IRB
product:
- Windows
targetos: Windows
req.typenames: AVC_MULTIFUNC_IRB, *PAVC_MULTIFUNC_IRB
---

# _AVC_MULTIFUNC_IRB structure


## -description


The AVC_MULTIFUNC_IRB structure contains other AV/C related structures in a union.


## -struct-fields




### -field Common

 I/O Request Block (IRB) header structure where a function number is stored.


### -field PinCount

Used with AVC_FUNCTION_GET_PIN_COUNT.


### -field PinDescriptor

Used with AVC_FUNCTION_GET_PIN_DESCRIPTOR.


### -field PreConnectInfo

Used with AVC_FUNCTION_GET_CONNECT_INFO.


### -field SetConnectInfo

Used with AVC_FUNCTION_SET_CONNECT_INFO.


### -field PinId

Used with AVC_FUNCTION_ACQUIRE, <b>AVC_FUNCTION_RELEASE</b> and AVC_FUNCTION_CLR_CONNECTINFO.


### -field ExtPlugCounts

Used with AVC_FUNCTION_GET_EXT_PLUG_COUNTS.


### -field UniqueID

Used with AVC_FUNCTION_GET_UNIQUE_ID.


### -field PeerLocator

Used with AVC_FUNCTION_PEER_DO_LOCATOR.


### -field PeerList

Used with AVC_FUNCTION_PEER_DO_LIST.


### -field Subunits

Used with AVC_FUNCTION_GET_SUBUNIT_INFO.


## -remarks



The AVC_MULTIFUNC_IRB structure used with a variety of AV/C functionality. Depending on the functionality described in the AVC_IRB header, the matching, respective structure in the union is used.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_ext_plug_counts">AVC_EXT_PLUG_COUNTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-acquire">AVC_FUNCTION_ACQUIRE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-clr-connectinfo">AVC_FUNCTION_CLR_CONNECTINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-find-peer-do">AVC_FUNCTION_FIND_PEER_DO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-connectinfo">AVC_FUNCTION_GET_CONNECTINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-ext-plug-counts">AVC_FUNCTION_GET_EXT_PLUG_COUNTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-pin-count">AVC_FUNCTION_GET_PIN_COUNT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-pin-descriptor">AVC_FUNCTION_GET_PIN_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-subunit-info">AVC_FUNCTION_GET_SUBUNIT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-unique-id">AVC_FUNCTION_GET_UNIQUE_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-peer-do-list">AVC_FUNCTION_PEER_DO_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-release">AVC_FUNCTION_RELEASE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-set-connectinfo">AVC_FUNCTION_SET_CONNECTINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_peer_do_list">AVC_PEER_DO_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_peer_do_locator">AVC_PEER_DO_LOCATOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_pin_count">AVC_PIN_COUNT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_pin_descriptor">AVC_PIN_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_pin_id">AVC_PIN_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_preconnect_info">AVC_PRECONNECT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_setconnect_info">AVC_SETCONNECT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_subunit_info_block">AVC_SUBUNIT_INFO_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_unique_id">AVC_UNIQUE_ID</a>
 

 


