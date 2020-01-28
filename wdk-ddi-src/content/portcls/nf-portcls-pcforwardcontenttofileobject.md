---
UID: NF:portcls.PcForwardContentToFileObject
title: PcForwardContentToFileObject function (portcls.h)
description: The PcForwardContentToFileObject function is obsolete and is maintained only to support existing drivers.
old-location: audio\pcforwardcontenttofileobject.htm
tech.root: audio
ms.assetid: 3cad8e61-e016-415a-9aa9-1169267dc729
ms.date: 05/08/2018
ms.keywords: PcForwardContentToFileObject, PcForwardContentToFileObject function [Audio Devices], audio.pcforwardcontenttofileobject, audpc-routines_2560382f-57c9-4d3c-9ba0-330374e18663.xml, portcls/PcForwardContentToFileObject
f1_keywords:
 - "portcls/PcForwardContentToFileObject"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcForwardContentToFileObject function in Microsoft Windows XP and later operating systems.
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
- PcForwardContentToFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcForwardContentToFileObject function


## -description


The <b>PcForwardContentToFileObject</b> function is obsolete and is maintained only to support existing drivers. Note that this function call is identical in operation to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttofileobject">DrmForwardContentToFileObject</a> function, and its parameter definitions and return value are also identical.


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param FileObject [in]

Pointer to a file object that represents the KS audio pin to which the KS audio stream is sent.


## -returns



See return value definition in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttofileobject">DrmForwardContentToFileObject</a>.




## -remarks



For more information, see the comments in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttofileobject">DrmForwardContentToFileObject</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttofileobject">DrmForwardContentToFileObject</a>
 

 

