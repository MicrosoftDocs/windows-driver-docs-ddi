---
UID: NF:wdfmemory.WdfMemoryCreate
title: WdfMemoryCreate function
author: windows-driver-content
description: The WdfMemoryCreate method creates a framework memory object and allocates a memory buffer of a specified size.
old-location: wdf\wdfmemorycreate.htm
tech.root: wdf
ms.assetid: d2071ea0-737d-4a61-90d6-614d77983f0b
ms.date: 02/26/2018
ms.keywords: DFMemoryObjectRef_53623d93-01bb-4062-b066-e884beed3f32.xml, WdfMemoryCreate, WdfMemoryCreate method, kmdf.wdfmemorycreate, wdf.wdfmemorycreate, wdfmemory/WdfMemoryCreate
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, ParentObjectCheck
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: See Remarks section.
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
-	WdfMemoryCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfMemoryCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfMemoryCreate</b> method creates a framework memory object and allocates a memory buffer of a specified size. 


## -parameters




### -param Attributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the new memory object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param PoolType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>-typed value that specifies the type of memory to be allocated. 


### -param PoolTag [in, optional]

A driver-defined pool tag for the allocated memory. Debuggers display this tag. Drivers typically specify a character string of up to four characters, delimited by single quotation marks, in reverse order (for example, 'dcba'). The ASCII value of each character in the tag must be between 0 and 127. Debugging your driver is easier if each pool tag is unique. 

If <i>PoolTag</i> is zero, the framework provides a default pool tag that uses the first four characters of your driver's kernel-mode service name. If the service name begins with "WDF" (the name is not case sensitive and does not include the quotation marks), the next four characters are used. If fewer than four characters are available, "FxDr" is used. 

For KMDF versions 1.5 and later, your driver can use the <b>DriverPoolTag</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551300">WDF_DRIVER_CONFIG</a> structure to specify a default pool tag.


### -param BufferSize [in]

The nonzero specified size, in bytes, of the buffer. 


### -param Memory [out]

A pointer to a location that receives a handle to the new memory object.


### -param Buffer [out, optional]

A pointer to a location that receives a pointer to the buffer that is associated with the new memory object. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>WdfMemoryCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
 

For a list of other return values that the <b>WdfMemoryCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>WdfMemoryCreate</b> method allocates a buffer of the size that the <i>BufferSize</i> parameter specifies and creates a framework memory object that represents the buffer. 

To obtain the buffer's address, your driver can supply a non-<b>NULL</b> value for the <b>WdfMemoryCreate</b> function's <i>Buffer</i> parameter, or the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>.

The default parent object for each memory object is the framework driver object that represents the driver that called <b>WdfMemoryCreate</b>. If your driver creates a memory object that it uses with a specific device object, request object, or other framework object, it should set the memory object's parent appropriately. The memory object and its buffer will be deleted when the parent object is deleted. If you do not change the default parent object, the memory object and its buffer will remain until the I/O manager unloads your driver. 

A driver can also delete a memory object and its buffer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a>.

If <i>BufferSize</i> is less than PAGE_SIZE, the operating system gives the caller exactly the number of requested bytes of memory. The buffer is not necessarily page-aligned, but it is aligned by the number of bytes that the MEMORY_ALLOCATION_ALIGNMENT constant specifies in <i>Ntdef.h</i>. Buffers of PAGE_SIZE or less do not cross page boundaries. 

If <i>BufferSize</i> is PAGE_SIZE or greater, the system allocates a page-aligned buffer. If the <i>PoolType</i> parameter is <b>NonPagedPool</b>, the system allocates the number of pages that are necessary to hold all of the bytes. Any unused bytes on the last-allocated page are essentially wasted.

For more information about framework memory objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

If your driver specifies <b>PagedPool</b> for <i>PoolType</i>, the <b>WdfMemoryCreate</b> method must be called at IRQL &lt;= APC_LEVEL. Otherwise, the method can be called at IRQL &lt;= DISPATCH_LEVEL.


#### Examples

The following code example creates a framework memory object and allocates a buffer whose size is WRITE_BUFFER_SIZE. The memory object's parent is a request object. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;
WDF_OBJECT_ATTRIBUTES  attributes;
WDFMEMORY  writeBufferMemHandle;
PVOID  writeBufferPointer;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = requestHandle;
status = WdfMemoryCreate(
                         &amp;attributes,
                         NonPagedPool,
                         0,
                         WRITE_BUFFER_SIZE,
                         &amp;writeBufferMemHandle,
                         &amp;writeBufferPointer
                         );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548709">WdfMemoryCreateFromLookaside</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a>
 

 

