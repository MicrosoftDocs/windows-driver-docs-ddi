---
UID: NF:wdfresource.WdfCmResourceListGetDescriptor
title: WdfCmResourceListGetDescriptor function
author: windows-driver-content
description: The WdfCmResourceListGetDescriptor method returns a pointer to a resource descriptor that is contained in a specified resource list.
old-location: wdf\wdfcmresourcelistgetdescriptor.htm
old-project: wdf
ms.assetid: 5aa96fed-83ca-417e-876d-a734be6f27dd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_bdc580d1-2283-4549-a26b-cbe0f2a84e19.xml, WdfCmResourceListGetDescriptor, WdfCmResourceListGetDescriptor method, kmdf.wdfcmresourcelistgetdescriptor, wdf.wdfcmresourcelistgetdescriptor, wdfresource/WdfCmResourceListGetDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfCmResourceListGetDescriptor
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfCmResourceListGetDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCmResourceListGetDescriptor</b> method returns a pointer to a resource descriptor that is contained in a specified resource list.


## -syntax


````
PCM_PARTIAL_RESOURCE_DESCRIPTOR WdfCmResourceListGetDescriptor(
  _In_ WDFCMRESLIST List,
  _In_ ULONG        Index
);
````


## -parameters




### -param List [in]

A handle to a framework resource-list object that represents a list of hardware resources for a device.


### -param Index [in]

A zero-based value that is used as an index into the logical configuration that <i>List</i> specifies.


## -returns



<b>WdfCmResourceListGetDescriptor</b> returns a pointer to the <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the hardware resource that the <i>Index</i> parameter identifies, if the index value is valid. Otherwise, the method returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver cannot modify the resource descriptor that <b>WdfCmResourceListGetDescriptor</b> retrieves. 

For more information about resource lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfCmResourceListGetDescriptor</b>, see <a href="..\wdfresource\nf-wdfresource-wdfcmresourcelistgetcount.md">WdfCmResourceListGetCount</a>.

<div class="code"></div>



## -see-also

<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCmResourceListGetDescriptor method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

