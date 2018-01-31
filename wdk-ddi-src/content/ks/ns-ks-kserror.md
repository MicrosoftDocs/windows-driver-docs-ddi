---
UID: NS:ks.KSERROR
title: KSERROR
author: windows-driver-content
description: The KSERROR structure is used to report streaming errors in both kernel and user mode to their respective quality managers.
old-location: stream\kserror.htm
old-project: stream
ms.assetid: c475810c-505e-446a-9b98-d512e745b6ce
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks-struct_86211cee-a711-4a84-b8ea-6de2d9ef81f6.xml, stream.kserror, PKSERROR structure pointer [Streaming Media Devices], KSERROR, PKSERROR, ks/KSERROR, *PKSERROR, ks/PKSERROR, KSERROR structure [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSERROR
product: Windows
targetos: Windows
req.typenames: "*PKSERROR, KSERROR"
---

# KSERROR structure


## -description


The KSERROR structure is used to report streaming errors in both kernel and user mode to their respective quality managers.


## -syntax


````
typedef struct {
  PVOID Context;
  ULONG Status;
} KSERROR, *PKSERROR;
````


## -struct-fields




#### - Context

Specifies a context parameter that was originally passed to the connection.


#### - Status

Specifies the NTSTATUS error.


## -remarks


Streaming error notifications can be generated against the Quality Management sink, if assigned. The same method of proxying Quality Management complaints is used for forwarding error reports for DirectShow graphs. For more information, see <a href="https://msdn.microsoft.com/359e6e12-903f-4037-8f35-b090ce41f770">Quality Management</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565211">KSPROPERTY_QUALITY_ERROR</a>

<a href="..\ks\ns-ks-ksidentifier.md">KSDEGRADE</a>

<a href="..\ks\ne-ks-ksdegrade_standard.md">KSDEGRADE_STANDARD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSERROR structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

