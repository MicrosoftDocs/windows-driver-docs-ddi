---
UID: NF:ursdevice.UrsReportHardwareEvent
title: UrsReportHardwareEvent function
author: windows-driver-content
description: Notifies the USB dual-role class extension about a new hardware event.
old-location: buses\ursreporthardwareevent.htm
tech.root: usbref
ms.assetid: 2BC80D99-5265-4D0C-A447-5CC2112F53F8
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UrsReportHardwareEvent, UrsReportHardwareEvent function [Buses], buses.ursreporthardwareevent, ursdevice/UrsReportHardwareEvent
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
req.irql: HIGH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Urscxstub.lib
-	Urscxstub.dll
api_name:
-	UrsReportHardwareEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# UrsReportHardwareEvent function


## -description


Notifies the USB dual-role class extension about a new hardware event.


## -parameters




### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.


### -param HardwareEvent [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt628022">URS_HARDWARE_EVENT</a>-type value that indicates the type of event that occurred.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



Before reporting any hardware events, the client driver for the dual-role controller must indicate to the class extension that the driver supports hardware events by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628018">UrsSetHardwareEventSupport</a>.

The client driver cannot pass <b>UrsHardwareEventNone</b> as the <i>HardwareEvent</i> parameter value. That value is reserved for internal use.

The client driver must call this method to report any hardware event, such as ID-pin interrupts. Typically, in the driver's implementation of the <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback, the driver reads the  ID-pin state and reports the event to the class extension by calling this method. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt628018">UrsSetHardwareEventSupport</a>
 

 

