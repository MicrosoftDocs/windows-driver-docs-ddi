---
UID: NF:ndis.NdisCloseConfiguration
title: NdisCloseConfiguration function (ndis.h)
description: The NdisCloseConfiguration function releases the handle to the registry key that was returned by the NdisOpenConfigurationEx, NdisOpenConfigurationKeyByIndex, or NdisOpenConfigurationKeyByName function.
old-location: netvista\ndiscloseconfiguration.htm
tech.root: netvista
ms.assetid: 2d68f7dd-3954-4b3b-8673-1da63e1a1edc
ms.date: 05/02/2018
keywords: ["NdisCloseConfiguration function"]
ms.keywords: NdisCloseConfiguration, NdisCloseConfiguration function [Network Drivers Starting with Windows Vista], ndis/NdisCloseConfiguration, ndis_configuration_ref_eb02fa4e-fff9-41e5-81f6-9580af7480a7.xml, netvista.ndiscloseconfiguration
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisCloseConfiguration
 - ndis/NdisCloseConfiguration
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisCloseConfiguration
---

# NdisCloseConfiguration function


## -description

The 
  <b>NdisCloseConfiguration</b> function releases the handle to the registry key that was returned by the 
  <a href="/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>, 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyindex">
  NdisOpenConfigurationKeyByIndex</a>, or 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyname">
  NdisOpenConfigurationKeyByName</a> function.

## -parameters

### -param ConfigurationHandle 

[in]
The handle that the 
     <a href="/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a> function
     returns.

## -remarks

This function frees any temporary storage allocated in calls to other 
    <b>Ndis<i>Xxx</i></b> functions that required the returned 
    <i>ConfigurationHandle</i> as a parameter.

## -see-also

<a href="/previous-versions/windows/embedded/gg156036(v=winembedded.80)">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyindex">
   NdisOpenConfigurationKeyByIndex</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenconfigurationkeybyname">
   NdisOpenConfigurationKeyByName</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadnetworkaddress">NdisReadNetworkAddress</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteconfiguration">NdisWriteConfiguration</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>