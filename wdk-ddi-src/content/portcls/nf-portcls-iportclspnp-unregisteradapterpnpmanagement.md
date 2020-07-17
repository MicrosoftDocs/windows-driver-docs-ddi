---
UID: NF:portcls.IPortClsPnp.UnregisterAdapterPnpManagement
title: IPortClsPnp::UnregisterAdapterPnpManagement (portcls.h)
description: The UnRegisterAdapterPowerManagement method unregisters the PnP management interface of the adapter from PortCls.
old-location: audio\iportclspnp_unregisteradapterpnpmanagement.htm
tech.root: audio
ms.assetid: 7FAA5C88-2846-4C98-A44A-B53A1A7A953C
ms.date: 05/08/2018
keywords: ["IPortClsPnp::UnregisterAdapterPnpManagement"]
ms.keywords: IPortClsPnp interface [Audio Devices],UnregisterAdapterPnpManagement method, IPortClsPnp.UnregisterAdapterPnpManagement, IPortClsPnp::UnregisterAdapterPnpManagement, UnregisterAdapterPnpManagement, UnregisterAdapterPnpManagement method [Audio Devices], UnregisterAdapterPnpManagement method [Audio Devices],IPortClsPnp interface, audio.iportclspnp_unregisteradapterpnpmanagement, portcls/IPortClsPnp::UnregisterAdapterPnpManagement
f1_keywords:
 - "portcls/IPortClsPnp.UnregisterAdapterPnpManagement"
 - "IPortClsPnp.UnregisterAdapterPnpManagement"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
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
req.lib: 
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
- IPortClsPnp.UnregisterAdapterPnpManagement
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsPnp::UnregisterAdapterPnpManagement


## -description


The <code>UnRegisterAdapterPowerManagement</code> method unregisters the PnP management interface of the adapter from PortCls.


## -parameters




### -param DeviceObject [in]

Specifies a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter that the PnP management was registered with earlier using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportclspnp-registeradapterpnpmanagement">IPortClsPnp::RegisterAdapterPnpManagement</a>.


## -returns



The <code>UnregisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.




## -remarks



For more information,  see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers">Implement PnP Rebalance for PortCls Audio Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportclspnp">IPortClsPnp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportclspnp-registeradapterpnpmanagement">IPortClsPnp::RegisterAdapterPnpManagement</a>
 

 

