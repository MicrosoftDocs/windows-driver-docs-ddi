---
UID: NA:wdffdo
ms.assetid: 3b4b9cb8-8139-3f49-a13d-762e25571789
ms.author: windowsdriverdev
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: wdf
---

# Wdffdo.h header


## -description


This header is used by wdf. For more information, see:

- [Windows Driver Framework](../_wdf/index.md)
- [wdfdevice.h header](../wdfdevice/index.md)
- [wdfpdo.h header](../wdfpdo/index.md)

This topic orders the Windows Driver Frameworks (WDF) functional device object (FDO) reference by category.

The categories on this page are:

-   [Framework FDO Event Callbacks](#framework-fdo-event-callbacks)
-   [Framework FDO Initialization Methods](#framework-fdo-initialization-methods)
-   [Framework FDO Methods](#framework-fdo-methods)
-   [Framework FDO Structures and Initialization Functions](#framework-fdo-structures-and-initialization-functions)

## Framework FDO Event Callbacks

-   [*EVT_WDF_DEVICE_FILTER_RESOURCE_REQUIREMENTS*](https://msdn.microsoft.com/library/windows/hardware/ff540870)
-   [*EvtDeviceRemoveAddedResources*](https://msdn.microsoft.com/library/windows/hardware/ff540892)

## Framework FDO Initialization Methods

-   [**WdfFdoInitAllocAndQueryProperty**](https://msdn.microsoft.com/library/windows/hardware/ff547239)
-   [**WdfFdoInitAllocAndQueryPropertyEx**](https://msdn.microsoft.com/library/windows/hardware/dn265612)
-   [**WdfFdoInitOpenRegistryKey**](https://msdn.microsoft.com/library/windows/hardware/ff547249)
-   [**WdfFdoInitQueryProperty**](https://msdn.microsoft.com/library/windows/hardware/ff547254)
-   [**WdfFdoInitQueryPropertyEx**](https://msdn.microsoft.com/library/windows/hardware/dn265613)
-   [**WdfFdoInitSetDefaultChildListConfig**](https://msdn.microsoft.com/library/windows/hardware/ff547258)
-   [**WdfFdoInitSetEventCallbacks**](https://msdn.microsoft.com/library/windows/hardware/ff547268)
-   [**WdfFdoInitSetFilter**](https://msdn.microsoft.com/library/windows/hardware/ff547273)
-   [**WdfFdoInitWdmGetPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff547281)

## Framework FDO Methods

-   [**WdfFdoAddStaticChild**](https://msdn.microsoft.com/library/windows/hardware/ff547225)
-   [**WdfFdoGetDefaultChildList**](https://msdn.microsoft.com/library/windows/hardware/ff547235)
-   [**WdfFdoInitAllocAndQueryProperty**](https://msdn.microsoft.com/library/windows/hardware/ff547239)
-   [**WdfFdoInitOpenRegistryKey**](https://msdn.microsoft.com/library/windows/hardware/ff547249)
-   [**WdfFdoInitQueryProperty**](https://msdn.microsoft.com/library/windows/hardware/ff547254)
-   [**WdfFdoInitSetDefaultChildListConfig**](https://msdn.microsoft.com/library/windows/hardware/ff547258)
-   [**WdfFdoInitSetEventCallbacks**](https://msdn.microsoft.com/library/windows/hardware/ff547268)
-   [**WdfFdoInitSetFilter**](https://msdn.microsoft.com/library/windows/hardware/ff547273)
-   [**WdfFdoInitWdmGetPhysicalDevice**](https://msdn.microsoft.com/library/windows/hardware/ff547281)
-   [**WdfFdoLockStaticChildListForIteration**](https://msdn.microsoft.com/library/windows/hardware/ff547282)
-   [**WdfFdoQueryForInterface**](https://msdn.microsoft.com/library/windows/hardware/ff547289)
-   [**WdfFdoRetrieveNextStaticChild**](https://msdn.microsoft.com/library/windows/hardware/ff547293)
-   [**WdfFdoUnlockStaticChildListFromIteration**](https://msdn.microsoft.com/library/windows/hardware/ff547297)

## Framework FDO Structures and Initialization Functions

-   [**WDF_FDO_EVENT_CALLBACKS**](https://msdn.microsoft.com/library/windows/hardware/ff551311)
-   [**WDF_FDO_EVENT_CALLBACKS_INIT**](https://msdn.microsoft.com/library/windows/hardware/ff551313)