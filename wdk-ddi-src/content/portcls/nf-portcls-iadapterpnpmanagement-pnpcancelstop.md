---
UID: NF:portcls.IAdapterPnpManagement.PnpCancelStop
title: IAdapterPnpManagement::PnpCancelStop (portcls.h)
description: The PnpCancelStop method provides a notification while processing the CancelStop IRP.
tech.root: audio
ms.assetid: 882d841c-1e16-4bb6-a9e2-df8fbe5728c9
ms.date: 10/31/2018
ms.topic: method
ms.keywords: IAdapterPnpManagement::PnpCancelStop, PnpCancelStop, IAdapterPnpManagement.PnpCancelStop, IAdapterPnpManagement::PnpCancelStop, IAdapterPnpManagement.PnpCancelStop
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
 - IAdapterPnpManagement.PnpCancelStop
product: 
 - Windows
targetos: Windows

---

# IAdapterPnpManagement::PnpCancelStop


## -description

The PnpCancelStop method provides a notification while processing the CancelStop IRP.

## -parameters
None

## -returns
This method returns void.

## -remarks
PnpCancelStop is invoked by portcls while processing the CancelStop IRP. This is just a notification. It is possible for the Miniport to receive PnpCancelStop even without previously receiving a PnpQueryStop notification. The miniport should be written to accommodate this behavior. For example this is the case when the QueryStop logic fails the IRP before Portcls has an opportunity to forward this notification to the Miniport. In this scenario PnP manager still invokes a PnP Cancel Stop. 

Note: Portcls acquires the device global lock before making this call, thus the miniport must execute this call as fast as possible. Portcls restarts any pended create requests.
 
For more information, see [Implement PnP Rebalance for PortCls Audio Drivers](https://docs.microsoft.com/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers).  


## -see-also

[IAdapterPnpManagement](nn-portcls-iadapterpnpmanagement.md)
