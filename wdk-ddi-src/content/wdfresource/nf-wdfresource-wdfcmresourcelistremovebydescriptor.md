---
UID: NF:wdfresource.WdfCmResourceListRemoveByDescriptor
title: WdfCmResourceListRemoveByDescriptor function
author: windows-driver-content
description: The WdfCmResourceListRemoveByDescriptor method removes a specified resource descriptor from a specified resource list.
old-location: wdf\wdfcmresourcelistremovebydescriptor.htm
old-project: wdf
ms.assetid: 532b56c9-6c24-4737-b1d6-e44802a898e3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfCmResourceListRemoveByDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfCmResourceListRemoveByDescriptor
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: *PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfCmResourceListRemoveByDescriptor function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfCmResourceListRemoveByDescriptor</b> method removes a specified resource descriptor from a specified resource list.



## -syntax

````
VOID WdfCmResourceListRemoveByDescriptor(
  _In_ WDFCMRESLIST                    List,
  _In_ PCM_PARTIAL_RESOURCE_DESCRIPTOR Descriptor
);
````


## -parameters

### -param List [in]

A handle to a framework resource-list object that represents a list of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## -returns
None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks
The <b>WdfCmResourceListRemoveByDescriptor</b> method removes the resource descriptor that matches the <i>Descriptor</i> parameter. To find a match, the method compares the specified resource descriptor with the resource descriptors in the logical configuration, byte for byte.

When <b>WdfCmResourceListRemoveByDescriptor</b> removes the resource descriptor that has the index value <i>n</i>, the index value of the next resource descriptor changes from <i>n</i>+1 to <i>n</i>.

For more information about resource lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

The following code example searches for port resource descriptors in a device's resource lists. For each port resource that the example finds, it checks to see if the port address is within a certain range. If the port address is outside of the range, the example removes the descriptor from both the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/raw-and-translated-resources">raw and translated resource lists</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdfresource\nf-wdfresource-wdfcmresourcelistremove.md">WdfCmResourceListRemove</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCmResourceListRemoveByDescriptor method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

