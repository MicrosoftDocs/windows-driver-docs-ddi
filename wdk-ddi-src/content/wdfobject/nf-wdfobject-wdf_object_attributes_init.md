---
UID: NF:wdfobject.WDF_OBJECT_ATTRIBUTES_INIT
title: WDF_OBJECT_ATTRIBUTES_INIT function
author: windows-driver-content
description: The WDF_OBJECT_ATTRIBUTES_INIT function initializes a driver's WDF_OBJECT_ATTRIBUTES structure.
old-location: wdf\wdf_object_attributes_init.htm
old-project: wdf
ms.assetid: c8412ad0-a3c2-41cf-aed6-32b244bc3969
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFGenObjectRef_2d1e5e34-5637-4301-807c-ad525d4cb34b.xml, WDF_OBJECT_ATTRIBUTES_INIT, WDF_OBJECT_ATTRIBUTES_INIT function, kmdf.wdf_object_attributes_init, wdf.wdf_object_attributes_init, wdfobject/WDF_OBJECT_ATTRIBUTES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	HeaderDef
api_location:
-	wdfobject.h
api_name:
-	WDF_OBJECT_ATTRIBUTES_INIT
product: Windows
targetos: Windows
req.typenames: WDF_SYNCHRONIZATION_SCOPE
req.product: Windows 10 or later.
---

# WDF_OBJECT_ATTRIBUTES_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_OBJECT_ATTRIBUTES_INIT function initializes a driver's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure.


## -syntax


````
VOID WDF_OBJECT_ATTRIBUTES_INIT(
  _Out_ PWDF_OBJECT_ATTRIBUTES Attributes
);
````


## -parameters




### -param Attributes [out]

A pointer to the driver's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure.


## -returns



None




## -remarks



The WDF_OBJECT_ATTRIBUTES_INIT function sets the <b>ExecutionLevel</b> member of the specified <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure to <b>WdfExecutionLevelInheritFromParent</b>, and it sets the <b>SynchronizationScope</b> member to <b>WdfSynchronizationScopeInheritFromParent</b>.

For code examples that use WDF_OBJECT_ATTRIBUTES_INIT, see <a href="..\wdfobject\nf-wdfobject-wdfobjectcreate.md">WdfObjectCreate</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff548749">WdfObjectGetTypedContext</a>.




## -see-also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



 

 


