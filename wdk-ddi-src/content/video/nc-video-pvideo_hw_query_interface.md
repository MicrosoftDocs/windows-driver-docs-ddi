---
UID: NC:video.PVIDEO_HW_QUERY_INTERFACE
title: PVIDEO_HW_QUERY_INTERFACE
author: windows-driver-content
description: HwVidQueryInterface returns a miniport driver-implemented functional interface that a child device can call.
old-location: display\hwvidqueryinterface.htm
tech.root: display
ms.assetid: f16a7fa3-3471-4ccb-b1b4-982d33f930d3
ms.date: 05/10/2018
ms.keywords: HwVidQueryInterface, HwVidQueryInterface callback function [Display Devices], PVIDEO_HW_QUERY_INTERFACE, PVIDEO_HW_QUERY_INTERFACE callback, VideoMiniport_Functions_69dec180-d966-4082-b050-0ed2e0e03121.xml, display.hwvidqueryinterface, video/HwVidQueryInterface
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidQueryInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_HW_QUERY_INTERFACE callback function


## -description


<i>HwVidQueryInterface</i> returns a miniport driver-implemented functional interface that a child device can call.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param QueryInterface

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569225">QUERY_INTERFACE</a> structure in which the miniport driver should return information about the interface it supports.


## -returns



<i>HwVidQueryInterface</i> should return NO_ERROR upon success; otherwise it should return the appropriate error code. For example, a miniport driver should return ERROR_OUTOFMEMORY if it cannot allocate memory to complete the operation.




## -remarks



<i>HwVidQueryInterface</i> exposes a communication mechanism between the video miniport driver and the driver of a child device. A miniport driver that exposes such a mechanism should implement this function.

The video port calls <i>HwVidQueryInterface</i> when it receives an IRP_MN_QUERY_INTERFACE request. If the miniport driver fails the call, the video port driver passes the request to the parent of the miniport driver's device.

<i>HwVidQueryInterface</i> should fill in the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure to which <i>QueryInterface</i>-&gt;<b>Interface</b> points as follows:

<ul>
<li>
Set <b>Size</b> to the number of bytes in the INTERFACE structure. This value must not exceed the number of bytes specified by <i>QueryInterface</i>-&gt;<b>Size</b>.

</li>
<li>
Set <b>Version</b> to the version of the interface being returned by the miniport driver. The miniport driver should best match the version requested by the child driver in <i>QueryInterface</i>-&gt;<b>Version</b>.

</li>
<li>
Set <b>Context</b> to point to a miniport driver-defined context for the interface. Typically, a miniport driver would set <b>Context</b> to point to the device extension identified by <i>HwDeviceExtension</i>.

</li>
<li>
Initialize <b>InterfaceReference</b> and <b>InterfaceDereference</b> to point to the miniport driver-implemented reference and dereference routines for this interface.

</li>
<li>
Initialize all additional interface-specific members to point to the appropriate routines of the interface being exposed.

</li>
</ul>
A miniport driver that returns an interface is responsible for referencing the interface by calling <i>QueryInterface</i>-&gt;<b>Interface.InterfaceReference</b>. The child driver requesting the interface is responsible for dereferencing it when the driver no longer requires the interface by calling <i>QueryInterface</i>-&gt;<b>Interface.InterfaceDereference</b>. If the child driver passes the interface to another component, the child is responsible for taking out another reference, and the other component is responsible for removing the additional reference when it no longer needs access to the interface. Referencing allows a parent to determine when the interface is still required by the child device, and consequently when the parent can free any interface-associated resources.

The driver of a child device can call into the miniport driver through the functions exposed by <i>HwVidQueryInterface</i> at any time without the video port driver's knowledge. Consequently, the miniport driver must synchronize access to itself by acquiring and releasing the video port driver-maintained device lock in all of the functions exposed by <i>HwVidQueryInterface</i>.

A child device is enumerated by <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>.

<i>HwVidQueryInterface</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569225">QUERY_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570174">VideoPortAcquireDeviceLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570356">VideoPortReleaseDeviceLock</a>
 

 

