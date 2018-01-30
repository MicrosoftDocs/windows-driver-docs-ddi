---
UID: NF:portcls.PcRegisterIoTimeout
title: PcRegisterIoTimeout function
author: windows-driver-content
description: The PcRegisterIoTimeout function registers a driver-supplied I/O-timer callback routine for a specified device object.
old-location: audio\pcregisteriotimeout.htm
old-project: audio
ms.assetid: 9cd7c366-1745-45b0-b9e9-87a259110621
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.pcregisteriotimeout, audpc-routines_1a63a1fa-c80a-4fe4-87d6-95543e6e2f1d.xml, portcls/PcRegisterIoTimeout, PcRegisterIoTimeout function [Audio Devices], PcRegisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcRegisterIoTimeout function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcRegisterIoTimeout
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcRegisterIoTimeout function


## -description


The <b>PcRegisterIoTimeout</b> function registers a driver-supplied I/O-timer callback routine for a specified device object.

Once registered, the port-class driver calls the timer callback approximately once per second for as long as the device remains active.
<div class="alert"><b>Note</b>  This function is deprecated for Windows 8 and later versions of Windows.  For Windows on Arm systems, this function is commented out in the PortCls class driver and is inaccessible.</div><div> </div>

## -syntax


````
NTSTATUS PcRegisterIoTimeout(
  _In_ PDEVICE_OBJECT    pDeviceObject,
  _In_ PIO_TIMER_ROUTINE pTimerRoutine,
  _In_ PVOID             pContext
);
````


## -parameters




### -param pDeviceObject [in]

Pointer to a device object representing a device on which I/O operations can time out. This parameter must point to a system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>. When calling the I/O-timer callback routine, the port class driver passes this pointer as the first of two call parameters. For more information, see the following Remarks section.


### -param pTimerRoutine [in]

Pointer to the driver-supplied I/O-timer callback routine. For more information, see the following Remarks section.


### -param pContext [in]

Pointer to the driver-specific context. When calling the I/O-timer callback routine, the port class driver passes this pointer as the second of two call parameters. For more information, see the following Remarks section.


## -returns


<b>PcRegisterIoTimeout</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code. The following table shows some of the possible error codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Possibly indicates that a memory allocation failed inside the port-class driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Possibly indicates that a timer callback with the same combination of device object, I/O-timer callback routine, and context is already registered.

</td>
</tr>
</table> 



## -remarks


An adapter driver calls the <b>PcRegisterIoTimeout</b> function to enable a low-resolution watchdog timer. Drivers use this function primarily to monitor devices that have no means to generate an event themselves if they fail to complete a previously initiated I/O operation within some maximum time interval.

After the driver calls <b>PcRegisterIoTimeout</b>, the port-class driver calls the driver's I/O-timer callback routine approximately once per second for as long as the device remains active. (The device is activated by an IRP_MN_START_DEVICE request and deactivated by an IRP_MN_STOP_DEVICE request.)

The driver can disable the timer by calling <a href="..\portcls\nf-portcls-pcunregisteriotimeout.md">PcUnregisterIoTimeout</a>.

Only one timer callback with a particular combination of device object, I/O-timer callback routine, and context can be registered at a time.

The meaning of the <i>pContext</i> parameter is determined by the adapter driver, but the driver typically sets this parameter to point to an object such as the miniport, miniport-stream, or adapter object.

The <i>pTimerRoutine </i>parameter is of type PIO_TIMER_ROUTINE, which is defined in ntddk.h to be
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  VOID
    (*PIO_TIMER_ROUTINE)(
      IN PDEVICE_OBJECT  DeviceObject,
      IN PVOID  Context
      );</pre>
</td>
</tr>
</table></span></div>The <i>DeviceObject</i> and <i>Context</i> parameters are the same values that the adapter driver previously passed as call parameters to <b>PcRegisterIoTimeout</b>. The port-class driver calls the timer routine at IRQL DISPATCH_LEVEL. The timer routine must not contain pageable code.



## -see-also

<a href="..\portcls\nf-portcls-pcunregisteriotimeout.md">PcUnregisterIoTimeout</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRegisterIoTimeout function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

