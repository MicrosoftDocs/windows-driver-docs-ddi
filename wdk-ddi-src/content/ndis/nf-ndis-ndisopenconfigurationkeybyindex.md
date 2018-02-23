---
UID: NF:ndis.NdisOpenConfigurationKeyByIndex
title: NdisOpenConfigurationKeyByIndex function
author: windows-driver-content
description: The NdisOpenConfigurationKeyByIndex function opens a subkey of a given open registry key that is designated by a caller-supplied handle.
old-location: netvista\ndisopenconfigurationkeybyindex.htm
old-project: netvista
ms.assetid: e405853a-cf25-4214-82a9-bc3d76334413
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis_configuration_ref_71c37932-c758-475c-9c84-c176c6c40cf8.xml, ndis/NdisOpenConfigurationKeyByIndex, NdisOpenConfigurationKeyByIndex, netvista.ndisopenconfigurationkeybyindex, NdisOpenConfigurationKeyByIndex function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisOpenConfigurationKeyByIndex
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisOpenConfigurationKeyByIndex function


## -description


The 
  <b>NdisOpenConfigurationKeyByIndex</b> function opens a subkey of a given open registry key that is
  designated by a caller-supplied handle.


## -syntax


````
VOID NdisOpenConfigurationKeyByIndex(
  _Out_ PNDIS_STATUS Status,
  _In_  NDIS_HANDLE  ConfigurationHandle,
  _In_  ULONG        Index,
  _Out_ PNDIS_STRING KeyName,
  _Out_ PNDIS_HANDLE KeyHandle
);
````


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
     <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">
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
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


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
    <a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a> function to
    release the handle that is obtained from 
    <b>NdisOpenConfigurationKeyByIndex</b>. 
    <b>NdisCloseConfiguration</b> also frees any temporary storage that NDIS allocated for the driver's calls
    to the 
    <a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>, 
    <a href="..\ndis\nf-ndis-ndisreadnetworkaddress.md">NdisReadNetworkAddress</a>, or 
    <a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a> functions
    with the 
    <i>SubKeyHandle</i> that 
    <b>NdisOpenConfigurationKeyByIndex</b> returned.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
   NdisOpenConfigurationKeyByName</a>



<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>



<a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndiscloseconfiguration.md">NdisCloseConfiguration</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOpenConfigurationKeyByIndex function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

