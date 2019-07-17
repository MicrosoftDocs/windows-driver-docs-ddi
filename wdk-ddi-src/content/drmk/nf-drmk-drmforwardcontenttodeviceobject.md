---
UID: NF:drmk.DrmForwardContentToDeviceObject
title: DrmForwardContentToDeviceObject function (drmk.h)
description: The DrmForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content.
old-location: audio\drmforwardcontenttodeviceobject.htm
tech.root: audio
ms.assetid: 1ce67fb6-190e-4de2-9877-f06cd08cf424
ms.date: 05/08/2018
ms.keywords: DrmForwardContentToDeviceObject, DrmForwardContentToDeviceObject function [Audio Devices], aud-prop2_45870b55-07dc-48bf-a8ff-8005a7791dc1.xml, audio.drmforwardcontenttodeviceobject, drmk/DrmForwardContentToDeviceObject
ms.topic: function
f1_keywords:
 - "drmk/DrmForwardContentToDeviceObject"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Drmk.lib
- Drmk.dll
api_name:
- DrmForwardContentToDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrmForwardContentToDeviceObject function


## -description


The <code>DrmForwardContentToDeviceObject</code> function accepts a device object representing a device to which the caller intends to forward protected content. The function authenticates the device and sends it the content ID and DRM rights that the system has assigned to the protected content.


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param Reserved [in, optional]

Reserved for future use. Set to <b>NULL</b>.


### -param DrmForward [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/ns-drmk-tagdrmforward">DRMFORWARD</a> structure specifying a device object and file object that identify the target device and a KS audio pin on that device, respectively. The structure also contains the context value that the <a href="https://docs.microsoft.com/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request passes to the device.


## -returns



<code>DrmForwardContentToDeviceObject</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



Before allowing protected content to flow through a data path, the system verifies that the data path is secure. To do so, the system authenticates each module in the data path beginning at the upstream end of the data path and moving downstream. As each module is authenticated, that module gives the system information about the next module in the data path so that it can also be authenticated. To be successfully authenticated, a module's binary file must be signed as DRM-compliant.

Two adjacent modules in the data path can communicate with each other in one of several ways. If the upstream module calls the downstream module through <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocalldriver">IoCallDriver</a>, the downstream module is part of a WDM driver. In this case, the upstream module calls the <code>DrmForwardContentToDeviceObject</code> function to provide the system with the device object representing the downstream module. (If the two modules communicate through the downstream module's COM interface or content handlers, the upstream module calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmaddcontenthandlers">DrmAddContentHandlers</a> instead.)

The caller fills in the <b>DeviceObject</b>, <b>FileObject</b>, and <b>Context</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/ns-drmk-tagdrmforward">DRMFORWARD</a> structure that parameter <i>DrmForward</i> points to. <code>DrmForwardContentToDeviceObject</code> uses these values as follows:

<ul>
<li>
<b>DeviceObject</b> specifies the device object that represents the driver (the downstream module). <code>DrmForwardContentToDeviceObject</code> uses the device object to authenticate the driver. If successful, the function sets the <a href="https://docs.microsoft.com/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a> property on the device by sending a set-property request to a KS pin on the device.

</li>
<li>
<b>FileObject</b> specifies the KS pin to which <code>DrmForwardContentToDeviceObject</code> sends the property request.

</li>
<li>
<b>Context</b> specifies a context value that the caller passes to the driver through the property request. <code>DrmForwardContentToDeviceObject</code> copies the context value into the request's property descriptor. The context value is typically a pointer to a buffer containing data in some custom format that both the caller and driver understand. By convention, if the downstream module is a KS filter, the <b>Context</b> member points to a file object that specifies the KS pin to which the <code>DrmForwardContentToDeviceObject</code> function sends the property request. In other words, the <b>Context</b> member points to the same file object as the <b>FileObject</b> member. USB audio drivers must set the <b>Context</b> parameter to a USBD_PIPE_HANDLE value.

</li>
</ul>
The property request also contains the DRM content ID from parameter <i>ContentId</i> and the DRM content rights belonging to that content ID. <code>DrmForwardContentToDeviceObject</code> copies these values into the request's property value. <code>DrmForwardContentToDeviceObject</code> makes no further use of the device object after returning.

<code>DrmForwardContentToDeviceObject</code> performs the same function as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcforwardcontenttodeviceobject">PcForwardContentToDeviceObject</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-idrmport2-forwardcontenttodeviceobject">IDrmPort2::ForwardContentToDeviceObject</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/drm-functions-and-interfaces">DRM Functions and Interfaces</a>.

The KSPROPERTY_DRMAUDIOSTREAM_CONTENTID property assigns the DRM content ID and DRM content rights to a KS audio pin.

<h3><a id="ddk_ksproperty_drmaudiostream_contentid_ks"></a><a id="DDK_KSPROPERTY_DRMAUDIOSTREAM_CONTENTID_KS"></a></h3>
<h3><a id="Usage_Summary_Table"></a><a id="usage_summary_table"></a><a id="USAGE_SUMMARY_TABLE"></a>Usage Summary Table</h3>
<table>
<tr>
<th>Get</th>
<th>Set</th>
<th>Target</th>
<th>Property descriptor type</th>
<th>Property value type</th>
</tr>
<tr>
<td>
No

</td>
<td>
Yes

</td>
<td>
Pin

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/ns-drmk-ksp_drmaudiostream_contentid">KSP_DRMAUDIOSTREAM_CONTENTID</a>


</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/ns-drmk-ksdrmaudiostream_contentid">KSDRMAUDIOSTREAM_CONTENTID</a>


</td>
</tr>
</table>
 

The property value (operation data) is a KSDRMAUDIOSTREAM_CONTENTID structure that specifies the stream's DRM content ID and DRM content rights.

<h3><a id="Return_Value"></a><a id="return_value"></a><a id="RETURN_VALUE"></a>Return Value</h3>
A KSPROPERTY_DRMAUDIOSTREAM_CONTENTID property request returns a status code that indicates whether the KS filter can enforce the specified DRM content rights, as shown in the following table.

<table>
<tr>
<th>Status Code</th>
<th>Meaning</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The KS audio filter enforces the specified DRM content rights.

</td>
</tr>
<tr>
<td>
STATUS_NOT_IMPLEMENTED

</td>
<td>
The KS filter cannot enforce the specified DRM content rights.

</td>
</tr>
</table>
 

The <b>DrmForwardContentToDeviceObject</b> function uses this property to set the DRM content ID and content rights on the audio stream entering the KS pin that is the target of the property request.

A KS audio filter handles this property request synchronously. If the request returns STATUS_SUCCESS, all the downstream KS audio nodes (see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-topology-nodes">Audio Topology Nodes</a>) of the target KS audio pin were also successfully configured with the specified DRM content ID and DRM content rights. (Note that a downstream node is a direct or indirect sink for the audio content flowing through an audio pin.)

The DRM system can set this property at any time during the lifetime of the file object that represents a KS audio pin. If the request does not succeed, the previously set DRM content ID and DRM content rights remain in effect on the KS audio stream.

The handler for the KSPROPERTY_DRMAUDIOSTREAM_CONTENTID property must verify that the property-request IRP originates in kernel mode (that is, confirm that the IRP's <b>RequestorMode</b> field equals <b>KernelMode</b>). If the IRP originates in user mode, the handler must fail the IRP and return status code INVALID_DEVICE_REQUEST.

<b>DrmForwardContentToDeviceObject</b> is an entry point in the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/kernel-mode-wdm-audio-components">DRMK system driver</a>, Drmk.sys. DRMK sends an IOCTL_KS_PROPERTY request for the KSPROPERTY_DRMAUDIOSTREAM_CONTENTID property at IRQL PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/ns-drmk-tagdrmforward">DRMFORWARD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmaddcontenthandlers">DrmAddContentHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-idrmport2-forwardcontenttodeviceobject">IDrmPort2::ForwardContentToDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="https://docs.microsoft.com/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcforwardcontenttodeviceobject">PcForwardContentToDeviceObject</a>
 

 

