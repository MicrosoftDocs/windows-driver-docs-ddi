---
UID: NF:ndis.NdisOpenConfigurationKeyByName
title: NdisOpenConfigurationKeyByName function (ndis.h)
description: The NdisOpenConfigurationKeyByName function opens a named subkey of a given open registry key that is designated by a caller-supplied handle.
old-location: netvista\ndisopenconfigurationkeybyname.htm
tech.root: netvista
ms.assetid: 9ce7f40f-28f1-4303-9f7a-24ff1213bab1
ms.date: 05/02/2018
ms.keywords: NdisOpenConfigurationKeyByName, NdisOpenConfigurationKeyByName function [Network Drivers Starting with Windows Vista], ndis/NdisOpenConfigurationKeyByName, ndis_configuration_ref_b952e09a-cef5-46f7-b566-6995e8581862.xml, netvista.ndisopenconfigurationkeybyname
ms.topic: function
f1_keywords:
 - "ndis/NdisOpenConfigurationKeyByName"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisOpenConfigurationKeyByName (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisOpenConfigurationKeyByName (NDIS 5.1)) in Windows XP.
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisOpenConfigurationKeyByName
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisOpenConfigurationKeyByName function


## -description


The 
  <b>NdisOpenConfigurationKeyByName</b> function opens a named subkey of a given open registry key that is
  designated by a caller-supplied handle.


## -parameters




### -param Status [out]

A pointer to a caller-supplied variable in which this function returns the status of its attempt
     to open the registry key. Possible return values are one of the following:
     





#### NDIS_STATUS_SUCCESS

NDIS has initialized accessed to the subkey specified by 
       <i>SubKeyName</i> .



#### NDIS_STATUS_FAILURE

The key could not be opened.


### -param ConfigurationHandle [in]

The handle to a registry key for which a subkey should be opened. Typically, 
     <i>ConfigurationHandle</i> is returned by the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationex">
     NdisOpenConfigurationEx</a> function.


### -param SubKeyName [in]

A pointer to an NDIS_STRING type containing a caller-supplied, counted string in the
     system-default character set that specifies the name of the registry subkey to open. For Microsoft
     Windows 2000 and later drivers, this string contains Unicode characters. That is, for Windows 2000 and
     later, NDIS defines the NDIS_STRING type as a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.


### -param SubKeyHandle [out]

A pointer to a caller-supplied variable in which this function returns a handle to the opened
     subkey if this call is successful.


## -remarks



<b>NdisOpenConfigurationKeyByName</b> allows a driver to access configuration information that is stored
    in a named subkey in the registry.

Note that the 
    <i>ConfigurationHandle</i> passed in to 
    <b>NdisOpenConfigurationKeyByName</b> can be any valid handle to a registry key already opened by the
    caller. 
    <b>NdisOpenConfigurationKeyByName</b> returns configuration information for subkeys relative to any valid 
    <i>ConfigurationHandle</i> .

After a driver has consumed and, possibly, modified the registry configuration information, it must
    call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseconfiguration">NdisCloseConfiguration</a> function to
    release the handle that was obtained from 
    <b>NdisOpenConfigurationKeyByName</b>. 
    <b>NdisCloseConfiguration</b> also frees any temporary storage that NDIS allocated in the driver's calls
    to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a>, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadnetworkaddress">NdisReadNetworkAddress</a>, or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteconfiguration">NdisWriteConfiguration</a> functions
    with the 
    <i>SubKeyHandle</i> that 
    <b>NdisOpenConfigurationKeyByName</b> returned.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_string">ANSI_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseconfiguration">NdisCloseConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyindex">
   NdisOpenConfigurationKeyByIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteconfiguration">NdisWriteConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

