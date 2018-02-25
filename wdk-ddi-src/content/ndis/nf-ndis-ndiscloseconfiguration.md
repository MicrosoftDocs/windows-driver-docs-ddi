---
UID: NF:ndis.NdisCloseConfiguration
title: NdisCloseConfiguration function
author: windows-driver-content
description: The NdisCloseConfiguration function releases the handle to the registry key that was returned by the NdisOpenConfigurationEx, NdisOpenConfigurationKeyByIndex, or NdisOpenConfigurationKeyByName function.
old-location: netvista\ndiscloseconfiguration.htm
old-project: netvista
ms.assetid: 2d68f7dd-3954-4b3b-8673-1da63e1a1edc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, N, NdisCloseConfiguration, NdisCloseConfiguration function [Network Drivers Starting with Windows Vista], a, d, e, f, g, i, l, n, ndis/NdisCloseConfiguration, ndis_configuration_ref_eb02fa4e-fff9-41e5-81f6-9580af7480a7.xml, netvista.ndiscloseconfiguration, o, r, s, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCloseConfiguration (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCloseConfiguration (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function, NdisOpenConfigurationEx
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisCloseConfiguration
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCloseConfiguration function


## -description


The 
  <b>NdisCloseConfiguration</b> function releases the handle to the registry key that was returned by the 
  <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>, 
  <a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyindex.md">
  NdisOpenConfigurationKeyByIndex</a>, or 
  <a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
  NdisOpenConfigurationKeyByName</a> function.


## -syntax


````
VOID NdisCloseConfiguration(
  _In_ NDIS_HANDLE ConfigurationHandle
);
````


## -parameters




### -param ConfigurationHandle [in]

The handle that the 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a> function
     returns.


## -returns



None




## -remarks



This function frees any temporary storage allocated in calls to other 
    <b>Ndis<i>Xxx</i></b> functions that required the returned 
    <i>ConfigurationHandle</i> as a parameter.




## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>



<a href="..\ndis\nf-ndis-ndisreadnetworkaddress.md">NdisReadNetworkAddress</a>



<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyname.md">
   NdisOpenConfigurationKeyByName</a>



<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisopenconfigurationkeybyindex.md">
   NdisOpenConfigurationKeyByIndex</a>



<a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a>



<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCloseConfiguration function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

