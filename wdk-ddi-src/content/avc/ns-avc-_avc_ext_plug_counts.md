---
UID: NS:avc._AVC_EXT_PLUG_COUNTS
title: "_AVC_EXT_PLUG_COUNTS"
author: windows-driver-content
description: The AVC_EXT_PLUG_COUNTS structure describes the number of external plugs on the subunit.
old-location: stream\avc_ext_plug_counts.htm
old-project: stream
ms.assetid: ffae774e-8ec9-49da-bdc6-b56beb45c4c0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: AVC_EXT_PLUG_COUNTS, AVC_EXT_PLUG_COUNTS structure [Streaming Media Devices], PAVC_EXT_PLUG_COUNTS structure pointer [Streaming Media Devices], *PAVC_EXT_PLUG_COUNTS, avcref_171f4765-bb9f-4056-a238-d4822af50a3d.xml, avc/PAVC_EXT_PLUG_COUNTS, _AVC_EXT_PLUG_COUNTS, stream.avc_ext_plug_counts, PAVC_EXT_PLUG_COUNTS, avc/AVC_EXT_PLUG_COUNTS
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
-	AVC_EXT_PLUG_COUNTS
product: Windows
targetos: Windows
req.typenames: "*PAVC_EXT_PLUG_COUNTS, AVC_EXT_PLUG_COUNTS"
---

# _AVC_EXT_PLUG_COUNTS structure


## -description


The AVC_EXT_PLUG_COUNTS structure describes the number of external plugs on the subunit.


## -syntax


````
typedef struct _AVC_EXT_PLUG_COUNTS {
  ULONG ExtInputs;
  ULONG ExtOutputs;
} AVC_EXT_PLUG_COUNTS, *PAVC_EXT_PLUG_COUNTS;
````


## -struct-fields




### -field ExtInputs

Ignored on input. On output, this contains the count of external input plugs.


### -field ExtOutputs

Ignored on input. On output, this contains the count of external output plugs.


## -remarks


This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554155">AVC_FUNCTION_GET_EXT_PLUG_COUNTS</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554155">AVC_FUNCTION_GET_EXT_PLUG_COUNTS</a>

<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_EXT_PLUG_COUNTS structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

