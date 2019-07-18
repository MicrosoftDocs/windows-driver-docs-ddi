---
UID: NF:wdfobject.WdfObjectCreate
title: WdfObjectCreate function (wdfobject.h)
description: The WdfObjectCreate method creates a general framework object.
old-location: wdf\wdfobjectcreate.htm
tech.root: wdf
ms.assetid: fd56c529-c7ad-4fc4-8fcc-950a1e8e21e5
ms.date: 02/26/2018
ms.keywords: DFGenObjectRef_6d84af32-c9c6-4327-be42-cda437dc80a1.xml, WdfObjectCreate, WdfObjectCreate method, kmdf.wdfobjectcreate, wdf.wdfobjectcreate, wdfobject/WdfObjectCreate
ms.topic: function
f1_keywords:
 - "wdfobject/WdfObjectCreate"
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
- WdfObjectCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfObjectCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfObjectCreate</b> method creates a general framework object.


## -parameters




### -param Attributes [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Object [out]

A pointer to a location that receives a handle to the new framework object.


## -returns



<b>WdfObjectCreate</b> returns STATUS_SUCCESS if the operation succeeds. For a list of additional return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



By default, the new general framework object's parent is the framework driver object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the general object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the general object when it has finished using the object; otherwise, the object will remain until the I/O manager unloads your driver. 

For more information about the <b>WdfObjectCreate</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-general-framework-objects">Using General Framework Objects</a>.

For more information about the cleanup rules for a framework object hierarchy, see [Framework Object Life Cycle](https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-life-cycle).

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

WDF_OBJECT_ATTRIBUTES_INIT(&Attributes);
status = WdfObjectCreate(
                         &Attributes,
                         &Object
                         );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a>
 

 

