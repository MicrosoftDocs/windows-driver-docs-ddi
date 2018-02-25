---
UID: NE:wdfdevice._WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
title: "_WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE"
author: windows-driver-content
description: The WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration specifies when the framework calls a driver's EvtDeviceReleaseHardware callback function.
old-location: wdf\wdf_release_hardware_order_on_failure.htm
old-project: wdf
ms.assetid: 534B1E39-6B11-4954-8792-41A25FCA31B2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , *, *PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, ,, A, D, E, F, H, I, L, N, O, P, PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration pointer, R, S, U, W, WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration, WdfReleaseHardwareOrderOnFailureAfterDescendants, WdfReleaseHardwareOrderOnFailureEarly, WdfReleaseHardwareOrderOnFailureInvalid, _, _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, kmdf.wdf_release_hardware_order_on_failure, wdf.wdf_release_hardware_order_on_failure, wdfdevice/PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, wdfdevice/WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, wdfdevice/WdfReleaseHardwareOrderOnFailureAfterDescendants, wdfdevice/WdfReleaseHardwareOrderOnFailureEarly, wdfdevice/WdfReleaseHardwareOrderOnFailureInvalid"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
product: Windows
targetos: Windows
req.typenames: WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, *PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
req.product: Windows 10 or later.
---

# _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]


   The <b>WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</b> enumeration specifies when the framework calls a driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function.


## -syntax


````
typedef enum _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE { 
  WdfReleaseHardwareOrderOnFailureInvalid           = 0,
  WdfReleaseHardwareOrderOnFailureEarly             = 1,
  WdfReleaseHardwareOrderOnFailureAfterDescendants  = 2
} WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, *PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE;
````


## -enum-fields




### -field WdfReleaseHardwareOrderOnFailureInvalid

Reserved for system use.


### -field WdfReleaseHardwareOrderOnFailureEarly

Except under certain error conditions, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates. For more information, see Remarks.


### -field WdfReleaseHardwareOrderOnFailureAfterDescendants

The framework always calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates.


## -remarks



The <b>WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</b> enumeration is used as input to  <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetreleasehardwareorderonfailure.md">WdfDeviceInitSetReleaseHardwareOrderOnFailure</a>.

If a driver specifies <b>WdfReleaseHardwareOrderOnFailureEarly</b>, then in normal device removal, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates. However, in the event of a device power-up or power-down failure, the framework might call the  driver's <i>EvtDeviceReleaseHardware</i> before it has called the <i>EvtDeviceReleaseHardware</i> functions for all child devices.

If a driver specifies <b>WdfReleaseHardwareOrderOnFailureAfterDescendants</b>, then the framework waits to  call the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> until it has called the <i>EvtDeviceReleaseHardware</i> functions of the child devices.




## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetreleasehardwareorderonfailure.md">WdfDeviceInitSetReleaseHardwareOrderOnFailure</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

