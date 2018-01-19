---
UID: NC:ndkpi.NDK_FN_REGISTER_MR
title: NDK_FN_REGISTER_MR
author: windows-driver-content
description: The NdkRegisterMr (NDK_FN_REGISTER_MR) function registers a virtually contiguous memory region with an NDK adapter.
old-location: netvista\ndk_fn_register_mr.htm
old-project: netvista
ms.assetid: 082BBDE1-1B80-4306-96A1-DCD23910B0F7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkRegisterMr
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
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

### -param pNdkMr [in]

A pointer to an NDK memory region (MR) object
(<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>).


### -param Mdl [in]

An MDL or chain of MDLs that represent a virtually contiguous memory region from the starting virtual address up to the number of bytes specified in the <i>Length</i> parameter.



### -param Length [in]

The number of bytes to register starting from the first MDL's virtual address. The first MDL's virtual address can be obtained by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a> macro. The length must not exceed the total number of bytes represented by the MDL chain.


### -param Flags [in]

A bitmask of flags that specify the access permissions for the registered memory region. The following flags can be set:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param NDK_MR_FLAG_ALLOW_LOCAL_READ
### -param 0x00000000

</td>
<td width="60%"></td>
</tr>
<tr>

### -param NDK_MR_FLAG_ALLOW_LOCAL_WRITE
### -param 0x00000001

</td>
<td width="60%"></td>
</tr>
<tr>

### -param NDK_MR_FLAG_ALLOW_REMOTE_READ
### -param 0x00000002

</td>
<td width="60%"></td>
</tr>
<tr>

### -param NDK_MR_FLAG_ALLOW_REMOTE_WRITE
### -param 0x00000005

</td>
<td width="60%"></td>
</tr>
<tr>

### -param NDK_MR_FLAG_RDMA_READ_SINK
### -param 0x00000008

</td>
<td width="60%"></td>
</tr>
</table>
 


### -param RequestCompletion [in]

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


## -returns
The 
     <i>NdkRegisterMr</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The MR registration was completed successfully.

<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl> The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The part of the MDL chain from the starting virtual address up to the length in bytes does not represent a virtually contiguous memory region. 

<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The request failed due to insufficient resources. 
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 


## -remarks
On an <a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a> object that was created with  the <i>FastRegister</i> parameter set to FALSE, <i>NdkRegisterMr</i> is used to register a virtually contiguous memory region with the adapter. 

The NDK consumer must pass an MDL or chain of MDLs that represent virtually contiguous memory region that is pinned in physical memory. The base virtual address for the memory region being registered is the virtual address indicated by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a> macro. If the MDL chain does not represent a virtually contiguous memory region from the starting virtual address up to the specified length in bytes, the NDK provider must fail the request.

The provider must treat the virtual  address that <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a> returns as an index to the start of the memory region being registered. The provider must not use the virtual address as a valid virtual address for reading or writing buffer contents.

The NDK consumer must not use the MDL chain while the registration request is pending.

<i>NdkRegisterMr</i> does not support zero-based virtual addresses.

An NDK consumer must pass the <b>NDK_MR_FLAG_RDMA_READ_SINK</b> flag when it registers memory that might be used as the sink buffer for an RDMA read request. Certain NDK providers might require enabling special access rights on the sink buffer for an RDMA read request on adapters for which the <b>NDK_ADAPTER_FLAG_RDMA_READ_SINK_NOT_REQUIRED</b> flag is not set in the <b>AdapterFlags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure. The <b>NDK_MR_FLAG_RDMA_READ_SINK</b> flag allows such providers to support registration requests appropriately. 

If an NDK consumer passes the <b>NDK_MR_FLAG_RDMA_READ_SINK</b> flag on an adapter for which the <b>NDK_ADAPTER_FLAG_RDMA_READ_SINK_NOT_REQUIRED</b> flag is set in the <b>AdapterFlags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure, the provider is not required to handle the <b>NDK_MR_FLAG_RDMA_READ_SINK</b> flag and must not fail the request  due to the presence of this flag.

To deregister the memory region, use the <i>NdkDeregisterMr</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_deregister_mr.md">NDK_FN_DEREGISTER_MR</a>) function.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_deregister_mr.md">NDK_FN_DEREGISTER_MR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_REGISTER_MR callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

