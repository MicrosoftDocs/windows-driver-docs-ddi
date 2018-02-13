---
UID: NF:ks.KsAllocateObjectHeader
title: KsAllocateObjectHeader function
author: windows-driver-content
description: The KsAllocateObjectHeader function initializes the required file context header.
old-location: stream\ksallocateobjectheader.htm
old-project: stream
ms.assetid: 18f5ea44-3f70-4c26-beb3-2f03568df03b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsAllocateObjectHeader, ksfunc_0ab53e6c-a934-4c4a-9377-c81ec37833f6.xml, stream.ksallocateobjectheader, KsAllocateObjectHeader function [Streaming Media Devices], ks/KsAllocateObjectHeader
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsAllocateObjectHeader
product: Windows
targetos: Windows
req.typenames: 
---

# KsAllocateObjectHeader function


## -description


The <b>KsAllocateObjectHeader</b> function initializes the required file context 
   header.


## -syntax


````
NTSTATUS KsAllocateObjectHeader(
  _Out_          KSOBJECT_HEADER       *Header,
  _In_           ULONG                 ItemsCount,
  _In_opt_       PKSOBJECT_CREATE_ITEM ItemsList,
  _In_           PIRP                  Irp,
  _In_     const KSDISPATCH_TABLE      *Table
);
````


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
      <a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a> structures to be added to 
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
     <a href="..\ks\ns-ks-ksdispatch_table.md">KSDISPATCH_TABLE</a> and initialize the dispatch table. 
     The memory for this dispatch table cannot be released until <b>KsFreeObjectHeader</b> 
     is called.

<b>KsAllocateObjectHeader</b> allocates the memory for the 
      <b>KSOBJECT_HEADER</b> structure and returns a pointer to the header at 
       <i>Header</i>. Drivers must not attempt to free the memory themselves, but rather call 
       <b>KsFreeObjectHeader</b> when all operations requiring this object header have been 
       completed.

If subobjects exist for a given device, the driver must, before calling 
     <b>KsAllocateObjectHeader</b>, allocate a buffer of either paged or nonpaged memory of 
     sufficient size to hold a <a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a> 
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
     <a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a> list until after calling 
     <b>KsFreeDeviceHeader</b>. Failure to do so can result in a bug check condition.




## -see-also

<a href="..\ks\nf-ks-ksfreeobjectheader.md">KsFreeObjectHeader</a>



<a href="..\ks\nf-ks-ksfreedeviceheader.md">KsFreeDeviceHeader</a>



<a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsAllocateObjectHeader function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

