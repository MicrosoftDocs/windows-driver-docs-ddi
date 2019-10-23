---
UID: NF:ndis.NdisReadNetworkAddress
title: NdisReadNetworkAddress function (ndis.h)
description: The NdisReadNetworkAddress function returns the software-configurable network address that was stored in the registry for a NIC when it was installed in the machine.
old-location: netvista\ndisreadnetworkaddress.htm
tech.root: netvista
ms.assetid: 42519c60-6dc6-4c20-a2e8-954d9610a982
ms.date: 05/02/2018
ms.keywords: NdisReadNetworkAddress, NdisReadNetworkAddress function [Network Drivers Starting with Windows Vista], ndis/NdisReadNetworkAddress, ndis_configuration_ref_459fbfae-4235-4f60-9b10-02c60defc236.xml, netvista.ndisreadnetworkaddress
ms.topic: function
f1_keywords:
 - "ndis/NdisReadNetworkAddress"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and later drivers in Windows Vista and later. Supported for NDIS 5.1 drivers (see    NdisReadNetworkAddress (NDIS   5.1)) in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisReadNetworkAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisReadNetworkAddress function


## -description


The 
  <b>NdisReadNetworkAddress</b> function returns the software-configurable network address that was stored in
  the registry for a NIC when it was installed in the machine.


## -parameters




### -param Status [out]

A pointer to a caller-supplied variable in which this function returns the status of the call as
     one of the following:
     





#### NDIS_STATUS_SUCCESS

The caller can use the address returned at 
       <i>NetworkAddress</i> for the NIC.



#### NDIS_STATUS_FAILURE

There was no NIC address information available in the caller's registry 
       <b>Parameters</b> key or the value stored was not a string.


### -param NetworkAddress [out]

A pointer to a caller-supplied variable in which this function returns a pointer to a buffer that contains the
     network address (typically the MAC address), stored as a sequence of byte integers, if the call is successful.


### -param NetworkAddressLength [out]

A pointer to a caller-supplied variable in which this function returns the number of bytes that
     are returned at 
     <i>NetworkAddress</i>.


### -param ConfigurationHandle [in]

The configuration handle returned by the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationex">
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseconfiguration">NdisCloseConfiguration</a> function,
    which frees the memory.

The caller cannot use the variable at 
    <i>NetworkAddress</i> as a pointer unless 
    <b>NdisReadNetworkAddress</b> returns NDIS_STATUS_SUCCESS at 
    <i>Status</i>.

The installation program for a NIC that supports software-configurable network addressing should store
    a value entry named with the 
    <b>NetworkAddress</b> keyword in the 
    <b>HKLM\System\CurrentControlSet\Control\Class\{4d36e972...}\00<i>xx</i></b> key of the registry.

A NIC installer usually stores the value of a 
    <b>NetworkAddress</b> entry in the registry as a string of hexadecimal digits. Optionally, an installer
    can store such an address as a string of paired digits, with each pair separated from the next by a
    hyphen. 
    <b>NdisReadNetworkAddress</b> discards hyphens and converts each such pair into a single byte.

In either form, 
    <b>NdisReadNetworkAddress</b> converts the address specified as a string, one character at a time, into
    the equivalent integer until the string is exhausted.

In the registry of Windows 2000 and later versions, such an installed address string contains Unicode
    characters.

Note that NDIS does not validate the value at 
    <i>NetworkAddress</i>. NDIS does not guarantee that this value is a valid address, that the value has the
    proper length, or even that the value is a network address. The caller of 
    <b>NdisReadNetworkAddress</b> must therefore not make any assumptions about this value and must itself
    validate the value. If the caller determines that the value is out of bounds, it should not use the
    value; instead, it should use the permanent medium access control (MAC) address or a default address.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseconfiguration">NdisCloseConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>
 

 

