---
UID: NF:portcls.PcDestroyContent
title: PcDestroyContent function
author: windows-driver-content
description: The PcDestroyContent function deletes a DRM content ID that was created by PcCreateContentMixed. Note that this function call is identical in operation to the DrmDestroyContent function, and its parameter definitions and return value are also identical.
old-location: audio\pcdestroycontent.htm
old-project: audio
ms.assetid: 742ee83c-3db4-4d77-a79d-28bcc405746d
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: portcls/PcDestroyContent, audpc-routines_8f5adcf6-89a7-4918-ac2e-78afa45c38c5.xml, PcDestroyContent, PcDestroyContent function [Audio Devices], audio.pcdestroycontent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcDestroyContent function in Microsoft Windows XP and later operating systems.
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
-	PcDestroyContent
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# PcDestroyContent function


## -description


The <b>PcDestroyContent</b> function deletes a DRM content ID that was created by <a href="..\portcls\nf-portcls-pccreatecontentmixed.md">PcCreateContentMixed</a>. Note that this function call is identical in operation to the <a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a> function, and its parameter definitions and return value are also identical.


## -syntax


````
PORTCLASSAPI NTSTATUS NTAPI  PcDestroyContent(void);
````


## -parameters




### -param ContentId

TBD




## -returns



See return value definition in <a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a>.




## -remarks



For more information, see the comments in <a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a>.




## -see-also

<a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a>



<a href="..\portcls\nf-portcls-pccreatecontentmixed.md">PcCreateContentMixed</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcDestroyContent function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

