---
UID: NC:ndkpi.NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN
title: NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN
author: windows-driver-content
description: The NdkGetPrivilegedMemoryRegionToken (NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN) function gets an NDK privileged memory region token.
old-location: netvista\ndk_fn_get_privileged_memory_region_token.htm
old-project: netvista
ms.assetid: A6295FEE-3633-42E7-A2EA-BA0D3C9E4101
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_get_privileged_memory_region_token, NdkGetPrivilegedMemoryRegionToken callback function [Network Drivers Starting with Windows Vista], NdkGetPrivilegedMemoryRegionToken, NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN, NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN, ndkpi/NdkGetPrivilegedMemoryRegionToken
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
-	NdkGetPrivilegedMemoryRegionToken
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS"
---

# NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN callback


## -description


The <i>NdkGetPrivilegedMemoryRegionToken</i> (<i>NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN</i>) function gets an NDK privileged  memory region token.


## -prototype


````
NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN NdkGetPrivilegedMemoryRegionToken;

VOID NdkGetPrivilegedMemoryRegionToken(
  _In_  NDK_PD *pNdkPd,
  _Out_ UINT32 *pToken
)
{ ... }
````


## -parameters




### -param *pNdkPd [in]

A pointer to an NDK protection domain (PD) object (<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>).


### -param *pToken [out]

A memory token value is returned in this location.


## -returns



None




## -remarks



<i>NdkGetPrivilegedMemoryRegionToken</i> gets a privileged  memory region token value that allows adapter logical addresses  to be used directly without memory registration. This token must provide LOCAL_READ and LOCAL_WRITE access. A provider must never allow remote access for the privileged memory region token.




## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

