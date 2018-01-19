---
UID: NF:ndis.NdisReadNetworkAddress
title: NdisReadNetworkAddress function
author: windows-driver-content
description: The NdisReadNetworkAddress function returns the software-configurable network address that was stored in the registry for a NIC when it was installed in the machine.
old-location: netvista\ndisreadnetworkaddress.htm
old-project: netvista
ms.assetid: 42519c60-6dc6-4c20-a2e8-954d9610a982
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisReadNetworkAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and later drivers in Windows Vista and later. Supported for NDIS 5.1 drivers (see    NdisReadNetworkAddress (NDIS   5.1)) in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisReadNetworkAddress
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisReadNetworkAddress function



## -description
The 
  <b>NdisReadNetworkAddress</b> function returns the software-configurable network address that was stored in
  the registry for a NIC when it was installed in the machine.



## -syntax

````
VOID NdisReadNetworkAddress(
  _Out_ PNDIS_STATUS Status,
  _Out_ PVOID        *NetworkAddress,
  _Out_ PUINT        NetworkAddressLength,
  _In_  NDIS_HANDLE  ConfigurationHandle
);
````


## -parameters

### -param Status [out]

A pointer to a caller-supplied variable in which this function returns the status of the call as
     one of the following:
     




### -param NDIS_STATUS_SUCCESS

The caller can use the address returned at 
       <i>NetworkAddress</i> for the NIC.


### -param NDIS_STATUS_FAILURE

There was no NIC address information available in the caller's registry 
       <b>Parameters</b> key or the value stored was not a string.

</dd>
</dl>

### -param NetworkAddress [out]

A pointer to a caller-supplied variable in which this function returns a pointer to a buffer that contains the
     network address (typically the MAC address), stored as a sequence of byte integers, if the call is successful.


### -param NetworkAddressLength [out]

A pointer to a caller-supplied variable in which this function returns the number of bytes that
     are returned at 
     <i>NetworkAddress</i>.


### -param ConfigurationHandle [in]

The configuration handle returned by the 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">
     NdisOpenConfigurationEx</a> function.


## -returns
None


## -remarks
<b>NdisReadNetworkAddress</b> searches the registry 
    <b>Parameters</b> key designated by the given 
    <i>ConfigurationHandle</i> for the keyword 
    <b>NetworkAddress</b>, converts the value of this string-type entry into a sequence of byte integers, and
    stores the requested information internally. The storage that NDIS allocates for such an address remains
    valid until the miniport driver calls the 
    <a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a> function,
    which frees the memory.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReadNetworkAddress function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

