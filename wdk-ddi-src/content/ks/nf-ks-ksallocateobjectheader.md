---
UID: NF:ks.KsAllocateObjectHeader
title: KsAllocateObjectHeader function (ks.h)
description: The KsAllocateObjectHeader function initializes the required file context header.
old-location: stream\ksallocateobjectheader.htm
tech.root: stream
ms.assetid: 18f5ea44-3f70-4c26-beb3-2f03568df03b
ms.date: 04/23/2018
ms.keywords: KsAllocateObjectHeader, KsAllocateObjectHeader function [Streaming Media Devices], ks/KsAllocateObjectHeader, ksfunc_0ab53e6c-a934-4c4a-9377-c81ec37833f6.xml, stream.ksallocateobjectheader
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAllocateObjectHeader
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAllocateObjectHeader function


## -description


The <b>KsAllocateObjectHeader</b> function initializes the required file context 
   header.


## -parameters




### -param Header [out]

Points to the caller-allocated location in which to return a pointer to the initialized 
      <b>KSOBJECT_HEADER</b> if successful. 


### -param ItemsCount [in]

Specifies the number of object create items in the <i>ItemsList</i> to be added to the 
      object header once the header is allocated. This value should be zero if <i>ItemsList</i> is 
      <b>NULL</b>.


### -param ItemsList [in, optional]

Optionally specifies a pointer to a caller-allocated buffer containing a series of 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff563479">KSOBJECT_CREATE_ITEM</a> structures to be added to 
      the object header. Must be set to <b>NULL</b> if there are no object create items.


### -param Irp [in]

Points to the IRP, of major function <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>, 
      that contains the necessary information to complete the creation of the object header.


### -param Table [in]

Points to an initialized dispatch table for this file object.


## -returns



The <b>KsAllocateObjectHeader</b> function returns 
      <b>STATUS_SUCCESS</b> if successful or 
      <b>STATUS_INSUFFICIENT_RESOURCES</b> if not enough resources are available to fulfill the 
      request.




## -remarks



Before calling this routine the driver must allocate system-resident storage for a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561723">KSDISPATCH_TABLE</a> and initialize the dispatch table. 
     The memory for this dispatch table cannot be released until <b>KsFreeObjectHeader</b> 
     is called.

<b>KsAllocateObjectHeader</b> allocates the memory for the 
      <b>KSOBJECT_HEADER</b> structure and returns a pointer to the header at 
       <i>Header</i>. Drivers must not attempt to free the memory themselves, but rather call 
       <b>KsFreeObjectHeader</b> when all operations requiring this object header have been 
       completed.

If subobjects exist for a given device, the driver must, before calling 
     <b>KsAllocateObjectHeader</b>, allocate a buffer of either paged or nonpaged memory of 
     sufficient size to hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563479">KSOBJECT_CREATE_ITEM</a> 
     structure for each subobject. For example:

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>/* Allocate a buffer for 4 subobjects for a given streaming device */
PKSOBJECT_CREATE_ITEM createBuffer ;
ULONG bufferSize  = (sizeof (KSOBJECT_CREATE_ITEM)) * 4 ;
 
createBuffer = (PKSOBJECT_CREATE_ITEM)
               ExAllocatePoolWithTag (PagedPool, bufferSize) ;
 </pre>
</td>
</tr>
</table></span></div>
Drivers must not free the memory allocated for the subobject 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563479">KSOBJECT_CREATE_ITEM</a> list until after calling 
     <b>KsFreeDeviceHeader</b>. Failure to do so can result in a bug check condition.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563479">KSOBJECT_CREATE_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562560">KsFreeDeviceHeader</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562565">KsFreeObjectHeader</a>
 

 

