---
UID: NF:portcls.IAdapterPnpManagement.GetSupportedRebalanceType
title: IAdapterPnpManagement::GetSupportedRebalanceType (portcls.h)
description: The GetSupportedRebalanceType method returns the type of rebalancing supported.
tech.root: audio
ms.date: 10/31/2018
keywords: ["IAdapterPnpManagement::GetSupportedRebalanceType"]
ms.keywords: IAdapterPnpManagement::GetSupportedRebalanceType, GetSupportedRebalanceType, IAdapterPnpManagement.GetSupportedRebalanceType, IAdapterPnpManagement::GetSupportedRebalanceType, IAdapterPnpManagement.GetSupportedRebalanceType
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
 - IAdapterPnpManagement::GetSupportedRebalanceType
 - portcls/IAdapterPnpManagement::GetSupportedRebalanceType
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IAdapterPnpManagement::GetSupportedRebalanceType
---

# IAdapterPnpManagement::GetSupportedRebalanceType


## -description

The GetSupportedRebalanceType method returns the type of rebalancing supported. Rebalancing is used in certain Thunderbolt USB scenario, where, when additional devices are added to the USB chain, the use of memory resources needs to be rearranged and consolidated.

## -returns

The GetSupportedRebalanceType method returns the type of rebalancing supported (RebalanceNotSupported or RebalanceRemoveSubdevices) as defined in the enum PC_REBALANCE_TYPE.

## -remarks

GetSupportedRebalanceType is called by Portcls while processing the QueryStop. Miniport returns the supported rebalance type. 

Note  Portcls acquires the device global lock before making this call, thus the miniport must execute this call as fast as possible.
 
For more information, see [Implement PnP Rebalance for PortCls Audio Drivers](/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers).

## -see-also

[IAdapterPnpManagement](nn-portcls-iadapterpnpmanagement.md)

