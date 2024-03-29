---
UID: NS:ndkpi._NDK_LOGICAL_ADDRESS_MAPPING
title: _NDK_LOGICAL_ADDRESS_MAPPING (ndkpi.h)
description: The NDK_LOGICAL_ADDRESS_MAPPING structure contains an array of adapter logical addresses.
old-location: netvista\ndk_logical_address_mapping.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_LOGICAL_ADDRESS_MAPPING structure"]
ms.keywords: NDK_LOGICAL_ADDRESS_MAPPING, NDK_LOGICAL_ADDRESS_MAPPING structure [Network Drivers Starting with Windows Vista], PNDK_LOGICAL_ADDRESS_MAPPING, PNDK_LOGICAL_ADDRESS_MAPPING structure pointer [Network Drivers Starting with Windows Vista], _NDK_LOGICAL_ADDRESS_MAPPING, ndkpi/NDK_LOGICAL_ADDRESS_MAPPING, ndkpi/PNDK_LOGICAL_ADDRESS_MAPPING, netvista.ndk_logical_address_mapping
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
req.irql: 
targetos: Windows
req.typenames: NDK_LOGICAL_ADDRESS_MAPPING
f1_keywords:
 - _NDK_LOGICAL_ADDRESS_MAPPING
 - ndkpi/_NDK_LOGICAL_ADDRESS_MAPPING
 - NDK_LOGICAL_ADDRESS_MAPPING
 - ndkpi/NDK_LOGICAL_ADDRESS_MAPPING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - _NDK_LOGICAL_ADDRESS_MAPPING
 - NDK_LOGICAL_ADDRESS_MAPPING
---

# _NDK_LOGICAL_ADDRESS_MAPPING structure


## -description

The <b>NDK_LOGICAL_ADDRESS_MAPPING</b> structure contains an array of adapter logical addresses.

## -struct-fields

### -field AdapterContext

Reserved for the NDK provider's use. The NDK consumer must not modify this member.

### -field AdapterPageCount

	The number of entries in the array that is specified in the  <b>AdapterPageArray</b> member.

### -field AdapterPageArray

An array of adapter logical addresses. Each logical address in the array corresponds to a page, of <b>PAGE_SIZE</b> bytes in length, and must be <b>PAGE_SIZE</b>-aligned. The array of pages correspond to a virtually contiguous memory region.
The <b>NDK_LOGICAL_ADDRESS</b> datatype is defined as follows:

<pre class="syntax"><code>typedef PHYSICAL_ADDRESS NDK_LOGICAL_ADDRESS;</code></pre>

## -remarks

<b>NDK_LOGICAL_ADDRESS_MAPPING</b> represents an adapter's view of physical memory. See <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_build_lam">NDK_FN_BUILD_LAM</a> and <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_release_lam">NDK_FN_RELEASE_LAM</a> for more information.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_build_lam">NDK_FN_BUILD_LAM</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_release_lam">NDK_FN_RELEASE_LAM</a>

