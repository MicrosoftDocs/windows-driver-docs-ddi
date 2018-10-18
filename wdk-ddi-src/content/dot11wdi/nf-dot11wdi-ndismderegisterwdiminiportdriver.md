---
UID: NF:dot11wdi.NdisMDeregisterWdiMiniportDriver
title: NdisMDeregisterWdiMiniportDriver function
author: windows-driver-content
description: A miniport driver calls the NdisMDeregisterWdiMiniportDriver function to release resources that it allocated with a previous call to the NdisMRegisterWdiMiniportDriver function.
old-location: netvista\ndismderegisterwdiminiportdriver.htm
tech.root: netvista
ms.assetid: 6B2B0A88-9F63-4A68-894B-38424FBE161E
ms.date: 05/02/2018
ms.keywords: NdisMDeregisterWdiMiniportDriver, NdisMDeregisterWdiMiniportDriver function [Network Drivers Starting with Windows Vista], dot11wdi/NdisMDeregisterWdiMiniportDriver, netvista.ndismderegisterwdiminiportdriver
ms.topic: function
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
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
-	NdisMDeregisterWdiMiniportDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMDeregisterWdiMiniportDriver function


## -description


A miniport driver calls the NdisMDeregisterWdiMiniportDriver function to release resources that it allocated with a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt297596">NdisMRegisterWdiMiniportDriver</a> function.


## -parameters




### -param NdisMiniportDriverHandle [in]

The NDIS handle for a miniport driver.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297596">NdisMRegisterWdiMiniportDriver</a>
 

 

