---
UID: NA:aux_klib
ms.assetid: c8496ac9-e318-30df-baca-c0ea009e04d1
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Aux_Klib.h header



This header is used by Windows kernel. For more information, see
- [Windows kernel](../_kernel/index.md)

Aux_Klib.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [AuxKlibEnumerateSystemFirmwareTables function](nf-aux_klib-auxklibenumeratesystemfirmwaretables.md) | The AuxKlibEnumerateSystemFirmwareTables routine enumerates all system firmware tables of the specified type. |
| [AuxKlibGetBugCheckData function](nf-aux_klib-auxklibgetbugcheckdata.md) | The AuxKlibGetBugCheckData routine retrieves information about a bug check that has just occurred. |
| [AuxKlibGetImageExportDirectory function](nf-aux_klib-auxklibgetimageexportdirectory.md) | The AuxKlibGetImageExportDirectory routine returns an image module's export directory. |
| [AuxKlibGetSystemFirmwareTable function](nf-aux_klib-auxklibgetsystemfirmwaretable.md) | The AuxKlibGetSystemFirmwareTable routine retrieves the specified firmware table from the firmware table provider. |
| [AuxKlibInitialize function](nf-aux_klib-auxklibinitialize.md) | The AuxKlibInitialize routine initializes the Auxiliary Kernel-Mode Library. |
| [AuxKlibQueryModuleInformation function](nf-aux_klib-auxklibquerymoduleinformation.md) | The AuxKlibQueryModuleInformation routine retrieves information about the image modules that the operating system has loaded. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_AUX_MODULE_BASIC_INFO structure](ns-aux_klib-_aux_module_basic_info.md) | The AUX_MODULE_BASIC_INFO structure contains basic information about a loaded image module. |
| [_AUX_MODULE_EXTENDED_INFO structure](ns-aux_klib-_aux_module_extended_info.md) | The AUX_MODULE_EXTENDED_INFO structure contains extended information about a loaded image module. |
| [_KBUGCHECK_DATA structure](ns-aux_klib-_kbugcheck_data.md) | The KBUGCHECK_DATA structure contains bug check parameters. |
