---
UID: NC:ndkpi.NDK_FN_REGISTER_MR
title: NDK_FN_REGISTER_MR
author: windows-driver-content
description: The NdkRegisterMr (NDK_FN_REGISTER_MR) function registers a virtually contiguous memory region with an NDK adapter.
old-location: netvista\ndk_fn_register_mr.htm
old-project: netvista
ms.assetid: 082BBDE1-1B80-4306-96A1-DCD23910B0F7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_register_mr, NdkRegisterMr callback function [Network Drivers Starting with Windows Vista], NdkRegisterMr, NDK_FN_REGISTER_MR, NDK_FN_REGISTER_MR, ndkpi/NdkRegisterMr, NDK_MR_FLAG_ALLOW_LOCAL_READ, NDK_MR_FLAG_ALLOW_LOCAL_WRITE, NDK_MR_FLAG_ALLOW_REMOTE_READ, NDK_MR_FLAG_ALLOW_REMOTE_WRITE, NDK_MR_FLAG_RDMA_READ_SINK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndkpi.h
apiname:
-	NdkRegisterMr
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_REGISTER_MR callback


## -description


The <i>NdkRegisterMr</i> (<i>NDK_FN_REGISTER_MR</i>) function registers a virtually contiguous memory region with an NDK adapter.


## -prototype


````
NDK_FN_REGISTER_MR NdkRegisterMr;

NTSTATUS NdkRegisterMr(
  _In_     NDK_MR                    *pNdkMr,
  _In_     MDL                       *Mdl,
  _In_     SIZE_T                    Length,
  _In_     ULONG                     Flags,
  _In_     NDK_FN_REQUEST_COMPLETION RequestCompletion,
  _In_opt_ PVOID                     RequestContext
)
{ ... }
````


## -parameters




#### - *pNdkMr [in]

A pointer to an NDK memory region (MR) object
(<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>).


#### - *Mdl [in]

An MDL or chain of MDLs that represent a virtually contiguous memory region from the starting virtual address up to the number of bytes specified in the <i>Length</i> parameter.



#### - Length [in]

The number of bytes to register starting from the first MDL's virtual address. The first MDL's virtual address can be obtained by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a> macro. The length must not exceed the total number of bytes represented by the MDL chain.


#### - Flags [in]

A bitmask of flags that specify the access permissions for the registered memory region. The following flags can be set:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDK_MR_FLAG_ALLOW_LOCAL_READ"></a><a id="ndk_mr_flag_allow_local_read"></a><dl>
<dt><b>NDK_MR_FLAG_ALLOW_LOCAL_READ</b></dt>
<dt>0x00000000</dt>
</dl>
</td>
<td width="60%"></td>
</tr>
<tr>
<td width="40%"><a id="NDK_MR_FLAG_ALLOW_LOCAL_WRITE"></a><a id="ndk_mr_flag_allow_local_write"></a><dl>
<dt><b>NDK_MR_FLAG_ALLOW_LOCAL_WRITE</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%"></td>
</tr>
<tr>
<td width="40%"><a id="NDK_MR_FLAG_ALLOW_REMOTE_READ"></a><a id="ndk_mr_flag_allow_remote_read"></a><dl>
<dt><b>NDK_MR_FLAG_ALLOW_REMOTE_READ</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%"></td>
</tr>
<tr>
<td width="40%"><a id="NDK_MR_FLAG_ALLOW_REMOTE_WRITE"></a><a id="ndk_mr_flag_allow_remote_write"></a><dl>
<dt><b>NDK_MR_FLAG_ALLOW_REMOTE_WRITE</b></dt>
<dt>0x00000005</dt>
</dl>
</td>
<td width="60%"></td>
</tr>
<tr>
<td width="40%"><a id="NDK_MR_FLAG_RDMA_READ_SINK"></a><a id="ndk_mr_flag_rdma_read_sink"></a><dl>
<dt><b>NDK_MR_FLAG_RDMA_READ_SINK</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%"></td>
</tr>
</table> 


#### - RequestCompletion [in]

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).


#### - RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


#### - pNdkMr [in]

A pointer to an NDK memory region (MR) object
(<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>).


#### - Mdl [in]

An MDL or chain of MDLs that represent a virtually contiguous memory region from the starting virtual address up to the number of bytes specified in the <i>Length</i> parameter.



## -returns


The 
     <i>NdkRegisterMr</i> function returns one of the following NTSTATUS codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The MR registration was completed successfully.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The part of the MDL chain from the starting virtual address up to the length in bytes does not represent a virtually contiguous memory region. 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The request failed due to insufficient resources. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table> 



## -remarks


On an <a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a> object that was created with  the <i>FastRegister</i> parameter set to FALSE, <i>NdkRegisterMr</i> is used to register a virtually contiguous memory region with the adapter. 

The NDK consumer must pass an MDL or chain of MDLs that represent virtually contiguous memory region that is pinned in physical memory. The base virtual address for the memory region being registered is the virtual address indicated by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a> macro. If the MDL chain does not represent a virtually contiguous memory region from the starting virtual address up to the specified length in bytes, the NDK provider must fail the request.

The provider must treat the virtual  address that <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a> returns as an index to the start of the memory region being registered. The provider must not use the virtual address as a valid virtual address for reading or writing buffer contents.

The NDK consumer must not use the MDL chain while the registration request is pending.

<i>NdkRegisterMr</i> does not support zero-based virtual addresses.

An NDK consumer must pass the <b>NDK_MR_FLAG_RDMA_READ_SINK</b> flag when it registers memory that might be used as the sink buffer for an RDMA read request. Certain NDK providers might require enabling special access rights on the sink buffer for an RDMA read request on adapters for which the <b>NDK_ADAPTER_FLAG_RDMA_READ_SINK_NOT_REQUIRED</b> flag is not set in the <b>AdapterFlags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure. The <b>NDK_MR_FLAG_RDMA_READ_SINK</b> flag allows such providers to support registration requests appropriately. 
<div class="alert"><b>Note</b>  Buffers can be registered for multiple purposes.  Therefore, the <b>NDK_MR_FLAG_RDMA_READ_SINK</b> flag might be accompanied by other flags. </div><div> </div>If an NDK consumer passes the <b>NDK_MR_FLAG_RDMA_READ_SINK</b> flag on an adapter for which the <b>NDK_ADAPTER_FLAG_RDMA_READ_SINK_NOT_REQUIRED</b> flag is set in the <b>AdapterFlags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure, the provider is not required to handle the <b>NDK_MR_FLAG_RDMA_READ_SINK</b> flag and must not fail the request  due to the presence of this flag.

To deregister the memory region, use the <i>NdkDeregisterMr</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_deregister_mr.md">NDK_FN_DEREGISTER_MR</a>) function.



## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>

<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_deregister_mr.md">NDK_FN_DEREGISTER_MR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_REGISTER_MR callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

