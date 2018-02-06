---
UID: NF:wdfobject.WDF_OBJECT_ATTRIBUTES_INIT
title: WDF_OBJECT_ATTRIBUTES_INIT function
author: windows-driver-content
description: The WDF_OBJECT_ATTRIBUTES_INIT function initializes a driver's WDF_OBJECT_ATTRIBUTES structure.
old-location: wdf\wdf_object_attributes_init.htm
old-project: wdf
ms.assetid: c8412ad0-a3c2-41cf-aed6-32b244bc3969
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdf_object_attributes_init, WDF_OBJECT_ATTRIBUTES_INIT function, DFGenObjectRef_2d1e5e34-5637-4301-807c-ad525d4cb34b.xml, WDF_OBJECT_ATTRIBUTES_INIT, wdfobject/WDF_OBJECT_ATTRIBUTES_INIT, kmdf.wdf_object_attributes_init
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfobject.h
apiname:
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_OBJECT_ATTRIBUTES_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

