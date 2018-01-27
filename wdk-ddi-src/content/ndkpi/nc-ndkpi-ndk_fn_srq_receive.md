---
UID: NC:ndkpi.NDK_FN_SRQ_RECEIVE
title: NDK_FN_SRQ_RECEIVE
author: windows-driver-content
description: The NdkSrqReceive (NDK_FN_SRQ_RECEIVE) function posts a receive request on an NDK shared receive queue (SRQ).
old-location: netvista\ndk_fn_srq_receive.htm
old-project: netvista
ms.assetid: 1D615DEA-5599-4A3D-AEE7-BDBFE9D40C47
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_srq_receive, NdkSrqReceive callback function [Network Drivers Starting with Windows Vista], NdkSrqReceive, NDK_FN_SRQ_RECEIVE, NDK_FN_SRQ_RECEIVE, ndkpi/NdkSrqReceive
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
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	ndkpi.h
apiname: 
-	NdkSrqReceive
product: Windows
targetos: Windows
req.typenames: *PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_SRQ_RECEIVE callback


## -description


The <i>NdkSrqReceive</i> (<i>NDK_FN_SRQ_RECEIVE</i>) function posts a receive request on an NDK shared receive queue (SRQ).


## -prototype


````
NDK_FN_SRQ_RECEIVE NdkSrqReceive;

NTSTATUS NdkSrqReceive(
  _In_     NDK_SRQ                        *pNdkSrq,
  _In_opt_ PVOID                          RequestContext,
           _In_reads_(nSge) const NDK_SGE *pSgl,
  _In_     ULONG                          nSge
)
{ ... }
````


## -parameters




### -param *pNdkSrq



### -param RequestContext [in, optional]

A context value to be returned in the <b>RequestContext</b> member of the <a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a> structure for this request.



### -param NDK_SGE



### -param nSge [in]

The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.


#### - pSgl

An array of SGE structures (<a href="..\ndkpi\ns-ndkpi-_ndk_sge.md">NDK_SGE</a>) that represent the buffers to receive incoming data.



#### - pNdkSrq [in]

A pointer to an NDK shared receive queue (SRQ) object
(<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>).


## -returns


The 
     <i>NdkSrqReceive</i> function returns one of the following NTSTATUS codes.
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
The receive request was posted successfully. A completion entry will be queued to the completion queue (CQ) when the request is completed.


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


<i>NdkSrqReceive</i> posts a receive request to a shared receive queue (SRQ).



## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_sge.md">NDK_SGE</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_SRQ_RECEIVE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

