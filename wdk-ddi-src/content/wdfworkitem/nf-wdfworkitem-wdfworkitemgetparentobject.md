---
UID: NF:wdfworkitem.WdfWorkItemGetParentObject
title: WdfWorkItemGetParentObject function
author: windows-driver-content
description: The WdfWorkItemGetParentObject method returns the framework object that a specified work item is associated with.
old-location: wdf\wdfworkitemgetparentobject.htm
old-project: wdf
ms.assetid: 6ebb1955-1ffc-4869-84c8-69d672ac782e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfworkitemgetparentobject, WdfWorkItemGetParentObject method, DFWorkItemObjectRef_d01f85c6-ab9e-413a-8352-49db7ae053d0.xml, PFN_WDFWORKITEMGETPARENTOBJECT, wdfworkitem/WdfWorkItemGetParentObject, kmdf.wdfworkitemgetparentobject, WdfWorkItemGetParentObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfworkitem.h
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfWorkItemGetParentObject
product: Windows
targetos: Windows
req.typenames: "*PWDF_WMI_PROVIDER_CONFIG, WDF_WMI_PROVIDER_CONFIG"
req.product: Windows 10 or later.
---

# WdfWorkItemGetParentObject function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfWorkItemGetParentObject</b> method returns the framework object that a specified work item is associated with.


## -syntax


````
WDFOBJECT WdfWorkItemGetParentObject(
  _In_ WDFWORKITEM WorkItem
);
````


## -parameters




#### - WorkItem [in]

A handle to a framework work-item object that is obtained from a previous call to <a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a>.


## -returns


<b>WdfWorkItemGetParentObject</b> returns a handle to the framework object that the driver specified as the <b>ParentObject</b> member of the driver's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure when the driver previously called <a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about work items, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.



## -see-also

<a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a>

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWorkItemGetParentObject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

