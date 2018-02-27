---
UID: NA:wdtfdriverpackageaction
ms.assetid: 3b7d1682-5abf-3f29-aa0b-4c77e50e2a62
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdtfdriverpackageaction.h header



This header is used by dtf. For more information, see
- [dtf](../_dtf/index.md)

Wdtfdriverpackageaction.h contain these programming interfaces:


## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IWDTFDriverPackageAction2 interface](nn-wdtfdriverpackageaction-iwdtfdriverpackageaction2.md) | Defines operations and properties that represent a driver package for imported and pre-imported driver packages. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IWDTFDriverPackageAction2::Compare method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-compare.md) | Compares two driver packages. |
| [IWDTFDriverPackageAction2::GetQueryForDeviceThatCanUsePackage method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-getqueryfordevicethatcanusepackage.md) | Returns an SDEL statement that queries for all devices that can use the driver package. |
| [IWDTFDriverPackageAction2::GetQueryForDeviceUsingPackage method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-getqueryfordeviceusingpackage.md) | Returns an SDEL statement that queries for all devices that use the driver package. |
| [IWDTFDriverPackageAction2::SetPackageInfFileName method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-setpackageinffilename.md) | Sets the pre-imported driver package path. |
| [IWDTFDriverPackageAction2::get_CatalogFile method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_catalogfile.md) | Gets the catalog file name. |
| [IWDTFDriverPackageAction2::get_ClassGuid method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_classguid.md) | Gets the class GUID. |
| [IWDTFDriverPackageAction2::get_ClassName method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_classname.md) | Gets the class name. |
| [IWDTFDriverPackageAction2::get_Date method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_date.md) | Gets the driver package date. |
| [IWDTFDriverPackageAction2::get_DigitalSigner method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_digitalsigner.md) | Gets the digital signer. |
| [IWDTFDriverPackageAction2::get_HasCatalog method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_hascatalog.md) | Gets a value that indicates whether the driver package has a catalog. |
| [IWDTFDriverPackageAction2::get_InfFileName method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_inffilename.md) | Gets the INF file name. |
| [IWDTFDriverPackageAction2::get_IsDigitalSigned method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_isdigitalsigned.md) | Gets a value that indicates whether the driver package is signed. |
| [IWDTFDriverPackageAction2::get_IsImported method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_isimported.md) | Gets a value that indicates whether the driver package is imported. |
| [IWDTFDriverPackageAction2::get_Provider method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_provider.md) | Gets the driver package provider. |
| [IWDTFDriverPackageAction2::get_Version method](nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_version.md) | Gets the driver package version. |
