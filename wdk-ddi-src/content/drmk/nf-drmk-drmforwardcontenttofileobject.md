---
UID: NF:drmk.DrmForwardContentToFileObject
title: DrmForwardContentToFileObject function
author: windows-driver-content
description: The DrmForwardContentToFileObject function is obsolete and is maintained only to support existing drivers.
old-location: audio\drmforwardcontenttofileobject.htm
old-project: audio
ms.assetid: 84d81ae3-708d-48ee-99c5-b79f085a9592
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DrmForwardContentToFileObject, DrmForwardContentToFileObject function [Audio Devices], aud-prop2_f0deebf5-ef63-406b-a424-b084e775333c.xml, audio.drmforwardcontenttofileobject, drmk/DrmForwardContentToFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Universal
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
req.lib: Drmk.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Drmk.lib
-	Drmk.dll
api_name:
-	DrmForwardContentToFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# DrmForwardContentToFileObject function


## -description


The <code>DrmForwardContentToFileObject</code> function is obsolete and is maintained only to support existing drivers. This function sends the operating system a file object representing a device that handles protected content. It also forwards to the specified device the content ID and associated DRM rights of a stream containing protected content.


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param FileObject [in]

Pointer to a file object that represents the KS audio pin to which the KS audio stream is sent.


## -returns



<code>DrmForwardContentToFileObject</code> returns STATUS_SUCCESS if the call was successful. The following table shows some of the possible error return values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the KS audio pin that is associated with <i>FileObject</i> does not support the DRM content rights that are assigned to <i>ContentId</i>.

</td>
</tr>
</table>
 




## -remarks



This function is superseded by <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>. A driver that calls <code>DrmForwardContentToFileObject</code> forces the system to run at a lower DRM security level. New drivers should call <code>DrmForwardContentToDeviceObject</code> instead.

The <code>DrmForwardContentToFileObject</code> function authenticates the KS audio filter that implements the KS audio pin represented by <i>FileObject</i>. If <code>DrmForwardContentToFileObject</code> successfully authenticates the KS audio filter, it sets the KS property <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a> on the audio pin that is represented by <i>FileObject</i>. The property data includes a DRM content ID and a <a href="https://msdn.microsoft.com/library/windows/hardware/ff536355">DRMRIGHTS</a> structure. <code>DrmForwardContentToFileObject</code> makes no use of <i>FileObject</i> after returning.

<code>DrmForwardContentToFileObject</code> performs the same function as <a href="https://msdn.microsoft.com/library/windows/hardware/ff537697">PcForwardContentToFileObject</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536584">IDrmPort::ForwardContentToFileObject</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536355">DRMRIGHTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536584">IDrmPort::ForwardContentToFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537697">PcForwardContentToFileObject</a>
 

 

