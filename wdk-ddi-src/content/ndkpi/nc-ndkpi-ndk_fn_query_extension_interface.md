---
UID: NC:ndkpi.NDK_FN_QUERY_EXTENSION_INTERFACE
title: NDK_FN_QUERY_EXTENSION_INTERFACE (ndkpi.h)
description: The NdkQqueryExtensionInterface (NDK_FN_QUERY_EXTENSION_INTERFACE) function gets information about an NDK extension interface.
old-location: netvista\ndk_fn_query_extension_interface.htm
tech.root: netvista
ms.assetid: 439C990E-6978-4D0F-8453-6EB2FED1DB77
ms.date: 05/02/2018
keywords: ["NDK_FN_QUERY_EXTENSION_INTERFACE callback function"]
ms.keywords: NDK_FN_QUERY_EXTENSION_INTERFACE, NDK_FN_QUERY_EXTENSION_INTERFACE callback, NdkQqueryExtensionInterface, NdkQqueryExtensionInterface callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkQqueryExtensionInterface, netvista.ndk_fn_query_extension_interface
f1_keywords:
 - "ndkpi/NdkQqueryExtensionInterface"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndkpi.h
api_name:
- NdkQqueryExtensionInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_QUERY_EXTENSION_INTERFACE callback function


## -description


The <i>NdkQqueryExtensionInterface</i> (<i>NDK_FN_QUERY_EXTENSION_INTERFACE</i>) function gets information about an NDK extension interface.


## -parameters




### -param pNdkObject [in]

	A pointer to the object header (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>) for the object being queried.


### -param ExtensionInterfaceID [in]

A pointer to the GUID that identifies the extension interface.


### -param ExtensionInterfaceVersion [in]

	The requested version (<a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-ndk_version">NDK_VERSION</a>) of the extension interface.



### -param pExtensionInterface [out]

A pointer to an   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_extension_interface">NDK_EXTENSION_INTERFACE</a> structure that the provider  initialized if the function returns STATUS_SUCCESS.


## -returns



The <i>NdkQqueryExtensionInterface</i> function returns one of the following NTSTATUS codes.

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
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The function is not supported.

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



Each NDK object contains an <i>NdkQqueryExtensionInterface</i> (<i>NDK_FN_QUERY_EXTENSION_INTERFACE</i>) function pointer in its object type-specific function dispatch table.  <i>NdkQqueryExtensionInterface</i> queries extended interfaces that are supported by the object type. There are currently no standard extended interfaces defined. An extension interface is identified by a GUID and represented as a pointer to a function dispatch table.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter_dispatch">NDK_ADAPTER_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq_dispatch">NDK_CQ_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_extension_interface">NDK_EXTENSION_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-ndk_version">NDK_VERSION</a>
 

 

