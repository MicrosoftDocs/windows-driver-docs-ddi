---
UID: NA:wdfpdo
ms.assetid: ac342a18-24b7-36b8-9447-8ee711b42a24
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfpdo.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfpdo.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_PDO_EVENT_CALLBACKS_INIT function](nf-wdfpdo-wdf_pdo_event_callbacks_init.md) | The WDF_PDO_EVENT_CALLBACKS_INIT function initializes a WDF_PDO_EVENT_CALLBACKS structure. |
| [WdfPdoAddEjectionRelationsPhysicalDevice function](nf-wdfpdo-wdfpdoaddejectionrelationsphysicaldevice.md) | The WdfPdoAddEjectionRelationsPhysicalDevice method indicates that a specified device is ejected when another specified device is ejected. |
| [WdfPdoClearEjectionRelationsDevices function](nf-wdfpdo-wdfpdoclearejectionrelationsdevices.md) | The WdfPdoClearEjectionRelationsDevices method removes all devices from the list of devices that must be ejected when a specified device is ejected. |
| [WdfPdoGetParent function](nf-wdfpdo-wdfpdogetparent.md) | The WdfPdoGetParent method returns a handle to the framework device object that represents the parent device of a specified device. |
| [WdfPdoInitAddCompatibleID function](nf-wdfpdo-wdfpdoinitaddcompatibleid.md) | The WdfPdoInitAddCompatibleID method adds a compatible ID to the list of compatible IDs for a child device. |
| [WdfPdoInitAddDeviceText function](nf-wdfpdo-wdfpdoinitadddevicetext.md) | The WdfPdoInitAddDeviceText method adds a device description and device location to a device, for a specified locale. |
| [WdfPdoInitAddHardwareID function](nf-wdfpdo-wdfpdoinitaddhardwareid.md) | The WdfPdoInitAddHardwareID method adds a hardware ID to the list of hardware IDs for a child device. |
| [WdfPdoInitAllocate function](nf-wdfpdo-wdfpdoinitallocate.md) | The WdfPdoInitAllocate method allocates a WDFDEVICE_INIT structure for a framework-based bus driver, which the bus driver uses when reporting a new device. |
| [WdfPdoInitAllowForwardingRequestToParent function](nf-wdfpdo-wdfpdoinitallowforwardingrequesttoparent.md) | The WdfPdoInitAllowForwardingRequestToParent method enables a driver's ability to call WdfRequestForwardToParentDeviceIoQueue. |
| [WdfPdoInitAssignContainerID function](nf-wdfpdo-wdfpdoinitassigncontainerid.md) | The WdfPdoInitAssignContainerID method updates the container ID for a child device. |
| [WdfPdoInitAssignDeviceID function](nf-wdfpdo-wdfpdoinitassigndeviceid.md) | The WdfPdoInitAssignDeviceID method updates the device ID for a child device. |
| [WdfPdoInitAssignInstanceID function](nf-wdfpdo-wdfpdoinitassigninstanceid.md) | The WdfPdoInitAssignInstanceID method updates the instance ID for a child device. |
| [WdfPdoInitAssignRawDevice function](nf-wdfpdo-wdfpdoinitassignrawdevice.md) | The WdfPdoInitAssignRawDevice method indicates that the calling driver can support a specified device in raw mode. |
| [WdfPdoInitSetDefaultLocale function](nf-wdfpdo-wdfpdoinitsetdefaultlocale.md) | The WdfPdoInitSetDefaultLocale method sets a device's default locale. |
| [WdfPdoInitSetEventCallbacks function](nf-wdfpdo-wdfpdoinitseteventcallbacks.md) | The WdfPdoInitSetEventCallbacks method registers a bus driver's event callback functions. |
| [WdfPdoMarkMissing function](nf-wdfpdo-wdfpdomarkmissing.md) | The WdfPdoMarkMissing method informs the framework that a device is no longer accessible. |
| [WdfPdoRemoveEjectionRelationsPhysicalDevice function](nf-wdfpdo-wdfpdoremoveejectionrelationsphysicaldevice.md) | The WdfPdoRemoveEjectionRelationsPhysicalDevice method removes a specified device from the list of devices that must be ejected when another specified device is ejected. |
| [WdfPdoRequestEject function](nf-wdfpdo-wdfpdorequesteject.md) | The WdfPdoRequestEject method informs the framework that a specified device is about to be ejected from its docking station. |
| [WdfPdoRetrieveAddressDescription function](nf-wdfpdo-wdfpdoretrieveaddressdescription.md) | The WdfPdoRetrieveAddressDescription method retrieves the address description that is associated with a specified framework device object. |
| [WdfPdoRetrieveIdentificationDescription function](nf-wdfpdo-wdfpdoretrieveidentificationdescription.md) | The WdfPdoRetrieveIdentificationDescription method retrieves the identification description that is associated with a specified framework device object. |
| [WdfPdoUpdateAddressDescription function](nf-wdfpdo-wdfpdoupdateaddressdescription.md) | The WdfPdoUpdateAddressDescription method updates the address description that is associated with a specified framework device object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_DEVICE_DISABLE_WAKE_AT_BUS callback](nc-wdfpdo-evt_wdf_device_disable_wake_at_bus.md) | A bus driver's EvtDeviceDisableWakeAtBus event callback function performs bus-level operations that disable the ability of one of the bus's devices to trigger a wake-up signal on the bus. |
| [EVT_WDF_DEVICE_EJECT callback](nc-wdfpdo-evt_wdf_device_eject.md) | A driver's EvtDeviceEject event callback function handles operations that are necessary to eject a device from its docking station. |
| [EVT_WDF_DEVICE_ENABLE_WAKE_AT_BUS callback](nc-wdfpdo-evt_wdf_device_enable_wake_at_bus.md) | A bus driver's EvtDeviceEnableWakeAtBus event callback function performs bus-level operations that enable one of the bus's devices to trigger a wake-up signal on the bus. |
| [EVT_WDF_DEVICE_REPORTED_MISSING callback](nc-wdfpdo-evt_wdf_device_reported_missing.md) | A bus driver's EvtDeviceReportedMissing event callback function informs the driver that the framework has reported the physical device object (PDO) missing to the Plug and Play manager. |
| [EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback](nc-wdfpdo-evt_wdf_device_resource_requirements_query.md) | A bus driver's EvtDeviceResourceRequirementsQuery event callback function creates a resource requirements list that represents the device's required hardware resources. |
| [EVT_WDF_DEVICE_SET_LOCK callback](nc-wdfpdo-evt_wdf_device_set_lock.md) | A driver's EvtDeviceSetLock event callback function locks the specified device so that it cannot be ejected, or unlocks the device so that it can be ejected. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_PDO_EVENT_CALLBACKS structure](ns-wdfpdo-_wdf_pdo_event_callbacks.md) | The WDF_PDO_EVENT_CALLBACKS structure is the dispatch table for a bus driver's event callback functions. |
