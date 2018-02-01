---
UID: NS:avc._AVC_UNIQUE_ID
title: "_AVC_UNIQUE_ID"
author: windows-driver-content
description: The AVC_UNIQUE_ID describe the unique ID of the AV/C unit.
old-location: stream\avc_unique_id.htm
old-project: stream
ms.assetid: d2a355e2-e5ff-4d20-ae8c-cdee3f5ddb76
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PAVC_UNIQUE_ID, stream.avc_unique_id, *PAVC_UNIQUE_ID, _AVC_UNIQUE_ID, AVC_UNIQUE_ID structure [Streaming Media Devices], AVC_UNIQUE_ID, avc/AVC_UNIQUE_ID, avcref_c7dadbdc-3227-4462-b2e3-5064e8f96e1a.xml, avc/PAVC_UNIQUE_ID, PAVC_UNIQUE_ID structure pointer [Streaming Media Devices]
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
-	AVC_UNIQUE_ID
product: Windows
targetos: Windows
req.typenames: "*PAVC_UNIQUE_ID, AVC_UNIQUE_ID"
---

# _AVC_UNIQUE_ID structure


## -description


The AVC_UNIQUE_ID describe the unique ID of the AV/C unit.


## -syntax


````
typedef struct _AVC_UNIQUE_ID {
  GUID DeviceID;
} AVC_UNIQUE_ID, *PAVC_UNIQUE_ID;
````


## -struct-fields




### -field DeviceID

A GUID representing the unit as a whole. All subunits within the same unit share the same GUID. No two units share the same GUID.


## -remarks


This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554166">AVC_FUNCTION_GET_UNIQUE_ID</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.



## -see-also

<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554166">AVC_FUNCTION_GET_UNIQUE_ID</a>

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_UNIQUE_ID structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

