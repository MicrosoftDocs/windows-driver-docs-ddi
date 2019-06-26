---
UID: NF:portcls.PcDestroyContent
title: PcDestroyContent function (portcls.h)
description: The PcDestroyContent function deletes a DRM content ID that was created by PcCreateContentMixed. Note that this function call is identical in operation to the DrmDestroyContent function, and its parameter definitions and return value are also identical.
old-location: audio\pcdestroycontent.htm
tech.root: audio
ms.assetid: 742ee83c-3db4-4d77-a79d-28bcc405746d
ms.date: 05/08/2018
ms.keywords: PcDestroyContent, PcDestroyContent function [Audio Devices], audio.pcdestroycontent, audpc-routines_8f5adcf6-89a7-4918-ac2e-78afa45c38c5.xml, portcls/PcDestroyContent
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcDestroyContent
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcDestroyContent function


## -description


The <b>PcDestroyContent</b> function deletes a DRM content ID that was created by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pccreatecontentmixed">PcCreateContentMixed</a>. Note that this function call is identical in operation to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmdestroycontent">DrmDestroyContent</a> function, and its parameter definitions and return value are also identical.


## -parameters




### -param ContentId [in]

Specifies a nonzero DRM content ID assigned to a KS audio stream by <b>DrmCreateContentMixed</b>. Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.


## -returns



See return value definition in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmdestroycontent">DrmDestroyContent</a>.




## -remarks



For more information, see the comments in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmdestroycontent">DrmDestroyContent</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmdestroycontent">DrmDestroyContent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pccreatecontentmixed">PcCreateContentMixed</a>
 

 

