---
UID: NF:ndis.NdisAllocateNetBufferPool
title: NdisAllocateNetBufferPool function
author: windows-driver-content
description: Call the NdisAllocateNetBufferPool function to allocate a pool of NET_BUFFER structures.
old-location: netvista\ndisallocatenetbufferpool.htm
old-project: netvista
ms.assetid: bc27758a-a793-48a1-a6ab-bd193aa9c61a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis_netbuf_functions_ref_f12d38a1-161d-4209-95ea-6e66fcbef255.xml, NdisAllocateNetBufferPool function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateNetBufferPool, netvista.ndisallocatenetbufferpool, NdisAllocateNetBufferPool
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisAllocateNetBufferPool
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateNetBufferPool function


## -description


Call the
  <b>NdisAllocateNetBufferPool</b> function to allocate a pool of 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures.


## -syntax


````
NDIS_HANDLE NdisAllocateNetBufferPool(
  _In_opt_ NDIS_HANDLE                 NdisHandle,
  _In_     PNET_BUFFER_POOL_PARAMETERS Parameters
);
````


## -parameters




### -param NdisHandle [in, optional]

An NDIS handle that was obtained during caller initialization.


### -param Parameters [in]

A pointer to a NET_BUFFER_POOL_PARAMETERS structure that defines the parameters for the pool. The
     structure is defined as follows:
     

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _NET_BUFFER_POOL_PARAMETERS {
  NDIS_OBJECT_HEADER  Header;
  ULONG  PoolTag;
  ULONG  DataSize;
} NET_BUFFER_POOL_PARAMETERS, *PNET_BUFFER_POOL_PARAMETERS;</pre>
</td>
</tr>
</table></span></div>
This structure includes the following members:





#### Header

The 
       <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
       NET_BUFFER_POOL_PARAMETERS structure. Set the 
       <b>Type</b> member of the structure that 
       <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
       <b>Revision</b> member to NET_BUFFER_POOL_PARAMETERS_REVISION_1, and the 
       <b>Size</b> member to NDIS_SIZEOF_NET_BUFFER_POOL_PARAMETERS_REVISION_1.



#### PoolTag

A kernel pool tag that the caller uses when it allocates 
       <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures from this pool. The tag
       is a string, delimited by single quotation marks, with up to four characters, usually specified in
       reverse order. The kernel pool tag helps NDIS to identify the owner of the NET_BUFFER structures that
       are allocated from this pool.



#### DataSize

The default data size for data buffers associated with this pool. The caller must set this value
       if it calls the 
       <a href="..\ndis\nf-ndis-ndisallocatenetbuffermdlanddata.md">
       NdisAllocateNetBufferMdlAndData</a> function. NDIS uses this value to set the size of the data
       buffer that it allocates for the NET_BUFFER structure. If the caller does not use this feature, this
       value should be set to zero.


## -returns



<b>NdisAllocateNetBufferPool</b> returns a handle to the NET_BUFFER structure pool that NDIS allocates.
     If the allocation was unsuccessful, this handle is <b>NULL</b>. This handle is a required parameter in
     subsequent calls to NDIS functions that allocate and free NET_BUFFER structures from this pool.




## -remarks



Call the following functions to allocate 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures from the NET_BUFFER
    structure pool.


<a href="..\ndis\nf-ndis-ndisallocatenetbuffer.md">NdisAllocateNetBuffer</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbuffermdlanddata.md">
       NdisAllocateNetBufferMdlAndData</a>


<div class="alert"><b>Note</b>  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> and 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures must be allocated
    from an NDIS buffer pool. A driver must not allocate and initialize a NET_BUFFER or NET_BUFFER_LIST
    structure from its private memory pool or the stack.</div>
<div> </div>
You can call 
    <b>NdisAllocateNetBufferPool</b> and set the 
    <b>DataSize</b> value when creating a NET_BUFFER structure pool. In this case, MDL and data are
    preallocated with each NET_BUFFER structure that the caller allocates from the pool. You must call the 
    <b>NdisAllocateNetBufferMdlAndData</b> function to allocate NET_BUFFER structures from such a pool.

MDL and data buffers that are allocated with 
    <b>NdisAllocateNetBufferMdlAndData</b> should not be freed separate from the NET_BUFFER structure. Such
    structures are freed with the NET_BUFFER structure when you call the 
    <a href="..\ndis\nf-ndis-ndisfreenetbuffer.md">NdisFreeNetBuffer</a> function.

Call the 
    <a href="..\ndis\nf-ndis-ndisfreenetbufferpool.md">NdisFreeNetBufferPool</a> function to
    free NET_BUFFER structure pools that are created with 
    <b>NdisAllocateNetBufferPool</b>.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nf-ndis-ndisfreenetbuffer.md">NdisFreeNetBuffer</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbuffer.md">NdisAllocateNetBuffer</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbuffermdlanddata.md">
   NdisAllocateNetBufferMdlAndData</a>



<a href="..\ndis\nf-ndis-ndisfreenetbufferpool.md">NdisFreeNetBufferPool</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateNetBufferPool function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

