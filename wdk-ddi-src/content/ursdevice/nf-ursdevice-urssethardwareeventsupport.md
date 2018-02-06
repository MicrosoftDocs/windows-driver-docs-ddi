---
UID: NF:ursdevice.UrsSetHardwareEventSupport
title: UrsSetHardwareEventSupport function
author: windows-driver-content
description: Indicates the client driver's support for reporting new hardware events.
old-location: buses\urssethardwareeventsupport.htm
old-project: usbref
ms.assetid: 905BA306-29A5-4AAB-BA30-6B459E0062F6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UrsSetHardwareEventSupport function [Buses], buses.urssethardwareeventsupport, ursdevice/UrsSetHardwareEventSupport, UrsSetHardwareEventSupport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Urscxstub.lib
-	Urscxstub.dll
apiname:
-	UrsSetHardwareEventSupport
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# UrsSetHardwareEventSupport function


## -description


Indicates the client driver's support for reporting new hardware events.


## -syntax


````
FORCEINLINE void UrsSetHardwareEventSupport(
  _In_ WDFDEVICE Device,
  _In_ BOOLEAN   HardwareEventReportingSupported
);
````


## -parameters




### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.


### -param HardwareEventReportingSupported [in]

A boolean value that indicates support for  reporting hardware events. 

TRUE indicates the client driver will report hardware events by calling <a href="..\ursdevice\nf-ursdevice-ursreporthardwareevent.md">UrsReportHardwareEvent</a>. 

FALSE indicates hardware event reporting is not handled by the client driver.


## -returns


This function does not return a value.



## -remarks


Before the client driver can report hardware events, the client driver for the dual-role controller must indicate to the class extension that the driver supports hardware events by calling this method. Typically, the driver calls <b>UrsSetHardwareEventSupport</b> in the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function. The driver must not call this method after <i>EvtDevicePrepareHardware</i> has returned. Otherwise, the method fails and a break is issued if <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> is enabled.

For certain controllers, the client driver might not support role detection before performing a role switch operation. In that case, the client driver must  set  <i>HardwareEventReportingSupported</i> to FALSE.  The operating system manages the role of the controller.

Otherwise, if the driver supports role detection, it must set  <i>HardwareEventReportingSupported</i> to TRUE.  This indicates to the class extension that the client driver will  handle hardware events, such as ID pin interrupts, and report to the class extension that the role needs to be changed. The driver can report events by calling <a href="..\ursdevice\nf-ursdevice-ursreporthardwareevent.md">UrsReportHardwareEvent</a>.



## -see-also

<a href="..\ursdevice\nf-ursdevice-ursreporthardwareevent.md">UrsReportHardwareEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UrsSetHardwareEventSupport function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

