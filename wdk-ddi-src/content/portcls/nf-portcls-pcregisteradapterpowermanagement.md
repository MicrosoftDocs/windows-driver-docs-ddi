---
UID: NF:portcls.PcRegisterAdapterPowerManagement
title: PcRegisterAdapterPowerManagement function (portcls.h)
description: The PcRegisterAdapterPowerManagement function registers the adapter's power-management interface with the PortCls system driver.
old-location: audio\pcregisteradapterpowermanagement.htm
tech.root: audio
ms.assetid: a9e2537d-4d67-4495-b391-55f885b7041a
ms.date: 05/08/2018
keywords: ["PcRegisterAdapterPowerManagement function"]
ms.keywords: PcRegisterAdapterPowerManagement, PcRegisterAdapterPowerManagement function [Audio Devices], audio.pcregisteradapterpowermanagement, audpc-routines_524bed01-a6ba-492c-9e18-7495de15be46.xml, portcls/PcRegisterAdapterPowerManagement
f1_keywords:
 - "portcls/PcRegisterAdapterPowerManagement"
 - "PcRegisterAdapterPowerManagement"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available starting in Windows 2000.
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
- PcRegisterAdapterPowerManagement
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcRegisterAdapterPowerManagement function


## -description


The <b>PcRegisterAdapterPowerManagement</b> function registers the adapter's power-management interface with the PortCls system driver.


## -parameters




### -param Unknown

<p>Pointer to an adapter driver object's <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown"><b>IUnknown</b></a> interface. The PortCls system driver queries this object for its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iadapterpowermanagement">IAdapterPowerManagement</a> interface.</p>


### -param pvContext1 [in]

Pointer to the adapter's <a href="https://docs.microsoft.com/windows-hardware/drivers/">functional device object (FDO)</a>. This parameter is a pointer to a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> but is cast to type PVOID.


## -returns



<b>PcRegisterAdapterPowerManagement</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iadapterpowermanagement">IAdapterPowerManagement</a>
 

 

