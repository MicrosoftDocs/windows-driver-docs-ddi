---
UID: NF:wdfmemory.WdfLookasideListCreate
title: WdfLookasideListCreate function (wdfmemory.h)
description: The WdfLookasideListCreate method creates a lookaside-list object, from which the driver can obtain memory objects.
old-location: wdf\wdflookasidelistcreate.htm
tech.root: wdf
ms.assetid: 37fc86b0-de8c-469b-94bb-ad482b9c7202
ms.date: 02/26/2018
keywords: ["WdfLookasideListCreate function"]
ms.keywords: DFMemoryObjectRef_f5146f3e-a9ae-459c-9361-37a4f33edd67.xml, WdfLookasideListCreate, WdfLookasideListCreate method, kmdf.wdflookasidelistcreate, wdf.wdflookasidelistcreate, wdfmemory/WdfLookasideListCreate
f1_keywords:
 - "wdfmemory/WdfLookasideListCreate"
 - "WdfLookasideListCreate"
req.header: wdfmemory.h
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfLookasideListCreate
targetos: Windows
req.typenames: 
---

# WdfLookasideListCreate function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfLookasideListCreate</b> method creates a lookaside-list object, from which the driver can obtain memory objects. 


## -parameters




### -param LookasideAttributes 
[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the new lookaside-list object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param BufferSize 
[in]
The nonzero size, in bytes, of the buffer that the framework will allocate for each memory object. 


### -param PoolType 
[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>-typed value that specifies the type of memory to be allocated. 


### -param MemoryAttributes 
[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for each memory object that the driver obtains from the lookaside list. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param PoolTag 
[in, optional]
A driver-defined pool tag for each memory object's buffer. Debuggers display this tag. Drivers typically specify a character string of up to four characters, delimited by single quotation marks, in reverse order (for example, 'dcba'). The ASCII value of each character in the tag must be between 0 and 127. Debugging your driver is easier if each pool tag is unique. 

If <i>PoolTag</i> is zero, the framework provides a default pool tag that uses the first four characters of your driver's kernel-mode service name. If the service name begins with "WDF" (the name is not case sensitive and does not include the quotation marks), the next four characters are used. If fewer than four characters are available, "FxDr" is used.

For KMDF versions 1.5 and later, your driver can use the <b>DriverPoolTag</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/ns-wdfdriver-_wdf_driver_config">WDF_DRIVER_CONFIG</a> structure to specify a default pool tag.


### -param Lookaside 
[out]
A pointer to a location that receives a handle to the new lookaside-list object.


## -returns



<b>WdfLookasideListCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfLookasideListCreate</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.



This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



After your driver calls <b>WdfLookasideListCreate</b> to create a lookaside-list object, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatefromlookaside">WdfMemoryCreateFromLookaside</a> to obtain a buffer from the lookaside list. 

By default, the new lookaside-list object's parent is the framework driver object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> method creates. You can use the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the lookaside-list object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the lookaside-list object when it has finished using the object; otherwise, the lookaside-list object will remain until the I/O manager unloads your driver. 

If your driver supplies a WDF_OBJECT_ATTRIBUTES structure for both the <i>LookasideAttributes</i> and the <i>MemoryAttributes</i> parameters, and if both structures specify a device object as the parent object, the device object handles must be the same. 

For more information about framework memory objects and lookaside lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

If your driver specifies <b>PagedPool</b> for the <i>PoolType</i> parameter, the <b>WdfLookasideListCreate</b> method must be called at IRQL <= APC_LEVEL. Otherwise, the method can be called at IRQL <= DISPATCH_LEVEL.


#### Examples

For a code example that uses <b>WdfLookasideListCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatefromlookaside">WdfMemoryCreateFromLookaside</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatefromlookaside">WdfMemoryCreateFromLookaside</a>
 

 

