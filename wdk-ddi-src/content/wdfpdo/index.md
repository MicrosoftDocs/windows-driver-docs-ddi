---
UID: NA:wdfpdo
title: Wdfpdo.h header
ms.assetid: ac342a18-24b7-36b8-9447-8ee711b42a24
ms.date: 05/09/2018
keywords: ["Wdfpdo.h header"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: wdf
f1_keywords:
 - wdfpdo
 - wdfpdo/wdfpdo
---

# Wdfpdo.h header


## -description

This header is used by wdf. For more information, see:

- [Windows Driver Framework](../_wdf/index.md)
- [wdfdevice.h header](../wdfdevice/index.md)
- [wdffdo.h header](../wdffdo/index.md)

This topic orders the Windows Driver Frameworks (WDF) physical device object (PDO) reference by category.

The categories on this page are:

- [Framework PDO Event Callbacks](#framework-pdo-event-callbacks)
- [Framework PDO Initialization Methods](#framework-pdo-initialization-methods)
- [Framework PDO Methods](#framework-pdo-methods)
- [Framework PDO Structures and Initialization Functions](#framework-pdo-structures-and-initialization-functions)

## Framework PDO Event Callbacks

- [*EvtDeviceDisableWakeAtBus*](./nc-wdfpdo-evt_wdf_device_disable_wake_at_bus.md)
- [*EvtDeviceEject*](./nc-wdfpdo-evt_wdf_device_eject.md)
- [*EvtDeviceEnableWakeAtBus*](./nc-wdfpdo-evt_wdf_device_enable_wake_at_bus.md)
- [*EvtDeviceReportedMissing*](./nc-wdfpdo-evt_wdf_device_reported_missing.md)
- [*EvtDeviceResourceRequirementsQuery*](./nc-wdfpdo-evt_wdf_device_resource_requirements_query.md)
- [*EvtDeviceResourcesQuery*](./nc-wdfpdo-evt_wdf_device_resources_query.md)
- [*EvtDeviceSetLock*](./nc-wdfpdo-evt_wdf_device_set_lock.md)

## Framework PDO Initialization Methods

- [**WdfPdoInitAddCompatibleID**](./nf-wdfpdo-wdfpdoinitaddcompatibleid.md)
- [**WdfPdoInitAddDeviceText**](./nf-wdfpdo-wdfpdoinitadddevicetext.md)
- [**WdfPdoInitAddHardwareID**](./nf-wdfpdo-wdfpdoinitaddhardwareid.md)
- [**WdfPdoInitAllocate**](./nf-wdfpdo-wdfpdoinitallocate.md)
- [**WdfPdoInitAllowForwardingRequestToParent**](./nf-wdfpdo-wdfpdoinitallowforwardingrequesttoparent.md)
- [**WdfPdoInitAssignContainerID**](./nf-wdfpdo-wdfpdoinitassigncontainerid.md)
- [**WdfPdoInitAssignDeviceID**](./nf-wdfpdo-wdfpdoinitassigndeviceid.md)
- [**WdfPdoInitAssignInstanceID**](./nf-wdfpdo-wdfpdoinitassigninstanceid.md)
- [**WdfPdoInitAssignRawDevice**](./nf-wdfpdo-wdfpdoinitassignrawdevice.md)
- [**WdfPdoInitSetDefaultLocale**](./nf-wdfpdo-wdfpdoinitsetdefaultlocale.md)
- [**WdfPdoInitSetEventCallbacks**](./nf-wdfpdo-wdfpdoinitseteventcallbacks.md)

## Framework PDO Methods

- [**WdfPdoInitAddCompatibleID**](./nf-wdfpdo-wdfpdoinitaddcompatibleid.md)
- [**WdfPdoAddEjectionRelationsPhysicalDevice**](./nf-wdfpdo-wdfpdoaddejectionrelationsphysicaldevice.md)
- [**WdfPdoClearEjectionRelationsDevices**](./nf-wdfpdo-wdfpdoclearejectionrelationsdevices.md)
- [**WdfPdoGetParent**](./nf-wdfpdo-wdfpdogetparent.md)
- [**WdfPdoInitAddDeviceText**](./nf-wdfpdo-wdfpdoinitadddevicetext.md)
- [**WdfPdoInitAddHardwareID**](./nf-wdfpdo-wdfpdoinitaddhardwareid.md)
- [**WdfPdoInitAllocate**](./nf-wdfpdo-wdfpdoinitallocate.md)
- [**WdfPdoInitAllowForwardingRequestToParent**](./nf-wdfpdo-wdfpdoinitallowforwardingrequesttoparent.md)
- [**WdfPdoInitAssignContainerID**](./nf-wdfpdo-wdfpdoinitassigncontainerid.md)
- [**WdfPdoInitAssignDeviceID**](./nf-wdfpdo-wdfpdoinitassigndeviceid.md)
- [**WdfPdoInitAssignInstanceID**](./nf-wdfpdo-wdfpdoinitassigninstanceid.md)
- [**WdfPdoInitAssignRawDevice**](./nf-wdfpdo-wdfpdoinitassignrawdevice.md)
- [**WdfPdoInitSetDefaultLocale**](./nf-wdfpdo-wdfpdoinitsetdefaultlocale.md)
- [**WdfPdoInitSetEventCallbacks**](./nf-wdfpdo-wdfpdoinitseteventcallbacks.md)
- [**WdfPdoMarkMissing**](./nf-wdfpdo-wdfpdomarkmissing.md)
- [**WdfPdoRemoveEjectionRelationsPhysicalDevice**](./nf-wdfpdo-wdfpdoremoveejectionrelationsphysicaldevice.md)
- [**WdfPdoRequestEject**](./nf-wdfpdo-wdfpdorequesteject.md)
- [**WdfPdoRetrieveAddressDescription**](./nf-wdfpdo-wdfpdoretrieveaddressdescription.md)
- [**WdfPdoRetrieveIdentificationDescription**](./nf-wdfpdo-wdfpdoretrieveidentificationdescription.md)
- [**WdfPdoUpdateAddressDescription**](./nf-wdfpdo-wdfpdoupdateaddressdescription.md)

## Framework PDO Structures and Initialization Functions

- [**WDF_PDO_EVENT_CALLBACKS**](./ns-wdfpdo-_wdf_pdo_event_callbacks.md)
- [**WDF_PDO_EVENT_CALLBACKS_INIT**](./nf-wdfpdo-wdf_pdo_event_callbacks_init.md)