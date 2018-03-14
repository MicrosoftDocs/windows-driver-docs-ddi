---
UID: NF:portcls.PcForwardContentToInterface
title: PcForwardContentToInterface function
author: windows-driver-content
description: The PcForwardContentToInterface function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content.
old-location: audio\pcforwardcontenttointerface.htm
old-project: audio
ms.assetid: 5aa6aa90-ef41-467e-a096-5ab660b3f357
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PcForwardContentToInterface, PcForwardContentToInterface function [Audio Devices], audio.pcforwardcontenttointerface, audpc-routines_1c3b8e8d-556e-4029-9e25-5a2e083dd17f.xml, portcls/PcForwardContentToInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcForwardContentToInterface function in Microsoft Windows XP and later operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcForwardContentToInterface
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcForwardContentToInterface function


## -description


The <b>PcForwardContentToInterface</b> function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. Note that this function call is identical in operation to the <a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a> function, and its parameter definitions and return value are also identical.


## -syntax


````
PORTCLASSAPI NTSTATUS NTAPI  PcForwardContentToInterface(
  _In_ ULONG    ContentId,
  _In_ PUNKNOWN pUnknown,
  _In_ ULONG    NumMethods
);
````


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param pUnknown [in]

Pointer to a COM interface that directly receives KS audio stream data for a KS audio filter.


### -param NumMethods [in]

Specifies the total number of methods in the COM interface that <i>pUnknown</i> points to, including all the methods in its base interfaces.


## -returns



See return value definition in <a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>.




## -remarks



For more information, see the comments in <a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>.




## -see-also

<a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcForwardContentToInterface function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

