---
UID: NF:wdfmemory.WdfMemoryCreatePreallocated
title: WdfMemoryCreatePreallocated function
author: windows-driver-content
description: The WdfMemoryCreatePreallocated method creates a framework memory object for a driver-supplied memory buffer.
old-location: wdf\wdfmemorycreatepreallocated.htm
old-project: wdf
ms.assetid: 8c4f9abc-f03d-4084-b0ce-34aea5dd7d96
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFMemoryObjectRef_03f219cd-a77b-4a17-b67a-2b01e0aeb3e6.xml, PFN_WDFMEMORYCREATEPREALLOCATED, WdfMemoryCreatePreallocated, WdfMemoryCreatePreallocated method, wdfmemory/WdfMemoryCreatePreallocated, wdf.wdfmemorycreatepreallocated, kmdf.wdfmemorycreatepreallocated
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfMemoryCreatePreallocated
product: Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---

# WdfMemoryCreatePreallocated function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfMemoryCreatePreallocated</b> method creates a framework memory object for a driver-supplied memory buffer. 


## -syntax


````
NTSTATUS WdfMemoryCreatePreallocated(
  _In_opt_ PWDF_OBJECT_ATTRIBUTES Attributes,
  _In_     PVOID                  Buffer,
  _In_     size_t                 BufferSize,
  _Out_    WDFMEMORY              *Memory
);
````


## -parameters




### -param Attributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the new memory object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Buffer [in]

A pointer to a driver-supplied buffer.


### -param BufferSize [in]

The nonzero size, in bytes, of the buffer that <i>Buffer</i> points to.


### -param Memory [out]

A pointer to a location that receives a handle to the new memory object.


## -returns


<b>WdfMemoryCreatePreallocated</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
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

For a list of other return values that the <b>WdfMemoryCreatePreallocated</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



## -remarks


The <b>WdfMemoryCreatePreallocated</b> method creates a framework memory object for a buffer that the driver has previously allocated or obtained. 

Your driver can call <b>WdfMemoryCreatePreallocated</b> if you need to create memory objects that represent pre-existing memory buffers. For example, the driver might receive a driver-defined structure within a buffer for an I/O request that contains an internal I/O control code. The driver can call <b>WdfMemoryCreatePreallocated</b> to create a memory object so that the driver can pass the structure to an I/O target. 

After a driver has called <b>WdfMemoryCreatePreallocated</b>, the driver can call <a href="..\wdfmemory\nf-wdfmemory-wdfmemoryassignbuffer.md">WdfMemoryAssignBuffer</a> to assign a different buffer to the memory object that <b>WdfMemoryCreatePreallocated</b> created.

The default parent object for each memory object is the framework driver object that represents the driver that called <b>WdfMemoryCreatePreallocated</b>. If your driver creates a memory object that it uses with a specific device object, request object, or other framework object, it should set the memory object's parent appropriately. The memory object will be deleted when the parent object is deleted. If you do not change the default parent object, the memory object will remain in memory until the I/O manager unloads your driver.

A driver can also delete a memory object by calling <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>.

When the framework memory object that <b>WdfMemoryCreatePreallocated</b> created is deleted, the framework does not deallocate the pre-existing buffer. Likewise, a call to <a href="..\wdfmemory\nf-wdfmemory-wdfmemoryassignbuffer.md">WdfMemoryAssignBuffer</a> does not deallocate the previously assigned buffer.

For more information about framework memory objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.



## -see-also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatefromlookaside.md">WdfMemoryCreateFromLookaside</a>

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>

<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>

<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>

<a href="..\wdfmemory\nf-wdfmemory-wdfmemoryassignbuffer.md">WdfMemoryAssignBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfMemoryCreatePreallocated method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

