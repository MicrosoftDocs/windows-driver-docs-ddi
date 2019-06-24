---
UID: NF:ndis.NdisOpenConfigurationKeyByIndex
title: NdisOpenConfigurationKeyByIndex function (ndis.h)
description: The NdisOpenConfigurationKeyByIndex function opens a subkey of a given open registry key that is designated by a caller-supplied handle.
old-location: netvista\ndisopenconfigurationkeybyindex.htm
tech.root: netvista
ms.assetid: e405853a-cf25-4214-82a9-bc3d76334413
ms.date: 05/02/2018
ms.keywords: NdisOpenConfigurationKeyByIndex, NdisOpenConfigurationKeyByIndex function [Network Drivers Starting with Windows Vista], ndis/NdisOpenConfigurationKeyByIndex, ndis_configuration_ref_71c37932-c758-475c-9c84-c176c6c40cf8.xml, netvista.ndisopenconfigurationkeybyindex
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisOpenConfigurationKeyByIndex (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisOpenConfigurationKeyByIndex (NDIS 5.1)) in Windows XP.
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisOpenConfigurationKeyByIndex
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisOpenConfigurationKeyByIndex function


## -description


The 
  <b>NdisOpenConfigurationKeyByIndex</b> function opens a subkey of a given open registry key that is
  designated by a caller-supplied handle.


## -parameters




### -param Status [out]

A pointer to a caller-supplied variable in which this function returns the status of its attempt
     to open the designated registry key. Possible return values are one of the following:
     





#### NDIS_STATUS_SUCCESS

NDIS has initialized accessed to the subkey specified by 
       <i>KeyName</i> and 
       <i>Index</i> .



#### NDIS_STATUS_FAILURE

The key could not be opened.


### -param ConfigurationHandle [in]

The handle to a registry key for which a subkey is to be opened. Typically, 
     <i>ConfigurationHandle</i> is returned by the 
     <a href="https://msdn.microsoft.com/76539106-6d8d-4a80-9c74-a6a4ca37c40e">
     NdisOpenConfigurationEx</a> function.


### -param Index [in]

The index of the subkey to be opened. This zero-based value designates the subkey to be opened
     under the key already opened with 
     <i>ConfigurationHandle</i> .


### -param KeyName [out]

A pointer to an NDIS_STRING type containing a caller-supplied buffer in which this functions
     returns a counted string in the system-default character set. This string specifies the name of the
     opened subkey if the call succeeds. For Microsoft Windows 2000 and later drivers, this string contains
     Unicode characters. That is, for Windows 2000 and later, NDIS defines the NDIS_STRING type as a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.


### -param KeyHandle [out]

A pointer to a caller-supplied variable in which this function returns a handle to the opened
     subkey if the call succeeds.


## -returns



None




## -remarks



<b>NdisOpenConfigurationKeyByIndex</b> allows a driver to access configuration information that its
    installation file stored in a registry subkey.

Note that the 
    <i>ConfigurationHandle</i> passed in to 
    <b>NdisOpenConfigurationKeyByIndex</b> can be any valid handle to a registry key already opened by the
    caller. 
    <b>NdisOpenConfigurationKeyByIndex</b> returns configuration information for subkeys relative to any valid    
    <i>ConfigurationHandle</i> .

Since 
    <b>NdisOpenConfigurationKeyByIndex</b> references a subkey through an index, the driver does not have to
    specify subkey names. A driver can sequence through a set of registry subkeys by repeatedly calling 
    <b>NdisOpenConfigurationKeyIndex</b> after incrementing the index until the function returns
    NDIS_STATUS_FAILURE, thereby indicating that there are no more subkeys to open.

After a driver has consumed and, possibly, modified the configuration information stored in the
    registry, it must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561642">NdisCloseConfiguration</a> function to
    release the handle that is obtained from 
    <b>NdisOpenConfigurationKeyByIndex</b>. 
    <b>NdisCloseConfiguration</b> also frees any temporary storage that NDIS allocated for the driver's calls
    to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a>, 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564512">NdisReadNetworkAddress</a>, or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a> functions
    with the 
    <i>SubKeyHandle</i> that 
    <b>NdisOpenConfigurationKeyByIndex</b> returned.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561642">NdisCloseConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975122">NdisOpenConfigurationEx</a>



<a href="https://msdn.microsoft.com/9ce7f40f-28f1-4303-9f7a-24ff1213bab1">
   NdisOpenConfigurationKeyByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

