---
UID: NF:wdfresource.WdfIoResourceListRemoveByDescriptor
title: WdfIoResourceListRemoveByDescriptor function
author: windows-driver-content
description: The WdfIoResourceListRemoveByDescriptor method removes a resource descriptor from a resource requirement list's logical configuration.
old-location: wdf\wdfioresourcelistremovebydescriptor.htm
old-project: wdf
ms.assetid: c4968449-eba0-4f7a-98e6-6955d3333495
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfresource/WdfIoResourceListRemoveByDescriptor, DFResourceObjectRef_4bd88d52-ea6d-43c1-9477-8338e6bf1cdb.xml, WdfIoResourceListRemoveByDescriptor, PFN_WDFIORESOURCELISTREMOVEBYDESCRIPTOR, WdfIoResourceListRemoveByDescriptor method, kmdf.wdfioresourcelistremovebydescriptor, wdf.wdfioresourcelistremovebydescriptor
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfIoResourceListRemoveByDescriptor
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfIoResourceListRemoveByDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListRemoveByDescriptor</b> method removes a resource descriptor from a resource requirement list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.


## -syntax


````
VOID WdfIoResourceListRemoveByDescriptor(
  _In_ WDFIORESLIST            ResourceList,
  _In_ PIO_RESOURCE_DESCRIPTOR Descriptor
);
````


## -parameters




#### - ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


#### - Descriptor [in]

A pointer to an <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## -returns


None.

A system bug check occurs if the driver supplies an invalid object handle.





## -remarks


The <b>WdfIoResourceListRemoveByDescriptor</b> method removes the resource descriptor that matches the <i>Descriptor</i> parameter. To find a match, the method compares the specified resource descriptor with the resource descriptors in the logical configuration, byte for byte.

When <b>WdfIoResourceListRemoveByDescriptor</b> removes the resource descriptor that has the index value <i>n</i>, the index value of the next resource descriptor changes from <i>n</i>+1 to <i>n</i>.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistremove.md">WdfIoResourceListRemove</a>

<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceListRemoveByDescriptor method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

