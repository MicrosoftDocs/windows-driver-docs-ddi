---
UID: NA:wdfpdo
author: windows-driver-content
ms.assetid: ac342a18-24b7-36b8-9447-8ee711b42a24
ms.author: windowsdriverdev
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: wdf
---

# Wdfpdo.h header


## -description


This header is used by wdf. For more information, see:

- [Windows Driver Framework](../_wdf/index.md)
- [wdfdevice.h header](../wdfdevice/index.md)
- [wdffdo.h header](../wdffdo/index.md)

This topic orders the Windows Driver Frameworks (WDF) physical device object (PDO) reference by category.

The categories on this page are:

-   [Framework PDO Event Callbacks](#framework-pdo-event-callbacks)
-   [Framework PDO Initialization Methods](#framework-pdo-initialization-methods)
-   [Framework PDO Methods](#framework-pdo-methods)
-   [Framework PDO Structures and Initialization Functions](#framework-pdo-structures-and-initialization-functions)

## Framework PDO Event Callbacks

-   [*EvtDeviceDisableWakeAtBus*](https://msdn.microsoft.com/library/windows/hardware/ff540858)
-   [*EvtDeviceEject*](https://msdn.microsoft.com/library/windows/hardware/ff540863)
-   [*EvtDeviceEnableWakeAtBus*](https://msdn.microsoft.com/library/windows/hardware/ff540866)
-   [*EvtDeviceReportedMissing*](https://msdn.microsoft.com/library/windows/hardware/hh406360)
-   [*EvtDeviceResourceRequirementsQuery*](https://msdn.microsoft.com/library/windows/hardware/ff540894)
-   [*EvtDeviceResourcesQuery*](https://msdn.microsoft.com/library/windows/hardware/ff540895)
-   [*EvtDeviceSetLock*](https://msdn.microsoft.com/library/windows/hardware/ff540909)

## Framework PDO Initialization Methods

-   [**WdfPdoInitAddCompatibleID**](https://msdn.microsoft.com/library/windows/hardware/ff548776)
-   [**WdfPdoInitAddDeviceText**](https://msdn.microsoft.com/library/windows/hardware/ff548780)
-   [**WdfPdoInitAddHardwareID**](https://msdn.microsoft.com/library/windows/hardware/ff548784)
-   [**WdfPdoInitAllocate**](https://msdn.microsoft.com/library/windows/hardware/ff548786)
-   [**WdfPdoInitAllowForwardingRequestToParent**](https://msdn.microsoft.com/library/windows/hardware/ff548789)
-   [**WdfPdoInitAssignContainerID**](https://msdn.microsoft.com/library/windows/hardware/ff548792)
-   [**WdfPdoInitAssignDeviceID**](https://msdn.microsoft.com/library/windows/hardware/ff548797)
-   [**WdfPdoInitAssignInstanceID**](https://msdn.microsoft.com/library/windows/hardware/ff548799)
-   [**WdfPdoInitAssignRawDevice**](https://msdn.microsoft.com/library/windows/hardware/ff548802)
-   [**WdfPdoInitSetDefaultLocale**](https://msdn.microsoft.com/library/windows/hardware/ff548803)
-   [**WdfPdoInitSetEventCallbacks**](https://msdn.microsoft.com/library/windows/hardware/ff548805)

## Framework PDO Methods

-   [**WdfPdoInitAddCompatibleID**](https://msdn.microsoft.com/library/windows/hardware/ff548776)
-   [**WdfPdoAddEjectionRelationsPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff548770)
-   [**WdfPdoClearEjectionRelationsDevices**](https://msdn.microsoft.com/library/windows/hardware/ff548771)
-   [**WdfPdoGetParent**](https://msdn.microsoft.com/library/windows/hardware/ff548774)
-   [**WdfPdoInitAddDeviceText**](https://msdn.microsoft.com/library/windows/hardware/ff548780)
-   [**WdfPdoInitAddHardwareID**](https://msdn.microsoft.com/library/windows/hardware/ff548784)
-   [**WdfPdoInitAllocate**](https://msdn.microsoft.com/library/windows/hardware/ff548786)
-   [**WdfPdoInitAllowForwardingRequestToParent**](https://msdn.microsoft.com/library/windows/hardware/ff548789)
-   [**WdfPdoInitAssignContainerID**](https://msdn.microsoft.com/library/windows/hardware/ff548792)
-   [**WdfPdoInitAssignDeviceID**](https://msdn.microsoft.com/library/windows/hardware/ff548797)
-   [**WdfPdoInitAssignInstanceID**](https://msdn.microsoft.com/library/windows/hardware/ff548799)
-   [**WdfPdoInitAssignRawDevice**](https://msdn.microsoft.com/library/windows/hardware/ff548802)
-   [**WdfPdoInitSetDefaultLocale**](https://msdn.microsoft.com/library/windows/hardware/ff548803)
-   [**WdfPdoInitSetEventCallbacks**](https://msdn.microsoft.com/library/windows/hardware/ff548805)
-   [**WdfPdoMarkMissing**](https://msdn.microsoft.com/library/windows/hardware/ff548809)
-   [**WdfPdoRemoveEjectionRelationsPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff548814)
-   [**WdfPdoRequestEject**](https://msdn.microsoft.com/library/windows/hardware/ff548817)
-   [**WdfPdoRetrieveAddressDescription**](https://msdn.microsoft.com/library/windows/hardware/ff548820)
-   [**WdfPdoRetrieveIdentificationDescription**](https://msdn.microsoft.com/library/windows/hardware/ff548824)
-   [**WdfPdoUpdateAddressDescription**](https://msdn.microsoft.com/library/windows/hardware/ff548826)

## Framework PDO Structures and Initialization Functions

-   [**WDF_PDO_EVENT_CALLBACKS**](https://msdn.microsoft.com/library/windows/hardware/ff552409)
-   [**WDF_PDO_EVENT_CALLBACKS_INIT**](https://msdn.microsoft.com/library/windows/hardware/ff552413)
