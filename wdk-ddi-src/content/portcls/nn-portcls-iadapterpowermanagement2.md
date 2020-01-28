---
UID: NN:portcls.IAdapterPowerManagement2
title: IAdapterPowerManagement2 (portcls.h)
description: The IAdapterPowerManagement2 interface inherits from IUnknown and it is used to manage the power state of an audio adapter.
old-location: audio\iadapterpowermanagement2.htm
tech.root: audio
ms.assetid: 86cab3f1-2792-486f-91a3-4fb88be2a1da
ms.date: 05/08/2018
ms.keywords: IAdapterPowerManagement2, IAdapterPowerManagement2 interface [Audio Devices], IAdapterPowerManagement2 interface [Audio Devices],described, audio.iadapterpowermanagement2, audmp-routines_c7d21546-b88c-46e6-9612-6244155058b0.xml, portcls/IAdapterPowerManagement2
f1_keywords:
 - "portcls/IAdapterPowerManagement2"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IAdapterPowerManagement2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IAdapterPowerManagement2 interface


## -description


The <code>IAdapterPowerManagement2</code> interface inherits from <b>IUnknown</b> and it is used to manage the power state of an audio adapter. In contrast with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iadapterpowermanagement">IAdapterPowerManagement</a> interface, <code>IAdapterPowerManagement2</code> provides the adapter driver with messages about device and system power states. This enables the driver to make more efficient power management adjustments.

<code>IAdapterPowerManagement2</code> is implemented by the audio adapter driver and the driver must register this interface with Portcls.sys (Portcls) so that it can receive power management messages. To register this interface, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpowermanagement">PcRegisterAdapterPowerManagement</a>. If you want to fill the <a href="https://go.microsoft.com/fwlink/p/?linkid=143127">caps structure</a> for your device, your adapter driver can call <b>PcRegisterAdapterPowerManagement</b> from within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> function or before your driver calls <b>AddDevice</b>.

