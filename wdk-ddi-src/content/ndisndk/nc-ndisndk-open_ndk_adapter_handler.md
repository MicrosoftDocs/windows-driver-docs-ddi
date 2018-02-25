---
UID: NC:ndisndk.OPEN_NDK_ADAPTER_HANDLER
title: OPEN_NDK_ADAPTER_HANDLER
author: windows-driver-content
description: The OpenNDKAdapterHandler (OPEN_NDK_ADAPTER_HANDLER) function opens an NDK adapter instance on an NDK-capable NDIS miniport adapter.
old-location: netvista\open_ndk_adapter_handler.htm
old-project: netvista
ms.assetid: 85888B9A-669C-478F-9318-EE9821BC3AF3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: OPEN_NDK_ADAPTER_HANDLER, OpenNdkAdapterHandler, OpenNdkAdapterHandler callback function [Network Drivers Starting with Windows Vista], ndisndk/OpenNdkAdapterHandler, netvista.open_ndk_adapter_handler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndisndk.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndisndk.h
apiname:
-	OpenNdkAdapterHandler
product: Windows
targetos: Windows
req.typenames: TCP_OFFLOAD_STATS, *PTCP_OFFLOAD_STATS
---

# OPEN_NDK_ADAPTER_HANDLER callback


## -description


The <i>OpenNDKAdapterHandler</i> (<i>OPEN_NDK_ADAPTER_HANDLER</i>) function opens an NDK adapter instance on an NDK-capable NDIS miniport adapter.


## -prototype


````
OPEN_NDK_ADAPTER_HANDLER OpenNdkAdapterHandler;

NDIS_STATUS OpenNdkAdapterHandler(
  _In_ NDIS_HANDLE                       MiniportAdapterContext,
  _In_ PNDIS_OPEN_NDK_ADAPTER_PARAMETERS Parameters,
       _Outptr_ NDK_ADAPTER              **ppNdkAdapter
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function. The miniport driver uses this context area to maintain state information for an NDIS miniport adapter.




### -param Parameters [in]

A pointer to an <a href="..\ndisndk\ns-ndisndk-_ndis_open_ndk_adapter_parameters.md">NDIS_OPEN_NDK_ADAPTER_PARAMETERS</a> structure that defines the input parameters to open an <a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a> instance.

The  <a href="..\ndisndk\ns-ndisndk-_ndis_open_ndk_adapter_parameters.md">NDIS_OPEN_NDK_ADAPTER_PARAMETERS</a> structure must specify the  NDKPI major version, and the lowest NDKPI minor version that the NDK consumer can support. 


If the provider does not support the consumer-specified major version, the provider must fail the request with  NDIS_STATUS_BAD_VERSION. 

If the provider supports the consumer-specified major version and the specified minor version is less than or equal to the highest minor version that the provider supports, the provider must succeed the request and use the highest minor version that     the provider supports.

 For example, if the consumer requests version 1.0, and the provider supports 1.1, the provider must report version  1.1  in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure and  NDK object headers. 

<div class="alert"><b>Note</b>  Higher minor versions at the provider are always fully backward-compatible with (that is, a superset of) lower minor versions. </div>
<div> </div>
If the provider supports the consumer-specified major version and the specified minor version is greater than the highest minor version that the provider supports, the provider must fail the request with NDIS_STATUS_BAD_VERSION.


#### - **ppNdkAdapter

A pointer to a variable that holds the pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a> structure. On return from  <i>OPEN_NDK_ADAPTER_HANDLER</i>, the <b>NDK_ADAPTER</b> structure referenced by  <i>ppNdkAdapter</i> identifies the newly opened NDK adapter instance. 


#### - ppNdkAdapter

A pointer to a variable that holds the pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a> structure. On return from  <i>OPEN_NDK_ADAPTER_HANDLER</i>, the <b>NDK_ADAPTER</b> structure referenced by  <i>ppNdkAdapter</i> identifies the newly opened NDK adapter instance. 


## -returns



<i>OPEN_NDK_ADAPTER_HANDLER</i> can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The NDK adapter instance was successfully opened.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
The requested version number is not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_ADAPTER_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The NDK functionality of the miniport adapter is not enabled.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
NDIS was unable to open the NDK adapter due to insufficient resources.

</td>
</tr>
</table>
 




## -remarks



<i>OPEN_NDK_ADAPTER_HANDLER</i> opens an <a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a> instance on an NDK-capable NDIS miniport adapter.
Multiple <b>NDK_ADAPTER</b> instances can be created on the same NDIS miniport adapter. Each <b>NDK_ADAPTER</b> instance contains a pointer to a table of dispatch  functions that implement the NDK application programming interface.
The miniport driver calls the <a href="..\ndisndk\nc-ndisndk-close_ndk_adapter_handler.md">CLOSE_NDK_ADAPTER_HANDLER</a> function to close the  NDK adapter instance and release the associated resources.




## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>



<a href="..\ndisndk\nc-ndisndk-close_ndk_adapter_handler.md">CLOSE_NDK_ADAPTER_HANDLER</a>



<a href="..\ndisndk\ns-ndisndk-_ndis_open_ndk_adapter_parameters.md">NDIS_OPEN_NDK_ADAPTER_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20OPEN_NDK_ADAPTER_HANDLER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

