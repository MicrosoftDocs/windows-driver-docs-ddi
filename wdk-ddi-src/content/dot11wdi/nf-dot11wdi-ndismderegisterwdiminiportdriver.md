---
UID: NF:dot11wdi.NdisMDeregisterWdiMiniportDriver
title: NdisMDeregisterWdiMiniportDriver function (dot11wdi.h)
description: A miniport driver calls the NdisMDeregisterWdiMiniportDriver function to release resources that it allocated with a previous call to the NdisMRegisterWdiMiniportDriver function.
old-location: netvista\ndismderegisterwdiminiportdriver.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMDeregisterWdiMiniportDriver function"]
ms.keywords: NdisMDeregisterWdiMiniportDriver, NdisMDeregisterWdiMiniportDriver function [Network Drivers Starting with Windows Vista], dot11wdi/NdisMDeregisterWdiMiniportDriver, netvista.ndismderegisterwdiminiportdriver
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMDeregisterWdiMiniportDriver
 - dot11wdi/NdisMDeregisterWdiMiniportDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMDeregisterWdiMiniportDriver
---

# NdisMDeregisterWdiMiniportDriver function


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

A miniport driver calls the NdisMDeregisterWdiMiniportDriver function to release resources that it allocated with a previous call to the <a href="/windows-hardware/drivers/ddi/dot11wdi/nf-dot11wdi-ndismregisterwdiminiportdriver">NdisMRegisterWdiMiniportDriver</a> function.

## -parameters

### -param NdisMiniportDriverHandle [in]


The NDIS handle for a miniport driver.

## -returns

This function does not return a value.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/nf-dot11wdi-ndismregisterwdiminiportdriver">NdisMRegisterWdiMiniportDriver</a>
