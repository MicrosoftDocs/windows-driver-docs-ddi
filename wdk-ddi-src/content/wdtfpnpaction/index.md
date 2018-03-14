---
UID: NA:wdtfpnpaction
ms.assetid: b137902b-ce9b-3b57-a450-c028e6fdfde4
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdtfpnpaction.h header



This header is used by dtf. For more information, see
- [dtf](../_dtf/index.md)

Wdtfpnpaction.h contain these programming interfaces:


## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IWDTFPNPAction2 interface](nn-wdtfpnpaction-iwdtfpnpaction2.md) | Defines operations and properties for the Plug and Play (PNP) device-related test interfaces. |
| [IWDTFPNPActions2 interface](nn-wdtfpnpaction-iwdtfpnpactions2.md) | Defines operations and properties for the collection of Plug and Play (PNP) device-related test interfaces. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IWDTFPNPAction2::DisableDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-disabledevice.md) | Disables the target device. |
| [IWDTFPNPAction2::EDTCancelRemoveDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-edtcancelremovedevice.md) | Sends an IRP_MN_CANCEL_REMOVE_DEVICE event to the target device. |
| [IWDTFPNPAction2::EDTCancelStopDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-edtcancelstopdevice.md) | Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device. |
| [IWDTFPNPAction2::EDTSurpriseRemoveDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-edtsurpriseremovedevice.md) | Sends an IRP_MN_SURPRISE_REMOVAL event to the target device. |
| [IWDTFPNPAction2::EDTTryStopDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevice.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device. |
| [IWDTFPNPAction2::EDTTryStopDeviceFailRestart method](nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevicefailrestart.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device and then fail the subsequent device restart. |
| [IWDTFPNPAction2::EDTTryStopDeviceRequestNewResources method](nf-wdtfpnpaction-iwdtfpnpaction2-edttrystopdevicerequestnewresources.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device and assign new resources to the target device. |
| [IWDTFPNPAction2::EnableDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-enabledevice.md) | Enables the target device. |
| [IWDTFPNPAction2::RemoveDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-removedevice.md) | Removes the device. |
| [IWDTFPNPAction2::RequestEjectDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-requestejectdevice.md) | Initiates a device eject. |
| [IWDTFPNPAction2::RescanDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-rescandevice.md) | Rescans the target device. |
| [IWDTFPNPAction2::RescanParentDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-rescanparentdevice.md) | Rescans and re-enumerates the target device's parent device. |
| [IWDTFPNPAction2::RestartDevice method](nf-wdtfpnpaction-iwdtfpnpaction2-restartdevice.md) | Initiates a device restart. |
| [IWDTFPNPActions2::DisableDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-disabledevice.md) | Disables the target device. |
| [IWDTFPNPActions2::EDTCancelRemoveDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-edtcancelremovedevice.md) | Sends an IRP_MN_CANCEL_REMOVE_DEVICE event to the target device. |
| [IWDTFPNPActions2::EDTCancelStopDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-edtcancelstopdevice.md) | Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device. |
| [IWDTFPNPActions2::EDTSurpriseRemoveDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-edtsurpriseremovedevice.md) | Sends an IRP_MN_SURPRISE_REMOVAL event to the target device. |
| [IWDTFPNPActions2::EDTTryStopDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-edttrystopdevice.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device. |
| [IWDTFPNPActions2::EDTTryStopDeviceFailRestart method](nf-wdtfpnpaction-iwdtfpnpactions2-edttrystopdevicefailrestart.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device and then fail the subsequent device restart. |
| [IWDTFPNPActions2::EDTTryStopDeviceRequestNewResources method](nf-wdtfpnpaction-iwdtfpnpactions2-edttrystopdevicerequestnewresources.md) | Attempts to send an IRP_MN_STOP_DEVICE event to the target device and assign new resources to the target device. |
| [IWDTFPNPActions2::EnableDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-enabledevice.md) | Enables the target device. |
| [IWDTFPNPActions2::RemoveDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-removedevice.md) | Removes the device. |
| [IWDTFPNPActions2::RequestEjectDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-requestejectdevice.md) | Initiates a device eject. |
| [IWDTFPNPActions2::RescanDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-rescandevice.md) | Rescans the target device. |
| [IWDTFPNPActions2::RescanParentDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-rescanparentdevice.md) | Rescans and re-enumerates the target device's parent device. |
| [IWDTFPNPActions2::RestartDevice method](nf-wdtfpnpaction-iwdtfpnpactions2-restartdevice.md) | Initiates a device restart. |
