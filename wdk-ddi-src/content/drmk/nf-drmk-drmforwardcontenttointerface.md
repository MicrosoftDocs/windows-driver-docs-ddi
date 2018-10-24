---
UID: NF:drmk.DrmForwardContentToInterface
title: DrmForwardContentToInterface function
author: windows-driver-content
description: The DrmForwardContentToInterface function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content.
old-location: audio\drmforwardcontenttointerface.htm
tech.root: audio
ms.assetid: 13326eae-3160-42e5-9254-089c8cdc97a3
ms.date: 05/08/2018
ms.keywords: DrmForwardContentToInterface, DrmForwardContentToInterface function [Audio Devices], aud-prop2_c065f793-db14-4fc9-8804-f6d86754e106.xml, audio.drmforwardcontenttointerface, drmk/DrmForwardContentToInterface
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
-	DrmForwardContentToInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrmForwardContentToInterface function


## -description


The <code>DrmForwardContentToInterface</code> function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. The function authenticates the object and sends the object the content ID and DRM rights that the system has assigned to the protected content.


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param pUnknown [in]

Pointer to a COM interface that directly receives KS audio stream data for a KS audio filter.


### -param NumMethods [in]

Specifies the total number of methods in the COM interface that <i>pUnknown</i> points to, including all the methods in its base interfaces.


## -returns



<code>DrmForwardContentToInterface</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.

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
Indicates that the KS audio stream that is associated with <i>pUnknown</i> does not support the DRM content rights that are assigned to <i>ContentId</i>.

</td>
</tr>
</table>
 




## -remarks



Before allowing protected content to flow through a data path, the system verifies that the data path is secure. To do so, the system authenticates each module in the data path beginning at the upstream end of the data path and moving downstream. As each module is authenticated, that module gives the system information about the next module in the data path so that it can also be authenticated. To be successfully authenticated, a module's binary file must be signed as DRM-compliant.

If two adjacent modules in the data path communicate with each other through the downstream module's COM interface, the upstream module calls the <code>DrmForwardContentToInterface</code> function to provide the system with a pointer to the COM interface. (If the two modules communicate through the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a> function or the downstream module's content handlers, the upstream module calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a> instead.)

<code>DrmForwardContentToInterface</code> authenticates the module that implements the methods in the COM interface pointed to by <i>pUnknown</i>. (If the methods are distributed among several modules, the function authenticates all these modules.) This vendor-defined interface must be understood by both the module that calls the interface and the module that implements the interface. <code>DrmForwardContentToInterface</code> makes no assumptions regarding this interface other than that it is derived from <b>IUnknown</b>.

If <code>DrmForwardContentToInterface</code> succeeds in authenticating the driver or library, it does the following:

<ul>
<li>
Queries the <i>pUnknown</i> interface for its <a href="https://msdn.microsoft.com/library/windows/hardware/ff536568">IDrmAudioStream</a> interface. Note that although the <code>DrmForwardContentToInterface</code> authenticates all the methods in the <i>pUnknown</i> interface, it does not call any methods in the <i>pUnknown</i> interface other than the base <b>IUnknown</b> methods.

</li>
<li>
Calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff536570">IDrmAudioStream::SetContentId</a> to set the DRM content ID and DRM content rights on the audio stream. Before returning, <code>DrmForwardContentToInterface</code> releases the <b>IDrmAudioStream</b> interface.

</li>
</ul>
The <i>pUnknown</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.

<code>DrmForwardContentToInterface</code> performs the same function as <a href="https://msdn.microsoft.com/library/windows/hardware/ff537698">PcForwardContentToInterface</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536586">IDrmPort::ForwardContentToInterface</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536568">IDrmAudioStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536570">IDrmAudioStream::SetContentId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536586">IDrmPort::ForwardContentToInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537698">PcForwardContentToInterface</a>
 

 

