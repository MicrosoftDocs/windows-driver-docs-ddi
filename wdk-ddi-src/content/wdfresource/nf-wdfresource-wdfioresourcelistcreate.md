---
UID: NF:wdfresource.WdfIoResourceListCreate
title: WdfIoResourceListCreate function
author: windows-driver-content
description: The WdfIoResourceListCreate method creates an empty logical configuration, which can be populated and added to a resource requirements list.
old-location: wdf\wdfioresourcelistcreate.htm
old-project: wdf
ms.assetid: aaf3d22d-da54-4478-9bf8-aad4b943788a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoResourceListCreate
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
req.alt-api: WdfIoResourceListCreate
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

# WdfIoResourceListCreate function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListCreate</b> method creates an empty <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>, which can be populated and added to a resource requirements list.



## -syntax

````
NTSTATUS WdfIoResourceListCreate(
  _In_     WDFIORESREQLIST        RequirementsList,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_    WDFIORESLIST           *ResourceList
);
````


## -parameters

### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param ResourceList [out]

A handle to a framework resource-range-list object that represents the new logical configuration.


## -returns
<b>WdfIoResourceListCreate</b> returns STATUS_SUCCESS if the operation succeeds.

 For additional return values, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



A system bug check occurs if the driver supplies an invalid object handle.




## -remarks
For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.

The caller-specified resource-requirements-list object becomes the parent of the new resource-range-list object. The driver cannot change this parent, and the <b>ParentObject</b> member or the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>.

For a code example that uses <b>WdfIoResourceListCreate</b>, see <a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistappendioreslist.md">WdfIoResourceRequirementsListAppendIoResList</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceListCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

