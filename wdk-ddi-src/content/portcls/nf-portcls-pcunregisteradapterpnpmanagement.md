---
UID: NF:portcls.PcUnregisterAdapterPnpManagement
title: PcUnregisterAdapterPnpManagement function (portcls.h)
description: The PcUnregisterAdapterPnpManagement function unregisters the audio adapter's PnP management interface from the PortCls class driver. It is used to support PnP rebalance.
old-location: audio\pcunregisteradapterpnpmanagement.htm
tech.root: audio
ms.assetid: 51BBE9F6-7661-45A1-8416-9AAA307FCA10
ms.date: 05/08/2018
keywords: ["PcUnregisterAdapterPnpManagement function"]
ms.keywords: PcUnregisterAdapterPnpManagement, PcUnregisterAdapterPnpManagement function [Audio Devices], audio.pcunregisteradapterpnpmanagement, portcls/PcUnregisterAdapterPnpManagement
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PcUnregisterAdapterPnpManagement
 - portcls/PcUnregisterAdapterPnpManagement
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcUnregisterAdapterPnpManagement
---

# PcUnregisterAdapterPnpManagement function


## -description

The <b>PcUnregisterAdapterPnpManagement</b> function unregisters the audio adapter's PnP management interface from the PortCls class driver.  It is used to support PnP rebalance.

## -parameters

### -param DeviceObject 

[in]
Specifies a pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.

## -returns

The <b>PcUnregisterAdapterPnpManagement</b>  function returns STATUS_SUCCESS if the function call was successful. Otherwise, it returns the appropriate error code.

## -remarks

The <b>PcUnregisterAdapterPnpManagement</b>  function unregisters a driver's PnP management interface that was registered with PortCls by using the <b>PcUnregisterAdapterPnpManagement</b>  function. 

 This function must only be called if the PnP management interface for the adapter was previously registered with PortCls using <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpnpmanagement">PcRegisterAdapterPnpManagement</a>.

Portcls uses <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpnpmanagement">PcRegisterAdapterPnpManagement</a> and <b>PcUnregisterAdapterPnpManagement</b> to support PNP rebalance. 


For more information,  see <a href="/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers">Implement PnP Rebalance for PortCls Audio Drivers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpnpmanagement">PcRegisterAdapterPnpManagement</a>