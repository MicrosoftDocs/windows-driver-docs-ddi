---
UID: NF:portcls.IAdapterPnpManagement.PnpStop
title: IAdapterPnpManagement::PnpStop
description: The PnpStop method provides a notification after stopping all Ioctl operations.
tech.root: audio
ms.assetid: 7ad59aef-fc02-4102-a5b8-5349209bd65d
ms.date: 10/31/2018
ms.topic: method
ms.keywords: IAdapterPnpManagement::PnpStop, PnpStop, IAdapterPnpManagement.PnpStop, IAdapterPnpManagement::PnpStop, IAdapterPnpManagement.PnpStop
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
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IAdapterPnpManagement.PnpStop
product: 
 - Windows
targetos: Windows

---

# IAdapterPnpManagement::PnpStop


## -description

The PnpStop method provides a notification after stopping all Ioctl operations and moving active streams from run|pause|acquire state to stop state.

## -parameters


## -returns
This method returns void.

## -remarks

PnpStop is invoked by Portcls after stopping all Ioctl operations and moving active streams from run|pause|acquire state to stop state. This call is not made while holding the device global lock. Thus the miniport driver has an opportunity to wait for its async operations (work-items, dpc, async threads) and unregister its audio subdevices. Before returning from this call the miniport must ensure that all the hardware resources have been released. 

The miniport must not wait for the current miniport/stream objects to be deleted since it is unclear when existing audio clients will release the current handles. The PnpStop thread cannot block forever without crashing the system, i.e., this is a PnP/Power thread.

IAdapterPnpManagement::Pnpstop is called after:

- All miniport audio subdevices have been notified. 
- All the streams belonging to the audio subdevices have been stopped. 
- All the Pnp interfaces have been turned off. 
- All pending I/O has been cancelled. 

For more information, see [Implement PnP Rebalance for PortCls Audio Drivers](https://docs.microsoft.com/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers).  

## -see-also

[IAdapterPnpManagement](nn-portcls-iadapterpnpmanagement.md)

