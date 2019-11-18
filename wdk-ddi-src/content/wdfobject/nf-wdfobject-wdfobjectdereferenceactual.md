---
UID: NF:wdfobject.WdfObjectDereferenceActual
title: WdfObjectDereferenceActual function (wdfobject.h)
description: The WdfObjectDereferenceActual method decrements the reference count for a specified framework object and assigns a tag value, line number, and file name to the reference.
old-location: wdf\wdfobjectdereferenceactual.htm
tech.root: wdf
ms.assetid: ff96ea2b-a1f9-417c-98e6-fbf9cc9f6827
ms.date: 02/26/2018
ms.keywords: DFGenObjectRef_d09786da-bccf-4735-bd7b-816bf2bd999d.xml, WdfObjectDereferenceActual, WdfObjectDereferenceActual method, kmdf.wdfobjectdereferenceactual, wdf.wdfobjectdereferenceactual, wdfobject/WdfObjectDereferenceActual
ms.topic: function
f1_keywords:
 - "wdfobject/WdfObjectDereferenceActual"
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfObjectDereferenceActual
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfObjectDereferenceActual function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfObjectDereferenceActual</b> method decrements the reference count for a specified framework object and assigns a tag value, line number, and file name to the reference<i>.</i>


## -parameters




### -param Handle [in]

A handle to a framework object.


### -param Tag [in, optional]

A driver-defined value that identifies an object reference. The tag value must match a tag value that the driver previously supplied to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectreferenceactual">WdfObjectReferenceActual</a>.


### -param Line [in]

A numeric value that represents a line number in a driver source file.


### -param File [in, optional]

A pointer to a null-terminated constant character string that represents the name of a driver source file. This parameter is optional and can be <b>NULL</b>.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




If the object's reference count becomes zero, the object might be deleted before <b>WdfObjectDereferenceActual</b> returns. 

Calling <b>WdfObjectDereferenceActual</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereferencewithtag">WdfObjectDereferenceWithTag</a> instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a> provides additional information (tag string, line number, and file name) to Microsoft debuggers. <b>WdfObjectDereferenceActual</b> allows your driver to specify the line number and file name, while <b>WdfObjectDereferenceWithTag</b> uses the driver's current line number and file name.

You can view the tag, line number, and file name values by using the <b>!wdftagtracker</b> debugger extension. The debugger extension displays the tag value as both a pointer and a series of characters. For more information about debugger extensions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/debugging-driver-installation">Debugging a KMDF Driver</a>.

For more information about object reference counts and the cleanup rules for a framework object hierarchy, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-life-cycle">Framework Object Life Cycle</a>.

#### Examples

The following code example decrements an object's reference count and assigns a tag value, line number, and file name to the reference.

```cpp
WdfObjectDereferenceActual(
                           object,
                           pTag,
                           line,
                           FILE_NAME
                           );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectreferenceactual">WdfObjectReferenceActual</a>
 

 

