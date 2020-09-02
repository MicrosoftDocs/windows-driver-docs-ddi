---
UID: NF:portcls.IAdapterPnpManagement.PnpQueryStop
title: IAdapterPnpManagement::PnpQueryStop (portcls.h)
description: PnpQueryStop provides a notification when PnpQueryStop is invoked by portcls just before succeeding the QueryStop IRP.
tech.root: audio
ms.assetid: ddc729dd-71fe-4341-ba7e-ee05e9f91291
ms.date: 10/31/2018
keywords: ["IAdapterPnpManagement::PnpQueryStop"]
ms.keywords: IAdapterPnpManagement::PnpQueryStop, PnpQueryStop, IAdapterPnpManagement.PnpQueryStop, IAdapterPnpManagement::PnpQueryStop, IAdapterPnpManagement.PnpQueryStop
req.header: portcls.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IAdapterPnpManagement::PnpQueryStop
 - portcls/IAdapterPnpManagement::PnpQueryStop
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IAdapterPnpManagement.PnpQueryStop
product:
 - Windows
---

# IAdapterPnpManagement::PnpQueryStop


## -description

PnpQueryStop provides a notification when PnpQueryStop is invoked by portcls just before succeeding the QueryStop IRP.

## -remarks

PnpQueryStop is invoked by portcls just before succeeding the QueryStop IRP. This is just a notification and the call doesn’t return a value. 

Note  Portcls acquires the device global lock before making this call, thus the miniport must execute this call as fast as possible. While a Stop is pending, Portcls will block (hold) any new create requests.
 

For more information, see [Implement PnP Rebalance for PortCls Audio Drivers](https://docs.microsoft.com/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers).

## -see-also

[IAdapterPnpManagement](nn-portcls-iadapterpnpmanagement.md)

