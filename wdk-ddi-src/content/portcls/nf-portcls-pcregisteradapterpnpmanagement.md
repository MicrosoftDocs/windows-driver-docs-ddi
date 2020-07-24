---
UID: NF:portcls.PcRegisterAdapterPnpManagement
title: PcRegisterAdapterPnpManagement function (portcls.h)
description: The PcRegisterAdapterPnpManagement function registers the adapter's PnP-management interface with the PortCls system driver. It is used to support PnP rebalance.
old-location: audio\pcregisteradapterpnpmanagement.htm
tech.root: audio
ms.assetid: DF597216-FB81-466C-871E-5E08C69B78DA
ms.date: 05/08/2018
keywords: ["PcRegisterAdapterPnpManagement function"]
ms.keywords: PcRegisterAdapterPnPManagement, PcRegisterAdapterPnPManagement function [Audio Devices], PcRegisterAdapterPnpManagement, audio.pcregisteradapterpnpmanagement, portcls/PcRegisterAdapterPnPManagement
f1_keywords:
 - "portcls/PcRegisterAdapterPnPManagement"
 - "PcRegisterAdapterPnPManagement"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
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
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcRegisterAdapterPnPManagement
targetos: Windows
req.typenames: 
---

# PcRegisterAdapterPnpManagement function


## -description


The  PcRegisterAdapterPnpManagement function registers the adapter's PnP-management interface with the PortCls system driver.  It is used to support PnP rebalance. 


## -parameters




### -param Unknown

<p>Pointer to an adapter driver object's <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown"><b>IUnknown</b></a> interface. The PortCls system driver queries this object for its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iadapterpnpmanagement">IAdapterPnpManagement</a> interface.</p>


### -param DeviceObject [in]

Specifies a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## -returns



<b>PcRegisterAdapterPnpManagement</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



Portcls uses <b>PcRegisterAdapterPnpManagement</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcunregisteradapterpnpmanagement">PcUnregisterAdapterPnpManagement</a> to support PNP rebalance.

For more information,  see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers">Implement PnP Rebalance for PortCls Audio Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iadapterpnpmanagement">IAdapterPnpManagement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers">Implement PnP Rebalance for PortCls Audio Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcunregisteradapterpnpmanagement">PcUnregisterAdapterPnpManagement</a>
 

 

