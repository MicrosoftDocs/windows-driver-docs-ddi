---
UID: NA:wdtfdriversetupsystemaction
ms.assetid: e463b19f-90ca-388e-8742-9094e47bef38
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdtfdriversetupsystemaction.h header



This header is used by dtf. For more information, see
- [dtf](../_dtf/index.md)

Wdtfdriversetupsystemaction.h contain these programming interfaces:


## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IWDTFDriverSetupSystemAction2 interface](nn-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2.md) | Defines operations that control the system during driver setup. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IWDTFDriverSetupSystemAction2::ClearTriageLogs method](nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-cleartriagelogs.md) | Clears the system device setup triage logs. |
| [IWDTFDriverSetupSystemAction2::ImportDriverPackage method](nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-importdriverpackage.md) | Imports a driver packge to the system driver store. |
| [IWDTFDriverSetupSystemAction2::IsImported method](nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-isimported.md) | Returns a value that indicates whether a package has already been imported. |
| [IWDTFDriverSetupSystemAction2::RemoveDriverPackage method](nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-removedriverpackage.md) | Removes a driver package from the driver store. |
| [IWDTFDriverSetupSystemAction2::RescanAllDevices method](nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-rescanalldevices.md) | Re-enumerates all devices in the system. |
| [IWDTFDriverSetupSystemAction2::SnapTriageLogs method](nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-snaptriagelogs.md) | Copies the driver setup triage logs. |
| [IWDTFDriverSetupSystemAction2::WaitNoPendingInstallEvents method](nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-waitnopendinginstallevents.md) | Waits until all device installations have completed. |
