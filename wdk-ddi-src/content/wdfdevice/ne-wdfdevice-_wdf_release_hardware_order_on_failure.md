---
UID: NE:wdfdevice._WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
title: "_WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE"
author: windows-driver-content
description: The WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration specifies when the framework calls a driver's EvtDeviceReleaseHardware callback function.
old-location: wdf\wdf_release_hardware_order_on_failure.htm
old-project: wdf
ms.assetid: 534B1E39-6B11-4954-8792-41A25FCA31B2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration pointer, WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration, WdfReleaseHardwareOrderOnFailureAfterDescendants, WdfReleaseHardwareOrderOnFailureEarly, WdfReleaseHardwareOrderOnFailureInvalid, _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, kmdf.wdf_release_hardware_order_on_failure, wdf.wdf_release_hardware_order_on_failure, wdfdevice/PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, wdfdevice/WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, wdfdevice/WdfReleaseHardwareOrderOnFailureAfterDescendants, wdfdevice/WdfReleaseHardwareOrderOnFailureEarly, wdfdevice/WdfReleaseHardwareOrderOnFailureInvalid"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
product:
- Windows
targetos: Windows
req.typenames: WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE, *PWDF_RELEASE_HARDWARE_ORDER_ON_FAILURE
---

# _WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]


   The <b>WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</b> enumeration specifies when the framework calls a driver's <a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a> callback function.


## -enum-fields




### -field WdfReleaseHardwareOrderOnFailureInvalid

Reserved for system use.


### -field WdfReleaseHardwareOrderOnFailureEarly

Except under certain error conditions, the framework calls the driver's <a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a> callback function after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates. For more information, see Remarks.


### -field WdfReleaseHardwareOrderOnFailureAfterDescendants

The framework always calls the driver's <a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a> callback function after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates.


## -remarks



The <b>WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</b> enumeration is used as input to  <a href="https://msdn.microsoft.com/library/windows/hardware/hh706196">WdfDeviceInitSetReleaseHardwareOrderOnFailure</a>.

If a driver specifies <b>WdfReleaseHardwareOrderOnFailureEarly</b>, then in normal device removal, the framework calls the driver's <a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a> after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates. However, in the event of a device power-up or power-down failure, the framework might call the  driver's <i>EvtDeviceReleaseHardware</i> before it has called the <i>EvtDeviceReleaseHardware</i> functions for all child devices.

If a driver specifies <b>WdfReleaseHardwareOrderOnFailureAfterDescendants</b>, then the framework waits to  call the driver's <a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a> until it has called the <i>EvtDeviceReleaseHardware</i> functions of the child devices.




## -see-also




<a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh706196">WdfDeviceInitSetReleaseHardwareOrderOnFailure</a>
 

 

