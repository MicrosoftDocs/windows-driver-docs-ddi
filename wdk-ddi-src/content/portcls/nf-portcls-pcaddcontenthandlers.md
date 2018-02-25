---
UID: NF:portcls.PcAddContentHandlers
title: PcAddContentHandlers function
author: windows-driver-content
description: The PcAddContentHandlers function provides the system with a list of functions that handle protected content.
old-location: audio\pcaddcontenthandlers.htm
old-project: audio
ms.assetid: c3ae9de0-3c21-498b-a29c-4ec54677826a
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , A, C, H, P, PcAddContentHandlers, PcAddContentHandlers function [Audio Devices], a, audio.pcaddcontenthandlers, audpc-routines_11505f52-36d9-4b58-b1f8-44083705f9b5.xml, c, d, e, l, n, o, portcls/PcAddContentHandlers, r, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available starting in Windows XP.
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
req.lib: Portcls.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcAddContentHandlers
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcAddContentHandlers function


## -description


The <b>PcAddContentHandlers</b> function provides the system with a list of functions that handle protected content. Note that this function call is identical in operation to the <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a> function, and its parameter definitions and return value are also identical.


## -syntax


````
PORTCLASSAPI NTSTATUS NTAPI PcAddContentHandlers(
  _In_ ULONG ContentId,
  _In_ PVOID *paHandlers,
  _In_ ULONG NumHandlers
);
````


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param paHandlers [in]

Pointer to an array of function pointers. Each array element points to a content handler.


### -param NumHandlers [in]

Specifies the number of function pointers in the <i>paHandlers</i> array.


## -returns



See return value definition in <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>.




## -remarks



For more information, see the comments in <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>.




## -see-also

<a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcAddContentHandlers function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

