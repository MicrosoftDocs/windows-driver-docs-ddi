---
UID: NF:wdfmemory.WdfMemoryCreateFromLookaside
title: WdfMemoryCreateFromLookaside function (wdfmemory.h)
description: The WdfMemoryCreateFromLookaside method creates a framework memory object and obtains a memory buffer from a specified lookaside list.
old-location: wdf\wdfmemorycreatefromlookaside.htm
tech.root: wdf
ms.assetid: aeafa20c-e4be-4b6d-88b7-22b84ef4cedd
ms.date: 02/26/2018
ms.keywords: DFMemoryObjectRef_0eabcdc7-a75d-49bf-9fe4-775748fca8bf.xml, WdfMemoryCreateFromLookaside, WdfMemoryCreateFromLookaside method, kmdf.wdfmemorycreatefromlookaside, wdf.wdfmemorycreatefromlookaside, wdfmemory/WdfMemoryCreateFromLookaside
f1_keywords:
 - "wdfmemory/WdfMemoryCreateFromLookaside"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfMemoryCreateFromLookaside
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfMemoryCreateFromLookaside function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfMemoryCreateFromLookaside</b> method creates a framework memory object and obtains a memory buffer from a specified lookaside list.


## -parameters




### -param Lookaside [in]

A handle to a framework lookaside-list object that is obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdflookasidelistcreate">WdfLookasideListCreate</a>.


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
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After your driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdflookasidelistcreate">WdfLookasideListCreate</a> to create a lookaside-list object, the driver can call <b>WdfMemoryCreateFromLookaside</b> to obtain a buffer from the lookaside list. 

The framework provides a handle to a memory object that represents the buffer. When the framework creates the memory object, it uses object attributes that the driver supplied when it called <b>WdfMemoryCreateFromLookaside</b>.

When your driver has finished using a memory object that it obtained from a lookaside list, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a> to return the memory object to the lookaside list.

For more information about framework memory objects and lookaside lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

If lookaside-list buffers are being allocated from the pageable memory pool, the <b>WdfMemoryCreateFromLookaside</b> method must be called at IRQL <= APC_LEVEL. Otherwise, the method can be called at IRQL <= DISPATCH_LEVEL.


#### Examples

The following code example creates a lookaside list and stores the list's handle in driver-defined device object context space. Then, the driver obtains a buffer from the lookaside list.

```cpp
PDRIVER_CONTEXT  driverContext;
WDFMEMORY  memHandle;

driverContext = GetDriverContext(driver);

status = WdfLookasideListCreate(
                                WDF_NO_OBJECT_ATTRIBUTES,
                                sizeof(MY_LOOKASIDE_BUFFER),
                                NonPagedPool,
                                WDF_NO_OBJECT_ATTRIBUTES,
                                MY_POOL_TAG,
                                &driverContext->LookasideListHandle
                                );
...
status = WdfMemoryCreateFromLookaside(
                                      driverContext->LookasideListHandle,
                                      &memHandle
                                      );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdflookasidelistcreate">WdfLookasideListCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a>
 

 

