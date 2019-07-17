---
UID: NE:wdm._DEVICE_INSTALL_STATE
title: _DEVICE_INSTALL_STATE (wdm.h)
description: The DEVICE_INSTALL_STATE enumeration describes a device's installation state.
old-location: kernel\device_install_state.htm
tech.root: kernel
ms.assetid: 82b702ae-ea62-4bc1-ad92-467eba027e3d
ms.date: 04/30/2018
ms.keywords: "*PDEVICE_INSTALL_STATE, DEVICE_INSTALL_STATE, DEVICE_INSTALL_STATE enumeration [Kernel-Mode Driver Architecture], InstallStateFailedInstall, InstallStateFinishInstall, InstallStateInstalled, InstallStateNeedsReinstall, PDEVICE_INSTALL_STATE, PDEVICE_INSTALL_STATE enumeration pointer [Kernel-Mode Driver Architecture], _DEVICE_INSTALL_STATE, kernel.device_install_state, sysenum_ba359e9d-17fd-43c7-8efd-ce6c61f46be6.xml, wdm/DEVICE_INSTALL_STATE, wdm/InstallStateFailedInstall, wdm/InstallStateFinishInstall, wdm/InstallStateInstalled, wdm/InstallStateNeedsReinstall, wdm/PDEVICE_INSTALL_STATE"
ms.topic: enum
f1_keywords:
 - "wdm/DEVICE_INSTALL_STATE"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later versions of the Windows operating system.
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
- HeaderDef
api_location:
- wdm.h
api_name:
- DEVICE_INSTALL_STATE
product:
- Windows
targetos: Windows
req.typenames: DEVICE_INSTALL_STATE, *PDEVICE_INSTALL_STATE
---

# _DEVICE_INSTALL_STATE enumeration


## -description


The <b>DEVICE_INSTALL_STATE</b> enumeration describes a device's installation state.


## -enum-fields




### -field InstallStateInstalled

The device is installed.


### -field InstallStateNeedsReinstall

The system will try to reinstall the device on a later enumeration.


### -field InstallStateFailedInstall

The device did not install properly.


### -field InstallStateFinishInstall

The installation of this device is not yet complete. 


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdeviceproperty">IoGetDeviceProperty</a> routine supplies a <b>DEVICE_INSTALL_STATE</b> enumeration value when a driver requests <b>DevicePropertyInstallState</b>. The operating system uses the value as a hint about the install state of the device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfwdm/ne-wudfwdm-device_registry_property">DEVICE_REGISTRY_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdeviceproperty">IoGetDeviceProperty</a>
 

 

