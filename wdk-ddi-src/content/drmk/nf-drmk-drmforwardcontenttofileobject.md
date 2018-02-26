---
UID: NF:drmk.DrmForwardContentToFileObject
title: DrmForwardContentToFileObject function
author: windows-driver-content
description: The DrmForwardContentToFileObject function is obsolete and is maintained only to support existing drivers.
old-location: audio\drmforwardcontenttofileobject.htm
old-project: audio
ms.assetid: 84d81ae3-708d-48ee-99c5-b79f085a9592
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , C, D, DrmForwardContentToFileObject, DrmForwardContentToFileObject function [Audio Devices], F, O, T, a, aud-prop2_f0deebf5-ef63-406b-a424-b084e775333c.xml, audio.drmforwardcontenttofileobject, b, c, d, drmk/DrmForwardContentToFileObject, e, i, j, l, m, n, o, r, t, w"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Drmk.lib
-	Drmk.dll
apiname:
-	DrmForwardContentToFileObject
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---

# DrmForwardContentToFileObject function


## -description


The <code>DrmForwardContentToFileObject</code> function is obsolete and is maintained only to support existing drivers. This function sends the operating system a file object representing a device that handles protected content. It also forwards to the specified device the content ID and associated DRM rights of a stream containing protected content.


## -syntax


````
NTSTATUS DrmForwardContentToFileObject(
  _In_ ULONG        ContentId,
  _In_ PFILE_OBJECT FileObject
);
````


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



This function is superseded by <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>. A driver that calls <code>DrmForwardContentToFileObject</code> forces the system to run at a lower DRM security level. New drivers should call <code>DrmForwardContentToDeviceObject</code> instead.

The <code>DrmForwardContentToFileObject</code> function authenticates the KS audio filter that implements the KS audio pin represented by <i>FileObject</i>. If <code>DrmForwardContentToFileObject</code> successfully authenticates the KS audio filter, it sets the KS property <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a> on the audio pin that is represented by <i>FileObject</i>. The property data includes a DRM content ID and a <a href="..\drmk\ns-drmk-tagdrmrights.md">DRMRIGHTS</a> structure. <code>DrmForwardContentToFileObject</code> makes no use of <i>FileObject</i> after returning.

<code>DrmForwardContentToFileObject</code> performs the same function as <a href="..\portcls\nf-portcls-pcforwardcontenttofileobject.md">PcForwardContentToFileObject</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536584">IDrmPort::ForwardContentToFileObject</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.




## -see-also

<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536584">IDrmPort::ForwardContentToFileObject</a>



<a href="..\drmk\ns-drmk-tagdrmrights.md">DRMRIGHTS</a>



<a href="..\portcls\nf-portcls-pcforwardcontenttofileobject.md">PcForwardContentToFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20DrmForwardContentToFileObject function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

