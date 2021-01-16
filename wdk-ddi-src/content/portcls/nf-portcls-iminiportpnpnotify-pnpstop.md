---
UID: NF:portcls.IMiniportPnpNotify.PnpStop
title: IMiniportPnpNotify::PnpStop (portcls.h)
description: An optional interface to allow miniport drivers to receive PnP state change notifications.
tech.root: audio
ms.date: 10/31/2018
keywords: ["IMiniportPnpNotify::PnpStop"]
ms.keywords: IMiniportPnpNotify::PnpStop, PnpStop, IMiniportPnpNotify.PnpStop, IMiniportPnpNotify::PnpStop, IMiniportPnpNotify.PnpStop
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
 - IMiniportPnpNotify::PnpStop
 - portcls/IMiniportPnpNotify::PnpStop
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportPnpNotify::PnpStop
product:
 - Windows
---

# IMiniportPnpNotify::PnpStop


## -description

An optional interface to allow miniport drivers to receive PnP state change notifications.

## -remarks

Available in Windows 10, version 1511 and later versions of Windows. 

Miniports have an opportunity to receive a PnP Stop notification for each audio subdevice they have registered. To receive this notification, the subdevice must support IMiniportPnpNotify. Only the IMiniportPnpNotify::PnpStop notification is defined on this interface.

IMiniportPnpNotify interface available is on both WaveRT and Topology.

Note:  Because Portcls acquires the device global lock before making this call, thus the miniport must execute this call as fast as possible. The miniport must not wait on other activity while processing this call to prevent deadlock when other threads/work-items are waiting for the device global lock. If needed, miniport can wait in the IAdapterPnpManagement::PnpStop call.
 
For more information, see [Implement PnP Rebalance for PortCls Audio Drivers](/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers).

## -see-also

[IMiniPortPnpNotify](nn-portcls-iminiportpnpnotify.md)

