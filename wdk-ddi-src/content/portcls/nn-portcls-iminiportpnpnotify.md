---
UID: NN:portcls.IMiniportPnpNotify
title: IMiniportPnpNotify (portcls.h)
description: IMiniportPnpNotify is an optional interface to allow miniport objects (audio subdevices) to receive PnP state change notifications.
old-location: audio\iminiportpnpnotify.htm
tech.root: audio
ms.assetid: 634ADB7C-85B6-4C37-81A0-4A4891D0BBC4
ms.date: 03/19/2018
keywords: ["IMiniportPnpNotify interface"]
ms.keywords: IMiniportPnpNotify, IMiniportPnpNotify interface [Audio Devices], IMiniportPnpNotify interface [Audio Devices], described, audio.iminiportpnpnotify, portcls/IMiniportPnpNotify
f1_keywords:
 - "portcls/IMiniportPnpNotify"
 - "IMiniportPnpNotify"
req.header: portcls.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib: Portcls.lib
req.dll:
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportPnpNotify
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportPnpNotify interface


## -description


IMiniportPnpNotify is an optional interface to allow miniport objects (audio subdevices)  to receive PnP state change notifications.


IMiniportPnpNotify interface available is on both WaveRT and Topology.

Miniports have an opportunity to receive a PnP Stop notification for each audio subdevice they have registered. To receive this notification, the subdevice must support IMiniportPnpNotify.
 Only the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportpnpnotify-pnpstop">IMiniportPnpNotify::PnpStop</a> notification is defined on this interface.

IAdapterPnpManagement is available in Windows 10, version 1511 and later versions of Windows.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers">
Implement PnP Rebalance for PortCls Audio Drivers</a>.

