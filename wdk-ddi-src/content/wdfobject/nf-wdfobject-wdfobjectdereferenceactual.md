---
UID: NF:wdfobject.WdfObjectDereferenceActual
title: WdfObjectDereferenceActual function
author: windows-driver-content
description: The WdfObjectDereferenceActual method decrements the reference count for a specified framework object and assigns a tag value, line number, and file name to the reference.
old-location: wdf\wdfobjectdereferenceactual.htm
old-project: wdf
ms.assetid: ff96ea2b-a1f9-417c-98e6-fbf9cc9f6827
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfObjectDereferenceActual
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
req.alt-api: WdfObjectDereferenceActual
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: WDF_SYNCHRONIZATION_SCOPE
req.product: Windows 10 or later.
---

# WdfObjectDereferenceActual function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectDereferenceActual</b> method decrements the reference count for a specified framework object and assigns a tag value, line number, and file name to the reference<i>.</i>



## -syntax

````
VOID WdfObjectDereferenceActual(
  _In_     WDFOBJECT Handle,
  _In_opt_ PVOID     Tag,
  _In_     LONG      Line,
  _In_opt_ PCCH      File
);
````


## -parameters

### -param Handle [in]

A handle to a framework object.


### -param Tag [in, optional]

A driver-defined value that identifies an object reference. The tag value must match a tag value that the driver previously supplied to <a href="..\wdfobject\nf-wdfobject-wdfobjectreferenceactual.md">WdfObjectReferenceActual</a>.


### -param Line [in]

A numeric value that represents a line number in a driver source file.


### -param File [in, optional]

A pointer to a null-terminated constant character string that represents the name of a driver source file. This parameter is optional and can be <b>NULL</b>.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
If the object's reference count becomes zero, the object might be deleted before <b>WdfObjectDereferenceActual</b> returns. 

Calling <b>WdfObjectDereferenceActual</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548746">WdfObjectDereferenceWithTag</a> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a> provides additional information (tag string, line number, and file name) to Microsoft debuggers. <b>WdfObjectDereferenceActual</b> allows your driver to specify the line number and file name, while <b>WdfObjectDereferenceWithTag</b> uses the driver's current line number and file name.

You can view the tag, line number, and file name values by using the <b>!wdftagtracker</b> debugger extension. The debugger extension displays the tag value as both a pointer and a series of characters. For more information about debugger extensions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/debugging-driver-installation">Debugging a KMDF Driver</a>.

For more information about object reference counts, see <a href="https://msdn.microsoft.com/33efc3a8-ac46-4626-ba0f-beb1eaa9ee47">Framework Object Life Cycle</a>.

The following code example decrements an object's reference count and assigns a tag value, line number, and file name to the reference.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a>
</dt>
<dt>
<a href="..\wdfobject\nf-wdfobject-wdfobjectreferenceactual.md">WdfObjectReferenceActual</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfObjectDereferenceActual method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

