---
UID: NF:wdfobject.WdfObjectReferenceActual
title: WdfObjectReferenceActual function (wdfobject.h)
description: The WdfObjectReferenceActual method increments the reference count for a specified framework object and assigns a tag value, line number, and file name to the reference.
old-location: wdf\wdfobjectreferenceactual.htm
tech.root: wdf
ms.assetid: d0bb58c1-1036-496a-b108-c0d5e5de3bc2
ms.date: 02/26/2018
ms.keywords: DFGenObjectRef_f1251726-c87f-4faa-9a96-0b7e49da2f2c.xml, WdfObjectReferenceActual, WdfObjectReferenceActual method, kmdf.wdfobjectreferenceactual, wdf.wdfobjectreferenceactual, wdfobject/WdfObjectReferenceActual
f1_keywords:
 - "wdfobject/WdfObjectReferenceActual"
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
- WdfObjectReferenceActual
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfObjectReferenceActual function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfObjectReferenceActual</b> method increments the reference count for a specified framework object and assigns a tag value, line number, and file name to the reference.


## -parameters




### -param Handle [in]

A handle to a framework object.


### -param Tag [in, optional]

A driver-defined value that the framework stores as an identification tag for the object reference.


### -param Line [in]

A numeric value that represents a line number in a driver source file.


### -param File [in]

A pointer to a null-terminated constant character string that represents the name of a driver source file. This parameter is optional and can be <b>NULL</b>.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




If your driver calls <b>WdfObjectReferenceActual</b> to increment a reference count, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdereferenceactual">WdfObjectDereferenceActual</a> to decrement the count.

Calling <b>WdfObjectReferenceActual</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectreferencewithtag">WdfObjectReferenceWithTag</a> instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a> provides additional information (tag value, line number, and file name) to Microsoft debuggers. <b>WdfObjectReferenceActual</b> allows your driver to specify the line number and file name, while <b>WdfObjectReferenceWithTag</b> uses the driver's current line number and file name.

You can view the tag, line number, and file name values by using the <b>!wdftagtracker</b> debugger extension. The debugger extension displays the tag value as both a pointer and a series of characters. For more about debugger extensions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/debugging-driver-installation">Debugging a KMDF Driver</a>.

For more information about object reference counts, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-life-cycle">Framework Object Life Cycle</a>.

For more information about the cleanup rules for a framework object hierarchy, see [Framework Object Life Cycle](https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-life-cycle).

#### Examples

The following code example increments an object's reference count and assigns a tag value, line number, and file name to the reference.

```cpp
WdfObjectReferenceActual(
                         object,
                         pTag,
                         line,
                         FILE_NAME
                         );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a>
 

 

