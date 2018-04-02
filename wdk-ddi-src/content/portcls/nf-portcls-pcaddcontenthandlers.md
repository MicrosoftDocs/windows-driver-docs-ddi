---
UID: NF:portcls.PcAddContentHandlers
title: PcAddContentHandlers function
author: windows-driver-content
description: The PcAddContentHandlers function provides the system with a list of functions that handle protected content.
old-location: audio\pcaddcontenthandlers.htm
old-project: audio
ms.assetid: c3ae9de0-3c21-498b-a29c-4ec54677826a
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PcAddContentHandlers, PcAddContentHandlers function [Audio Devices], audio.pcaddcontenthandlers, audpc-routines_11505f52-36d9-4b58-b1f8-44083705f9b5.xml, portcls/PcAddContentHandlers
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcAddContentHandlers
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcAddContentHandlers function


## -description


The <b>PcAddContentHandlers</b> function provides the system with a list of functions that handle protected content. Note that this function call is identical in operation to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a> function, and its parameter definitions and return value are also identical.


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param paHandlers [in]

Pointer to an array of function pointers. Each array element points to a content handler.


### -param NumHandlers [in]

Specifies the number of function pointers in the <i>paHandlers</i> array.


## -returns



See return value definition in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>.




## -remarks



For more information, see the comments in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>
 

 

