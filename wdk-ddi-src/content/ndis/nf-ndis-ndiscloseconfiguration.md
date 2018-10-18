---
UID: NF:ndis.NdisCloseConfiguration
title: NdisCloseConfiguration function
author: windows-driver-content
description: The NdisCloseConfiguration function releases the handle to the registry key that was returned by the NdisOpenConfigurationEx, NdisOpenConfigurationKeyByIndex, or NdisOpenConfigurationKeyByName function.
old-location: netvista\ndiscloseconfiguration.htm
tech.root: netvista
ms.assetid: 2d68f7dd-3954-4b3b-8673-1da63e1a1edc
ms.date: 5/2/2018
ms.keywords: NdisCloseConfiguration, NdisCloseConfiguration function [Network Drivers Starting with Windows Vista], ndis/NdisCloseConfiguration, ndis_configuration_ref_eb02fa4e-fff9-41e5-81f6-9580af7480a7.xml, netvista.ndiscloseconfiguration
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisCloseConfiguration
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCloseConfiguration function


## -description


The 
  <b>NdisCloseConfiguration</b> function releases the handle to the registry key that was returned by the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh975122">NdisOpenConfigurationEx</a>, 
  <a href="https://msdn.microsoft.com/e405853a-cf25-4214-82a9-bc3d76334413">
  NdisOpenConfigurationKeyByIndex</a>, or 
  <a href="https://msdn.microsoft.com/9ce7f40f-28f1-4303-9f7a-24ff1213bab1">
  NdisOpenConfigurationKeyByName</a> function.


## -parameters




### -param ConfigurationHandle [in]

The handle that the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh975122">NdisOpenConfigurationEx</a> function
     returns.


## -returns



None




## -remarks



This function frees any temporary storage allocated in calls to other 
    <b>Ndis<i>Xxx</i></b> functions that required the returned 
    <i>ConfigurationHandle</i> as a parameter.




## -see-also




<a href="https://msdn.microsoft.com/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975122">NdisOpenConfigurationEx</a>



<a href="https://msdn.microsoft.com/e405853a-cf25-4214-82a9-bc3d76334413">
   NdisOpenConfigurationKeyByIndex</a>



<a href="https://msdn.microsoft.com/9ce7f40f-28f1-4303-9f7a-24ff1213bab1">
   NdisOpenConfigurationKeyByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564511">NdisReadConfiguration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564512">NdisReadNetworkAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564659">NdisWriteConfiguration</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>
 

 

