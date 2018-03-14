---
UID: NF:wdfobject.WdfObjectCreate
title: WdfObjectCreate function
author: windows-driver-content
description: The WdfObjectCreate method creates a general framework object.
old-location: wdf\wdfobjectcreate.htm
old-project: wdf
ms.assetid: fd56c529-c7ad-4fc4-8fcc-950a1e8e21e5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFGenObjectRef_6d84af32-c9c6-4327-be42-cda437dc80a1.xml, WdfObjectCreate, WdfObjectCreate method, kmdf.wdfobjectcreate, wdf.wdfobjectcreate, wdfobject/WdfObjectCreate
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
-	WdfObjectCreate
product: Windows
targetos: Windows
req.typenames: WDF_SYNCHRONIZATION_SCOPE
req.product: Windows 10 or later.
---

# WdfObjectCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectCreate</b> method creates a general framework object.


## -syntax


````
NTSTATUS WdfObjectCreate(
  _In_opt_ PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_    WDFOBJECT              *Object
);
````


## -parameters




### -param Attributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Object [out]

A pointer to a location that receives a handle to the new framework object.


## -returns



<b>WdfObjectCreate</b> returns STATUS_SUCCESS if the operation succeeds. For a list of additional return values, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



By default, the new general framework object's parent is the framework driver object that the <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the general object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the general object when it has finished using the object; otherwise, the object will remain until the I/O manager unloads your driver. 

For more information about the <b>WdfObjectCreate</b> method, see <a href="https://msdn.microsoft.com/d3356d3f-8110-44dd-b4a2-36265f5a1714">Using General Framework Objects</a>.


#### Examples

The following code example initializes an WDF_OBJECT_ATTRIBUTES structure and creates a general framework object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  Attributes;
WDFOBJECT  Object;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;Attributes);
status = WdfObjectCreate(
                         &amp;Attributes,
                         &amp;Object
                         );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>



<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>



<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



 

 


