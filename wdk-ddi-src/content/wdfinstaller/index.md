---
UID: NA:wdfinstaller
ms.assetid: 7d20668c-a0dd-32f7-aeef-8188b28028fb
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfinstaller.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfinstaller.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_COINSTALLER_INSTALL_OPTIONS_INIT function](nf-wdfinstaller-wdf_coinstaller_install_options_init.md) | The WDF_COINSTALLER_INSTALL_OPTIONS_INIT function initializes a WDF_COINSTALLER_INSTALL_OPTIONS structure. |
| [WdfPostDeviceInstall function](nf-wdfinstaller-wdfpostdeviceinstall.md) | The co-installer's WdfPostDeviceInstall function performs any operations that the co-installer might require after a non-Plug and Play (PnP) driver's installer has created the driver's kernel-mode service. |
| [WdfPostDeviceRemove function](nf-wdfinstaller-wdfpostdeviceremove.md) | The co-installer's WdfPostDeviceRemove function performs any operations that the co-installer might require after a non-Plug and Play (PnP) driver's installer has deleted the driver's kernel-mode service. |
| [WdfPreDeviceInstall function](nf-wdfinstaller-wdfpredeviceinstall.md) | The co-installer's WdfPreDeviceInstall function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service. |
| [WdfPreDeviceInstallEx function](nf-wdfinstaller-wdfpredeviceinstallex.md) | The co-installer's WdfPreDeviceInstallEx function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service. |
| [WdfPreDeviceRemove function](nf-wdfinstaller-wdfpredeviceremove.md) | The co-installer's WdfPreDeviceRemove function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer deletes the driver's kernel-mode service. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_COINSTALLER_INSTALL_OPTIONS structure](ns-wdfinstaller-_wdf_coinstaller_install_options.md) | The WDF_COINSTALLER_INSTALL_OPTIONS structure contains installation options that a framework-based driver's installer can specify to the framework's co-installer. |
