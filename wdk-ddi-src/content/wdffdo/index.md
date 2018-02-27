---
UID: NA:wdffdo
ms.assetid: 3b4b9cb8-8139-3f49-a13d-762e25571789
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdffdo.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdffdo.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_FDO_EVENT_CALLBACKS_INIT function](nf-wdffdo-wdf_fdo_event_callbacks_init.md) | The WDF_FDO_EVENT_CALLBACKS_INIT function initializes a WDF_FDO_EVENT_CALLBACKS structure. |
| [WdfFdoAddStaticChild function](nf-wdffdo-wdffdoaddstaticchild.md) | The WdfFdoAddStaticChild method adds a specified device to a function driver's list of child devices that have been identified by static enumeration. |
| [WdfFdoGetDefaultChildList function](nf-wdffdo-wdffdogetdefaultchildlist.md) | The WdfFdoGetDefaultChildList method returns a handle to a specified device's default child list. |
| [WdfFdoInitAllocAndQueryProperty function](nf-wdffdo-wdffdoinitallocandqueryproperty.md) | The WdfFdoInitAllocAndQueryProperty method allocates a buffer and retrieves a specified device property. |
| [WdfFdoInitAllocAndQueryPropertyEx function](nf-wdffdo-wdffdoinitallocandquerypropertyex.md) | The WdfFdoInitAllocAndQueryPropertyEx method allocates a buffer and retrieves a specified device property. |
| [WdfFdoInitOpenRegistryKey function](nf-wdffdo-wdffdoinitopenregistrykey.md) | The WdfFdoInitOpenRegistryKey method opens a device's hardware key or a driver's software key in the registry and creates a framework registry-key object that represents the registry key. |
| [WdfFdoInitQueryProperty function](nf-wdffdo-wdffdoinitqueryproperty.md) | The WdfFdoInitQueryProperty method retrieves a specified device property. |
| [WdfFdoInitQueryPropertyEx function](nf-wdffdo-wdffdoinitquerypropertyex.md) | The WdfFdoInitQueryPropertyEx method retrieves a specified device property. |
| [WdfFdoInitSetDefaultChildListConfig function](nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md) | The WdfFdoInitSetDefaultChildListConfig method configures a bus driver's default child list. |
| [WdfFdoInitSetEventCallbacks function](nf-wdffdo-wdffdoinitseteventcallbacks.md) | The WdfFdoInitSetEventCallbacks method registers a framework-based function driver's event callback functions, for a specified device. |
| [WdfFdoInitSetFilter function](nf-wdffdo-wdffdoinitsetfilter.md) | The WdfFdoInitSetFilter method identifies the calling driver as an upper-level or lower-level filter driver, for a specified device. |
| [WdfFdoInitWdmGetPhysicalDevice function](nf-wdffdo-wdffdoinitwdmgetphysicaldevice.md) | The WdfFdoInitWdmGetPhysicalDevice method retrieves a device's WDM physical device object (PDO). |
| [WdfFdoLockStaticChildListForIteration function](nf-wdffdo-wdffdolockstaticchildlistforiteration.md) | The WdfFdoLockStaticChildListForIteration method prepares the framework for retrieving items from the static child list that belongs to a specified parent device. |
| [WdfFdoQueryForInterface function](nf-wdffdo-wdffdoqueryforinterface.md) | The WdfFdoQueryForInterface method obtains access to another driver's GUID-identified interface. |
| [WdfFdoRetrieveNextStaticChild function](nf-wdffdo-wdffdoretrievenextstaticchild.md) | The WdfFdoRetrieveNextStaticChild method retrieves a handle to the next framework device object in a list of child devices. |
| [WdfFdoUnlockStaticChildListFromIteration function](nf-wdffdo-wdffdounlockstaticchildlistfromiteration.md) | The WdfFdoUnlockStaticChildListFromIteration method unlocks the list of child devices for a specified device and processes any changes to the list that the driver made while the list was locked. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_DEVICE_REMOVE_ADDED_RESOURCES callback](nc-wdffdo-evt_wdf_device_remove_added_resources.md) | A driver's EvtDeviceRemoveAddedResources event callback function removes hardware resources that the driver's EvtDeviceFilterAddResourceRequirements callback function added. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_FDO_EVENT_CALLBACKS structure](ns-wdffdo-_wdf_fdo_event_callbacks.md) | The WDF_FDO_EVENT_CALLBACKS structure contains pointers to a function driver's PnP event callback functions. |
