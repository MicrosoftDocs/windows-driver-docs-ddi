---
UID: NF:wdfcollection.WdfCollectionCreate
title: WdfCollectionCreate function (wdfcollection.h)
description: The WdfCollectionCreate method creates a framework collection object.
old-location: wdf\wdfcollectioncreate.htm
tech.root: wdf
ms.assetid: b185b1ca-6fd9-4508-b001-d1853f2948c2
ms.date: 02/26/2018
ms.keywords: DFCollectionObjectRef_0c567e7a-209b-4ac2-a721-0c2ee4122aaa.xml, WdfCollectionCreate, WdfCollectionCreate method, kmdf.wdfcollectioncreate, wdf.wdfcollectioncreate, wdfcollection/WdfCollectionCreate
ms.topic: function
req.header: wdfcollection.h
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
-	WdfCollectionCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCollectionCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfCollectionCreate</b> method creates a framework collection object. 


## -parameters




### -param CollectionAttributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new collection object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Collection [out]

A pointer to a location that receives a handle to the new collection object.


## -returns



<b>WdfCollectionCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller supplied an invalid parameter value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A collection object could not be allocated.

</td>
</tr>
</table>
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



After calling <b>WdfCollectionCreate</b> to create a framework collection object, a driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545732">WdfCollectionAdd</a> to add objects to the collection. 

By default, the new collection object's parent is the framework driver object that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the collection object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the collection object when it has finished using the object; otherwise, the object will remain until the I/O manager unloads your driver. 

For more information about object collections, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

For a code example that uses <b>WdfCollectionCreate</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545732">WdfCollectionAdd</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545732">WdfCollectionAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545784">WdfCollectionRemove</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>
 

 

