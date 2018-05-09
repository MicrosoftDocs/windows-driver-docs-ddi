---
UID: NF:portcls.PcCreateContentMixed
title: PcCreateContentMixed function
author: windows-driver-content
description: The PcCreateContentMixed function computes the DRM content rights for a composite stream containing mixed content from some number of KS audio streams.
old-location: audio\pccreatecontentmixed.htm
old-project: audio
ms.assetid: 9b916d43-26ab-4354-8537-2d4789c5fb52
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PcCreateContentMixed, PcCreateContentMixed function [Audio Devices], audio.pccreatecontentmixed, audpc-routines_40c3dd23-60cb-48dc-a570-1ba007a27bb2.xml, portcls/PcCreateContentMixed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcCreateContentMixed function in Microsoft Windows XP and later operating systems.
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
-	PcCreateContentMixed
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcCreateContentMixed function


## -description


The <b>PcCreateContentMixed</b> function computes the DRM content rights for a composite stream containing mixed content from some number of KS audio streams. Note that this function call is identical in operation to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a> function, and its parameter definitions and return value are also identical.


## -parameters




### -param paContentId [in]

Pointer to an array of DRM content IDs. Each array element is of type ULONG and contains a content ID that represents a protected KS audio stream. If <i>cContentId</i> is zero, <i>paContentID</i> can be <b>NULL</b>. A content ID of zero is a special value that represents an audio stream with default DRM content rights (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536254">DEFINE_DRMRIGHTS_DEFAULT</a>).


### -param cContentId [in]

Specifies the number of DRM content IDs in the <i>paContentId</i> array. The array can hold zero or more content IDs.


### -param pMixedContentId [out]

Output pointer for the composite content ID. This parameter points to a caller-allocated ULONG variable into which the function writes the new content ID for the composite KS audio stream. If <i>cContentId</i> is zero, the function assigns default DRM content rights to the new content ID.


## -returns



See return value definition in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>.




## -remarks



For more information, see the comments in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>
 

 

