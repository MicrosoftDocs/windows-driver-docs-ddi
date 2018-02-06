---
UID: NS:avc._AVC_SUBUNIT_INFO_BLOCK
title: "_AVC_SUBUNIT_INFO_BLOCK"
author: windows-driver-content
description: The AVC_SUBUNIT_INFO_BLOCK structure describes subunit information.
old-location: stream\avc_subunit_info_block.htm
old-project: stream
ms.assetid: 66231303-20ec-42d4-b61d-c8e85e4e6a88
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PAVC_SUBUNIT_INFO_BLOCK structure pointer [Streaming Media Devices], avc/AVC_SUBUNIT_INFO_BLOCK, stream.avc_subunit_info_block, avc/PAVC_SUBUNIT_INFO_BLOCK, PAVC_SUBUNIT_INFO_BLOCK, AVC_SUBUNIT_INFO_BLOCK structure [Streaming Media Devices], avcref_d8151f14-0fc4-4be5-b815-d94dc77165db.xml, *PAVC_SUBUNIT_INFO_BLOCK, AVC_SUBUNIT_INFO_BLOCK, _AVC_SUBUNIT_INFO_BLOCK
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
-	AVC_SUBUNIT_INFO_BLOCK
product: Windows
targetos: Windows
req.typenames: "*PAVC_SUBUNIT_INFO_BLOCK, AVC_SUBUNIT_INFO_BLOCK"
---

# _AVC_SUBUNIT_INFO_BLOCK structure


## -description


The AVC_SUBUNIT_INFO_BLOCK structure describes subunit information.


## -syntax


````
typedef struct _AVC_SUBUNIT_INFO_BLOCK {
  UCHAR Info[AVC_SUBUNITINFO_BYTES];
} AVC_SUBUNIT_INFO_BLOCK, *PAVC_SUBUNIT_INFO_BLOCK;
````


## -struct-fields




### -field Info

Ignored on input. On output, this contains up to eight contiguous pages of subunit information in the format of the AV/C SUBUNIT_INFO unit command. The subunit information pages are terminated with 0xff. See Section 9.11 of the AV/C Digital Interface Command Set General Specification, Rev 3.0. This specification can be found at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8728">1394 Trade Association</a> website.


## -remarks


This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554164">AVC_FUNCTION_GET_SUBUNIT_INFO</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.



## -see-also

<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554164">AVC_FUNCTION_GET_SUBUNIT_INFO</a>

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_SUBUNIT_INFO_BLOCK structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

