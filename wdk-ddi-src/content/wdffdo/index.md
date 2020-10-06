---
UID: NA:wdffdo
title: Wdffdo.h header
ms.assetid: 3b4b9cb8-8139-3f49-a13d-762e25571789
ms.date: 05/09/2018
keywords: ["Wdffdo.h header"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: wdf
f1_keywords:
 - wdffdo
 - wdffdo/wdffdo
---

# Wdffdo.h header


## -description

This header is used by wdf. For more information, see:

- [Windows Driver Framework](../_wdf/index.md)
- [wdfdevice.h header](../wdfdevice/index.md)
- [wdfpdo.h header](../wdfpdo/index.md)

This topic orders the Windows Driver Frameworks (WDF) functional device object (FDO) reference by category.

The categories on this page are:

- [Framework FDO Event Callbacks](#framework-fdo-event-callbacks)
- [Framework FDO Initialization Methods](#framework-fdo-initialization-methods)
- [Framework FDO Methods](#framework-fdo-methods)
- [Framework FDO Structures and Initialization Functions](#framework-fdo-structures-and-initialization-functions)

## Framework FDO Event Callbacks

- [*EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS*](./nc-wdffdo-evt_wdf_device_filter_resource_requirements.md)
- [*EvtDeviceRemoveAddedResources*](./nc-wdffdo-evt_wdf_device_remove_added_resources.md)

## Framework FDO Initialization Methods

- [**WdfFdoInitAllocAndQueryProperty**](./nf-wdffdo-wdffdoinitallocandqueryproperty.md)
- [**WdfFdoInitAllocAndQueryPropertyEx**](./nf-wdffdo-wdffdoinitallocandquerypropertyex.md)
- [**WdfFdoInitOpenRegistryKey**](./nf-wdffdo-wdffdoinitopenregistrykey.md)
- [**WdfFdoInitQueryProperty**](./nf-wdffdo-wdffdoinitqueryproperty.md)
- [**WdfFdoInitQueryPropertyEx**](./nf-wdffdo-wdffdoinitquerypropertyex.md)
- [**WdfFdoInitSetDefaultChildListConfig**](./nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md)
- [**WdfFdoInitSetEventCallbacks**](./nf-wdffdo-wdffdoinitseteventcallbacks.md)
- [**WdfFdoInitSetFilter**](./nf-wdffdo-wdffdoinitsetfilter.md)
- [**WdfFdoInitWdmGetPhysicalDevice**](./nf-wdffdo-wdffdoinitwdmgetphysicaldevice.md)

## Framework FDO Methods

- [**WdfFdoAddStaticChild**](./nf-wdffdo-wdffdoaddstaticchild.md)
- [**WdfFdoGetDefaultChildList**](./nf-wdffdo-wdffdogetdefaultchildlist.md)
- [**WdfFdoInitAllocAndQueryProperty**](./nf-wdffdo-wdffdoinitallocandqueryproperty.md)
- [**WdfFdoInitOpenRegistryKey**](./nf-wdffdo-wdffdoinitopenregistrykey.md)
- [**WdfFdoInitQueryProperty**](./nf-wdffdo-wdffdoinitqueryproperty.md)
- [**WdfFdoInitSetDefaultChildListConfig**](./nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md)
- [**WdfFdoInitSetEventCallbacks**](./nf-wdffdo-wdffdoinitseteventcallbacks.md)
- [**WdfFdoInitSetFilter**](./nf-wdffdo-wdffdoinitsetfilter.md)
- [**WdfFdoInitWdmGetPhysicalDevice**](./nf-wdffdo-wdffdoinitwdmgetphysicaldevice.md)
- [**WdfFdoLockStaticChildListForIteration**](./nf-wdffdo-wdffdolockstaticchildlistforiteration.md)
- [**WdfFdoQueryForInterface**](./nf-wdffdo-wdffdoqueryforinterface.md)
- [**WdfFdoRetrieveNextStaticChild**](./nf-wdffdo-wdffdoretrievenextstaticchild.md)
- [**WdfFdoUnlockStaticChildListFromIteration**](./nf-wdffdo-wdffdounlockstaticchildlistfromiteration.md)

## Framework FDO Structures and Initialization Functions

- [**WDF_FDO_EVENT_CALLBACKS**](./ns-wdffdo-_wdf_fdo_event_callbacks.md)
- [**WDF_FDO_EVENT_CALLBACKS_INIT**](./nf-wdffdo-wdf_fdo_event_callbacks_init.md)