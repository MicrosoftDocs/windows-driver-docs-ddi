---
UID: NS:avc._AVC_MULTIFUNC_IRB
title: "_AVC_MULTIFUNC_IRB"
author: windows-driver-content
description: The AVC_MULTIFUNC_IRB structure contains other AV/C related structures in a union.
old-location: stream\avc_multifunc_irb.htm
old-project: stream
ms.assetid: cd8090b1-47d7-4d82-86b3-757b0642c5fe
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: AVC_MULTIFUNC_IRB structure [Streaming Media Devices], PAVC_MULTIFUNC_IRB structure pointer [Streaming Media Devices], avcref_99cf5d79-48d7-4b86-80a7-9de22cc2f29e.xml, AVC_MULTIFUNC_IRB, avc/PAVC_MULTIFUNC_IRB, PAVC_MULTIFUNC_IRB, avc/AVC_MULTIFUNC_IRB, stream.avc_multifunc_irb, _AVC_MULTIFUNC_IRB, *PAVC_MULTIFUNC_IRB
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avc.h
apiname:
-	AVC_MULTIFUNC_IRB
product: Windows
targetos: Windows
req.typenames: AVC_MULTIFUNC_IRB, *PAVC_MULTIFUNC_IRB
---

# _AVC_MULTIFUNC_IRB structure


## -description


The AVC_MULTIFUNC_IRB structure contains other AV/C related structures in a union.


## -syntax


````
typedef struct _AVC_MULTIFUNC_IRB {
  AVC_IRB Common;
  union {
    AVC_PIN_COUNT          PinCount;
    AVC_PIN_DESCRIPTOR     PinDescriptor;
    AVC_PRECONNECT_INFO    PreConnectInfo;
    AVC_SETCONNECT_INFO    SetConnectInfo;
    AVC_PIN_ID             PinId;
    AVC_EXT_PLUG_COUNTS    ExtPlugCounts;
    AVC_UNIQUE_ID          UniqueID;
    AVC_PEER_DO_LOCATOR    PeerLocator;
    AVC_PEER_DO_LIST       PeerList;
    AVC_SUBUNIT_INFO_BLOCK Subunits;
  };
} AVC_MULTIFUNC_IRB, *PAVC_MULTIFUNC_IRB;
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554148">AVC_FUNCTION_ACQUIRE</a>



<a href="..\avc\ns-avc-_avc_unique_id.md">AVC_UNIQUE_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554164">AVC_FUNCTION_GET_SUBUNIT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554168">AVC_FUNCTION_PEER_DO_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554160">AVC_FUNCTION_GET_PIN_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554169">AVC_FUNCTION_RELEASE</a>



<a href="..\avc\ns-avc-_avc_pin_count.md">AVC_PIN_COUNT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554154">AVC_FUNCTION_GET_CONNECTINFO</a>



<a href="..\avc\ns-avc-_avc_pin_id.md">AVC_PIN_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554152">AVC_FUNCTION_FIND_PEER_DO</a>



<a href="..\avc\ns-avc-_avc_ext_plug_counts.md">AVC_EXT_PLUG_COUNTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554166">AVC_FUNCTION_GET_UNIQUE_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554155">AVC_FUNCTION_GET_EXT_PLUG_COUNTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554149">AVC_FUNCTION_CLR_CONNECTINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554158">AVC_FUNCTION_GET_PIN_COUNT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554171">AVC_FUNCTION_SET_CONNECTINFO</a>



<a href="..\avc\ns-avc-_avc_subunit_info_block.md">AVC_SUBUNIT_INFO_BLOCK</a>



<a href="..\avc\ns-avc-_avc_peer_do_locator.md">AVC_PEER_DO_LOCATOR</a>



<a href="..\avc\ns-avc-_avc_preconnect_info.md">AVC_PRECONNECT_INFO</a>



<a href="..\avc\ns-avc-_avc_setconnect_info.md">AVC_SETCONNECT_INFO</a>



<a href="..\avc\ns-avc-_avc_peer_do_list.md">AVC_PEER_DO_LIST</a>



<a href="..\avc\ns-avc-_avc_pin_descriptor.md">AVC_PIN_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_MULTIFUNC_IRB structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

