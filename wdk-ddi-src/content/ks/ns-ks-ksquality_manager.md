---
UID: NS:ks.KSQUALITY_MANAGER
title: KSQUALITY_MANAGER
author: windows-driver-content
description: The KSQUALITY_MANAGER structure is used with the KSPROPERTY_STREAM_QUALITY property and contains the handle of the quality manager sink and a context to pass in the quality complaints.
old-location: stream\ksquality_manager.htm
old-project: stream
ms.assetid: 33e66fa0-53d6-400a-a03b-6d7b3fd01ace
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKSQUALITY_MANAGER, PKSQUALITY_MANAGER structure pointer [Streaming Media Devices], *PKSQUALITY_MANAGER, KSQUALITY_MANAGER, stream.ksquality_manager, ks-struct_97f36a6a-6d00-4cec-b13d-8f039b54c5a8.xml, ks/KSQUALITY_MANAGER, KSQUALITY_MANAGER structure [Streaming Media Devices], ks/PKSQUALITY_MANAGER
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
-	KSQUALITY_MANAGER
product: Windows
targetos: Windows
req.typenames: KSQUALITY_MANAGER, *PKSQUALITY_MANAGER
---

# KSQUALITY_MANAGER structure


## -description


The KSQUALITY_MANAGER structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565750">KSPROPERTY_STREAM_QUALITY</a> property and contains the handle of the quality manager sink and a context to pass in the quality complaints.


## -syntax


````
typedef struct {
  HANDLE QualityManager;
  PVOID  Context;
} KSQUALITY_MANAGER, *PKSQUALITY_MANAGER;
````


## -struct-fields




### -field QualityManager

Specifies a handle to the quality manager sink receiving the <a href="..\ks\ns-ks-ksquality.md">KSQUALITY</a> complaint structures.


### -field Context

Specifies the context parameter to use when reporting quality problems. The context is used by the quality manager to distinguish between various clients that can send complaints to the same file object.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565750">KSPROPERTY_STREAM_QUALITY</a>

<a href="..\ks\ns-ks-ksquality.md">KSQUALITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSQUALITY_MANAGER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

