---
UID: NS:ndkpi._NDK_LOGICAL_ADDRESS_MAPPING
title: "_NDK_LOGICAL_ADDRESS_MAPPING"
author: windows-driver-content
description: The NDK_LOGICAL_ADDRESS_MAPPING structure contains an array of adapter logical addresses.
old-location: netvista\ndk_logical_address_mapping.htm
old-project: netvista
ms.assetid: 7FB34813-5F89-4B9C-9594-B23E7D4736C6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDK_LOGICAL_ADDRESS_MAPPING structure pointer [Network Drivers Starting with Windows Vista], PNDK_LOGICAL_ADDRESS_MAPPING, netvista.ndk_logical_address_mapping, ndkpi/PNDK_LOGICAL_ADDRESS_MAPPING, NDK_LOGICAL_ADDRESS_MAPPING, _NDK_LOGICAL_ADDRESS_MAPPING, ndkpi/NDK_LOGICAL_ADDRESS_MAPPING, NDK_LOGICAL_ADDRESS_MAPPING structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	HeaderDef
apilocation:
-	ndkpi.h
apiname:
-	NDK_LOGICAL_ADDRESS_MAPPING
product: Windows
targetos: Windows
req.typenames: NDK_LOGICAL_ADDRESS_MAPPING
---

# _NDK_LOGICAL_ADDRESS_MAPPING structure


## -description


The <b>NDK_LOGICAL_ADDRESS_MAPPING</b> structure contains an array of adapter logical addresses.


## -syntax


````
typedef struct _NDK_LOGICAL_ADDRESS_MAPPING {
  PVOID               AdapterContext;
  ULONG               AdapterPageCount;
  NDK_LOGICAL_ADDRESS AdapterPageArray[1];
} NDK_LOGICAL_ADDRESS_MAPPING, *PNDK_LOGICAL_ADDRESS_MAPPING;
````


## -struct-fields




### -field AdapterContext

Reserved for the NDK provider's use. The NDK consumer must not modify this member.


### -field AdapterPageCount

	The number of entries in the array that is specified in the  <b>AdapterPageArray</b> member.



### -field AdapterPageArray

An array of adapter logical addresses. Each logical address in the array corresponds to a page, of <b>PAGE_SIZE</b> bytes in length, and must be <b>PAGE_SIZE</b>-aligned. The array of pages correspond to a virtually contiguous memory region.
The <b>NDK_LOGICAL_ADDRESS</b> datatype is defined as follows:

<pre class="syntax" xml:space="preserve"><code>typedef PHYSICAL_ADDRESS NDK_LOGICAL_ADDRESS;</code></pre>

## -remarks



<b>NDK_LOGICAL_ADDRESS_MAPPING</b> represents an adapter's view of physical memory. See <a href="..\ndkpi\nc-ndkpi-ndk_fn_build_lam.md">NDK_FN_BUILD_LAM</a> and <a href="..\ndkpi\nc-ndkpi-ndk_fn_release_lam.md">NDK_FN_RELEASE_LAM</a> for more information.




## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_release_lam.md">NDK_FN_RELEASE_LAM</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_build_lam.md">NDK_FN_BUILD_LAM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_LOGICAL_ADDRESS_MAPPING structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

