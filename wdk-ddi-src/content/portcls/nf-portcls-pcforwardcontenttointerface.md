---
UID: NF:portcls.PcForwardContentToInterface
title: PcForwardContentToInterface function (portcls.h)
description: The PcForwardContentToInterface function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content.
old-location: audio\pcforwardcontenttointerface.htm
tech.root: audio
ms.assetid: 5aa6aa90-ef41-467e-a096-5ab660b3f357
ms.date: 05/08/2018
ms.keywords: PcForwardContentToInterface, PcForwardContentToInterface function [Audio Devices], audio.pcforwardcontenttointerface, audpc-routines_1c3b8e8d-556e-4029-9e25-5a2e083dd17f.xml, portcls/PcForwardContentToInterface
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcForwardContentToInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcForwardContentToInterface function


## -description


The <b>PcForwardContentToInterface</b> function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. Note that this function call is identical in operation to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a> function, and its parameter definitions and return value are also identical.


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param pUnknown [in]

Pointer to a COM interface that directly receives KS audio stream data for a KS audio filter.


### -param NumMethods [in]

Specifies the total number of methods in the COM interface that <i>pUnknown</i> points to, including all the methods in its base interfaces.


## -returns



See return value definition in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a>.




## -remarks



For more information, see the comments in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a>
 

 

