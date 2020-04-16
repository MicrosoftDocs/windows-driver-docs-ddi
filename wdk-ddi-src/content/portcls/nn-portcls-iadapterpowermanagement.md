---
UID: NN:portcls.IAdapterPowerManagement
title: IAdapterPowerManagement (portcls.h)
description: The IAdapterPowerManagement interface is used to manage the power state of an audio adapter.
old-location: audio\iadapterpowermanagement.htm
tech.root: audio
ms.assetid: 20c898fd-a782-4d73-bf1b-a25db4440632
ms.date: 05/08/2018
keywords: ["IAdapterPowerManagement interface"]
ms.keywords: IAdapterPowerManagement, IAdapterPowerManagement interface [Audio Devices], IAdapterPowerManagement interface [Audio Devices],described, audio.iadapterpowermanagement, audmp-routines_9daec120-c61d-426c-b30f-80484e1fb652.xml, portcls/IAdapterPowerManagement
f1_keywords:
 - "portcls/IAdapterPowerManagement"
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
- IAdapterPowerManagement
product:
- Windows
targetos: Windows
req.typenames: 
---

# IAdapterPowerManagement interface


## -description


The <code>IAdapterPowerManagement</code> interface is used to manage the power state of an audio adapter. This interface is implemented by the adapter driver, which exposes the interface to the PortCls system driver. <code>IAdapterPowerManagement</code> inherits from the <b>IUnknown</b> interface.

The operating system manages power in a WDM audio adapter primarily through the <code>IAdapterPowerManagement</code> interface that the adapter driver registers with PortCls during the device-startup phase of device initialization (see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/starting-a-device">Starting a Device</a>). The adapter driver registers its <code>IAdapterPowerManagement</code> interface by calling the PortCls function <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpowermanagement">PcRegisterAdapterPowerManagement</a>. This function receives an <b>IUnknown</b> object from the adapter driver and determines whether the object supports the <code>IAdapterPowerManagement</code> interface by calling <b>QueryInterface</b> on this object with REFIID <b>IID_IAdapterPowerManagement</b>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/implementing-iadapterpowermanagement">Implementing IAdapterPowerManagement</a>.

