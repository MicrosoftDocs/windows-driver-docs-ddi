---
UID: NF:wdfresource.WdfIoResourceRequirementsListRemove
title: WdfIoResourceRequirementsListRemove function
author: windows-driver-content
description: The WdfIoResourceRequirementsListRemove method removes a logical configuration from a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistremove.htm
old-project: wdf
ms.assetid: 3668aa5a-1cb4-4ee1-91bd-bf2f3fa30622
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFResourceObjectRef_7f7c29e8-231a-48ec-b4e3-01989ad994b0.xml, wdf.wdfioresourcerequirementslistremove, PFN_WDFIORESOURCEREQUIREMENTSLISTREMOVE, WdfIoResourceRequirementsListRemove method, kmdf.wdfioresourcerequirementslistremove, WdfIoResourceRequirementsListRemove, wdfresource/WdfIoResourceRequirementsListRemove
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
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname: 
-	WdfIoResourceRequirementsListRemove
product: Windows
targetos: Windows
req.typenames: *PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfIoResourceRequirementsListRemove function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListRemove</b> method removes a <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a> from a resource requirements list.


## -syntax


````
VOID WdfIoResourceRequirementsListRemove(
  _In_ WDFIORESREQLIST RequirementsList,
  _In_ ULONG           Index
);
````


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param Index [in]

A zero-based value that is used as an index into the resource requirements list that <i>RequirementsList</i> specifies. 


## -returns


None.

A system bug check occurs if the driver supplies an invalid object handle.



## -remarks


The <b>WdfIoResourceRequirementsListRemove</b> method removes the logical configuration that is associated with the index value that the <i>Index</i> parameter specifies.

When <b>WdfIoResourceRequirementsListRemove</b> removes the logical configuration that has the index value <i>n</i>, the index value of the next logical configuration changes from <i>n</i>+1 to <i>n</i>.

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfresource\nf-wdfresource-wdfioresourcerequirementslistremovebyioreslist.md">WdfIoResourceRequirementsListRemoveByIoResList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceRequirementsListRemove method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

