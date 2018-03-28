---
UID: NA:sti
ms.assetid: 68cc0060-fd37-3ec3-a689-419b81682f45
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Sti.h header



This header is used by Imaging devices. For more information, see
- [Imaging devices](../_image/index.md)

Sti.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_ERROR_INFOW structure](ns-sti-_error_infow.md) | The STI_ERROR_INFO structure is used as a parameter for the IStiDevice |
| [_STINOTIFY structure](ns-sti-_stinotify.md) | The STINOTIFY structure is used as a parameter to the IStillImage |
| [_STISUBSCRIBE structure](ns-sti-_stisubscribe.md) | The STISUBSCRIBE structure is used as a parameter for the IStiDevice |
| [_STI_DEVICE_INFORMATIONW structure](ns-sti-_sti_device_informationw.md) | The STI_DEVICE_INFORMATION structure is used as an output parameter for the IStillImage |
| [_STI_DEVICE_STATUS structure](ns-sti-_sti_device_status.md) | The STI_DEVICE_STATUS structure is used as a parameter to the IStiDevice |
| [_STI_DEV_CAPS structure](ns-sti-_sti_dev_caps.md) | The STI_DEV_CAPS structure is used as a parameter to the IStiDevice |
| [_STI_DIAG structure](ns-sti-_sti_diag.md) | The STI_DIAG structure is used as a parameter to the IStiDevice |
| [_STI_WIA_DEVICE_INFORMATIONW structure](ns-sti-_sti_wia_device_informationw.md) | The STI_WIA_DEVICE_INFORMATION structure contains device information. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_STI_DEVICE_MJ_TYPE enumeration](ne-sti-_sti_device_mj_type.md) | The STI_DEVICE_TYPE type identifies the device type of a still image device.The DWORD is divided into a HIWORD containing the major device type, and a LOWORD containing a vendor-defined subtype. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IStiDevice interface](nn-sti-istidevice.md) | This section describes the methods defined for the IStiDevice COM Interface. Method prototypes are contained in Sti.h. |
| [IStillImageW interface](nn-sti-istillimagew.md) | This section describes the methods defined for the IStillImage COM Interface. Method prototypes are contained in Sti.h. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IStiDevice::DeviceReset method](nf-sti-istidevice-devicereset.md) | The IStiDevice |
| [IStiDevice::Diagnostic method](nf-sti-istidevice-diagnostic.md) | The IStiDevice |
| [IStiDevice::Escape method](nf-sti-istidevice-escape.md) | The IStiDevice |
| [IStiDevice::GetCapabilities method](nf-sti-istidevice-getcapabilities.md) | The IStiDevice |
| [IStiDevice::GetLastError method](nf-sti-istidevice-getlasterror.md) | The IStiDevice |
| [IStiDevice::GetLastErrorInfo method](nf-sti-istidevice-getlasterrorinfo.md) | The IStiDevice |
| [IStiDevice::GetLastNotificationData method](nf-sti-istidevice-getlastnotificationdata.md) | The IStiDevice |
| [IStiDevice::GetStatus method](nf-sti-istidevice-getstatus.md) | The IStiDevice |
| [IStiDevice::Initialize method](nf-sti-istidevice-initialize.md) | The IStiDevice |
| [IStiDevice::LockDevice method](nf-sti-istidevice-lockdevice.md) | The IStiDevice |
| [IStiDevice::RawReadCommand method](nf-sti-istidevice-rawreadcommand.md) | The IStiDevice |
| [IStiDevice::RawReadData method](nf-sti-istidevice-rawreaddata.md) | The IStiDevice |
| [IStiDevice::RawWriteCommand method](nf-sti-istidevice-rawwritecommand.md) | The IStiDevice |
| [IStiDevice::RawWriteData method](nf-sti-istidevice-rawwritedata.md) | The IStiDevice |
| [IStiDevice::Release method](nf-sti-istidevice-release.md) | The IStiDevice |
| [IStiDevice::Subscribe method](nf-sti-istidevice-subscribe.md) | The IStiDevice |
| [IStiDevice::UnLockDevice method](nf-sti-istidevice-unlockdevice.md) | The IStiDevice |
| [IStiDevice::UnSubscribe method](nf-sti-istidevice-unsubscribe.md) | The IStiDevice |
| [IStillImageW::CreateDevice method](nf-sti-istillimagew-createdevice.md) | The IStillImage |
| [IStillImageW::EnableHwNotifications method](nf-sti-istillimagew-enablehwnotifications.md) | The IStillImage |
| [IStillImageW::GetDeviceInfo method](nf-sti-istillimagew-getdeviceinfo.md) | The IStillImage |
| [IStillImageW::GetDeviceList method](nf-sti-istillimagew-getdevicelist.md) | The IStillImage |
| [IStillImageW::GetDeviceValue method](nf-sti-istillimagew-getdevicevalue.md) | The IStillImage |
| [IStillImageW::GetHwNotificationState method](nf-sti-istillimagew-gethwnotificationstate.md) | The IStillImage |
| [IStillImageW::GetSTILaunchInformation method](nf-sti-istillimagew-getstilaunchinformation.md) | The IStillImage |
| [IStillImageW::Initialize method](nf-sti-istillimagew-initialize.md) | The IStillImage |
| [IStillImageW::LaunchApplicationForDevice method](nf-sti-istillimagew-launchapplicationfordevice.md) | The IStillImage |
| [IStillImageW::RegisterLaunchApplication method](nf-sti-istillimagew-registerlaunchapplication.md) | The IStillImage |
| [IStillImageW::Release method](nf-sti-istillimagew-release.md) | The IStillImage |
| [IStillImageW::SetDeviceValue method](nf-sti-istillimagew-setdevicevalue.md) | The IStillImage |
| [IStillImageW::SetupDeviceParameters method](nf-sti-istillimagew-setupdeviceparameters.md) | The IStillImage |
| [IStillImageW::UnregisterLaunchApplication method](nf-sti-istillimagew-unregisterlaunchapplication.md) | The IStillImage |
| [IStillImageW::WriteToErrorLog method](nf-sti-istillimagew-writetoerrorlog.md) | The IStillImage |
