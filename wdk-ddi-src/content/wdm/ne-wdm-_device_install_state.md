---
UID: NE:wdm._DEVICE_INSTALL_STATE
title: "_DEVICE_INSTALL_STATE"
author: windows-driver-content
description: The DEVICE_INSTALL_STATE enumeration describes a device's installation state.
old-location: kernel\device_install_state.htm
old-project: kernel
ms.assetid: 82b702ae-ea62-4bc1-ad92-467eba027e3d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PDEVICE_INSTALL_STATE, ,, A, C, D, DEVICE_INSTALL_STATE, DEVICE_INSTALL_STATE enumeration [Kernel-Mode Driver Architecture], E, I, InstallStateFailedInstall, InstallStateFinishInstall, InstallStateInstalled, InstallStateNeedsReinstall, L, N, P, PDEVICE_INSTALL_STATE, PDEVICE_INSTALL_STATE enumeration pointer [Kernel-Mode Driver Architecture], S, T, V, _, _DEVICE_INSTALL_STATE, kernel.device_install_state, sysenum_ba359e9d-17fd-43c7-8efd-ce6c61f46be6.xml, wdm/DEVICE_INSTALL_STATE, wdm/InstallStateFailedInstall, wdm/InstallStateFinishInstall, wdm/InstallStateInstalled, wdm/InstallStateNeedsReinstall, wdm/PDEVICE_INSTALL_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	DEVICE_INSTALL_STATE
product: Windows
targetos: Windows
req.typenames: DEVICE_INSTALL_STATE, *PDEVICE_INSTALL_STATE
req.product: Windows 10 or later.
---

# _DEVICE_INSTALL_STATE enumeration


## -description


The <b>DEVICE_INSTALL_STATE</b> enumeration describes a device's installation state.


## -syntax


````
typedef enum _DEVICE_INSTALL_STATE { 
  InstallStateInstalled       = 0,
  InstallStateNeedsReinstall  = 1,
  InstallStateFailedInstall   = 2,
  InstallStateFinishInstall   = 3
} DEVICE_INSTALL_STATE, *PDEVICE_INSTALL_STATE;
````


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



The <a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a> routine supplies a <b>DEVICE_INSTALL_STATE</b> enumeration value when a driver requests <b>DevicePropertyInstallState</b>. The operating system uses the value as a hint about the install state of the device.




## -see-also

<a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a>



<a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_INSTALL_STATE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

