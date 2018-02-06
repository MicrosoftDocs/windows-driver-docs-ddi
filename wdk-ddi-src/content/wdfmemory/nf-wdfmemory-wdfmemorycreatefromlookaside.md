---
UID: NF:wdfmemory.WdfMemoryCreateFromLookaside
title: WdfMemoryCreateFromLookaside function
author: windows-driver-content
description: The WdfMemoryCreateFromLookaside method creates a framework memory object and obtains a memory buffer from a specified lookaside list.
old-location: wdf\wdfmemorycreatefromlookaside.htm
old-project: wdf
ms.assetid: aeafa20c-e4be-4b6d-88b7-22b84ef4cedd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdfmemorycreatefromlookaside, PFN_WDFMEMORYCREATEFROMLOOKASIDE, WdfMemoryCreateFromLookaside method, WdfMemoryCreateFromLookaside, DFMemoryObjectRef_0eabcdc7-a75d-49bf-9fe4-775748fca8bf.xml, wdfmemory/WdfMemoryCreateFromLookaside, wdf.wdfmemorycreatefromlookaside
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfMemoryCreateFromLookaside
product: Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---

# WdfMemoryCreateFromLookaside function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfMemoryCreateFromLookaside</b> method creates a framework memory object and obtains a memory buffer from a specified lookaside list.


## -syntax


````
NTSTATUS WdfMemoryCreateFromLookaside(
  _In_  WDFLOOKASIDE Lookaside,
  _Out_ WDFMEMORY    *Memory
);
````


## -parameters




### -param Lookaside [in]

A handle to a framework lookaside-list object that is obtained by calling <a href="..\wdfmemory\nf-wdfmemory-wdflookasidelistcreate.md">WdfLookasideListCreate</a>.


### -param Memory [out]

A pointer to a location that receives a handle to the new framework memory object.


## -returns


<b>WdfMemoryCreateFromLookaside</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method return one of the following values:
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

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


After your driver calls <a href="..\wdfmemory\nf-wdfmemory-wdflookasidelistcreate.md">WdfLookasideListCreate</a> to create a lookaside-list object, the driver can call <b>WdfMemoryCreateFromLookaside</b> to obtain a buffer from the lookaside list. 

The framework provides a handle to a memory object that represents the buffer. When the framework creates the memory object, it uses object attributes that the driver supplied when it called <b>WdfMemoryCreateFromLookaside</b>.

When your driver has finished using a memory object that it obtained from a lookaside list, the driver must call <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a> to return the memory object to the lookaside list.

For more information about framework memory objects and lookaside lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

If lookaside-list buffers are being allocated from the pageable memory pool, the <b>WdfMemoryCreateFromLookaside</b> method must be called at IRQL &lt;= APC_LEVEL. Otherwise, the method can be called at IRQL &lt;= DISPATCH_LEVEL.



## -see-also

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>

<a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>

<a href="..\wdfmemory\nf-wdfmemory-wdflookasidelistcreate.md">WdfLookasideListCreate</a>

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfMemoryCreateFromLookaside method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

