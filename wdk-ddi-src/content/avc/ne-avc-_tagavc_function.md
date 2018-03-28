---
UID: NE:avc._tagAVC_FUNCTION
title: "_tagAVC_FUNCTION"
author: windows-driver-content
description: The AVC_FUNCTION enumeration type is used to specify AV/C subunit functions.
old-location: stream\avc_function.htm
old-project: stream
ms.assetid: 31451163-bc60-4c84-88a7-e11edea97436
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVC_FUNCTION, AVC_FUNCTION enumeration [Streaming Media Devices], AVC_FUNCTION_ACQUIRE, AVC_FUNCTION_CLR_CONNECTINFO, AVC_FUNCTION_COMMAND, AVC_FUNCTION_FIND_PEER_DO, AVC_FUNCTION_GET_CONNECTINFO, AVC_FUNCTION_GET_EXT_PLUG_COUNTS, AVC_FUNCTION_GET_PIN_COUNT, AVC_FUNCTION_GET_PIN_DESCRIPTOR, AVC_FUNCTION_GET_REQUEST, AVC_FUNCTION_GET_SUBUNIT_INFO, AVC_FUNCTION_GET_UNIQUE_ID, AVC_FUNCTION_PEER_DO_LIST, AVC_FUNCTION_RELEASE, AVC_FUNCTION_SEND_RESPONSE, AVC_FUNCTION_SET_CONNECTINFO, _tagAVC_FUNCTION, avc/AVC_FUNCTION, avc/AVC_FUNCTION_ACQUIRE, avc/AVC_FUNCTION_CLR_CONNECTINFO, avc/AVC_FUNCTION_COMMAND, avc/AVC_FUNCTION_FIND_PEER_DO, avc/AVC_FUNCTION_GET_CONNECTINFO, avc/AVC_FUNCTION_GET_EXT_PLUG_COUNTS, avc/AVC_FUNCTION_GET_PIN_COUNT, avc/AVC_FUNCTION_GET_PIN_DESCRIPTOR, avc/AVC_FUNCTION_GET_REQUEST, avc/AVC_FUNCTION_GET_SUBUNIT_INFO, avc/AVC_FUNCTION_GET_UNIQUE_ID, avc/AVC_FUNCTION_PEER_DO_LIST, avc/AVC_FUNCTION_RELEASE, avc/AVC_FUNCTION_SEND_RESPONSE, avc/AVC_FUNCTION_SET_CONNECTINFO, avcref_aa8add30-67c7-469c-ab3d-9173e7b4b91e.xml, stream.avc_function
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	avc.h
api_name:
-	AVC_FUNCTION
product: Windows
targetos: Windows
req.typenames: AVC_FUNCTION
---

# _tagAVC_FUNCTION enumeration


## -description


The AVC_FUNCTION enumeration type is used to specify AV/C subunit functions.


## -syntax


````
typedef enum _tagAVC_FUNCTION { 
  AVC_FUNCTION_COMMAND              = 0,
  AVC_FUNCTION_GET_PIN_COUNT        = 1,
  AVC_FUNCTION_GET_PIN_DESCRIPTOR   = 2,
  AVC_FUNCTION_GET_CONNECTINFO      = 3,
  AVC_FUNCTION_SET_CONNECTINFO      = 4,
  AVC_FUNCTION_ACQUIRE              = 5,
  AVC_FUNCTION_RELEASE              = 6,
  AVC_FUNCTION_CLR_CONNECTINFO      = 7,
  AVC_FUNCTION_GET_EXT_PLUG_COUNTS  = 8,
  AVC_FUNCTION_GET_UNIQUE_ID        = 9,
  AVC_FUNCTION_GET_REQUEST          = 10,
  AVC_FUNCTION_SEND_RESPONSE        = 11,
  AVC_FUNCTION_FIND_PEER_DO         = 12,
  AVC_FUNCTION_PEER_DO_LIST         = 13,
  AVC_FUNCTION_GET_SUBUNIT_INFO     = 14
} AVC_FUNCTION;
````


## -enum-fields




### -field AVC_FUNCTION_COMMAND

This value is a function code used to send an AV/C request and receive a response as one operation. This function code uses the AVC_COMMAND_IRB structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_PIN_COUNT

This value is a function code used to obtain the number of pins supported by the underlying subunit device. This function code uses the AVC_PIN_COUNT structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_PIN_DESCRIPTOR

This value is a function code used to obtain the pin descriptor for each pin ID. This function code uses the AVC_PIN_DESCRIPTOR structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_CONNECTINFO

This value is a function code used to obtain the AVCPRECONNECTINFO structure for each pin ID. This function code uses the AVC_PRE_CONNECTINFO structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_SET_CONNECTINFO

This value is a function code used to set the AVCCONNECTINFO structure for each pin ID. This function code uses the AVC_SET_CONNECTINFO structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_ACQUIRE

This value is a function code used to cause <i>avc.sys</i> to establish any connections suggested by cached AVCCONNECTINFO values. This function code uses the AVC_PIN_ID structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_RELEASE

This value is a function code used to cause <i>avc.sys</i> to release any connections suggested by cached AVCCONNECTINFO values. This function code uses the AVC_PIN_ID structure.


### -field AVC_FUNCTION_CLR_CONNECTINFO

This value is a function code used to cause <i>avc.sys</i> to remove any cached AVCCONNECTINFO values. This function code uses the AVC_PIN_ID structure. 

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_EXT_PLUG_COUNTS

This value is a function code used to cause <i>avc.sys</i> to obtain the external input and output plug counts. This function code uses the AVC_EXT_PLUG_COUNTS structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_UNIQUE_ID

This value is a function code used to obtain the unique ID of the AV/C unit. This function code uses the AVC_UNIQUE_ID structure.

This function code is available only to peer instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_REQUEST

This value is a function code used to register to receive AV/C unit and subunit requests. This function code uses the AVC_COMMAND_IRB structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_SEND_RESPONSE

This value is a function code used to cause <i>avc.sys</i> to respond to AV/C unit and subunit requests. This function code uses the AVC_COMMAND_IRB structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_FIND_PEER_DO

This value is a function code used to locate a nonvirtual <i>avc.sys</i> instance. This function code uses the AVC_PEER_DO_LOCATOR structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_PEER_DO_LIST

This value is a function code used to locate all nonvirtual <i>avc.sys</i> instances. This function code uses the AVC_PEER_DO_LIST structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


### -field AVC_FUNCTION_GET_SUBUNIT_INFO

This value is a function code used to obtain the subunit information of the target device. This function code uses the AVC_SUBUNIT_INFO_BLOCK structure.

This function code is available to both peer and virtual instances of <i>avc.sys</i>.


## -see-also

<<<<<<< HEAD
<a href="..\avc\ns-avc-_avc_command_irb.md">AVC_COMMAND_IRB</a>



<a href="..\avc\ns-avc-_avc_unique_id.md">AVC_UNIQUE_ID</a>



<a href="..\avc\ns-avc-_avc_setconnect_info.md">AVC_SETCONNECT_INFO</a>
=======
<a href="..\avc\ns-avc-_avc_ext_plug_counts.md">AVC_EXT_PLUG_COUNTS</a>



<a href="..\avc\ns-avc-_avc_peer_do_list.md">AVC_PEER_DO_LIST</a>



<a href="..\avc\ns-avc-_avc_preconnect_info.md">AVC_PRECONNECT_INFO</a>
>>>>>>> 7b6bd3b88106eb7b25c8489b98269eb870735b73



<a href="..\avc\ns-avc-_avc_pin_descriptor.md">AVC_PIN_DESCRIPTOR</a>



<<<<<<< HEAD
<a href="..\avc\ns-avc-_avc_ext_plug_counts.md">AVC_EXT_PLUG_COUNTS</a>



<a href="..\avc\ns-avc-_avc_preconnect_info.md">AVC_PRECONNECT_INFO</a>



<a href="..\avc\ns-avc-_avc_subunit_info_block.md">AVC_SUBUNIT_INFO_BLOCK</a>
=======
<a href="..\avc\ns-avc-_avc_command_irb.md">AVC_COMMAND_IRB</a>



<a href="..\avc\ns-avc-_avc_unique_id.md">AVC_UNIQUE_ID</a>



<a href="..\avc\ns-avc-_avc_pin_id.md">AVC_PIN_ID</a>
>>>>>>> 7b6bd3b88106eb7b25c8489b98269eb870735b73



<a href="..\avc\ns-avc-_avc_pin_count.md">AVC_PIN_COUNT</a>



<<<<<<< HEAD
<a href="..\avc\ns-avc-_avc_peer_do_list.md">AVC_PEER_DO_LIST</a>
=======
<a href="..\avc\ns-avc-_avc_setconnect_info.md">AVC_SETCONNECT_INFO</a>
>>>>>>> 7b6bd3b88106eb7b25c8489b98269eb870735b73



<a href="..\avc\ns-avc-_avc_peer_do_locator.md">AVC_PEER_DO_LOCATOR</a>



<<<<<<< HEAD
<a href="..\avc\ns-avc-_avc_pin_id.md">AVC_PIN_ID</a>
=======
<a href="..\avc\ns-avc-_avc_subunit_info_block.md">AVC_SUBUNIT_INFO_BLOCK</a>
>>>>>>> 7b6bd3b88106eb7b25c8489b98269eb870735b73



<a href="..\avc\ns-avc-_avc_irb.md">AVC_IRB</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_FUNCTION enumeration%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

