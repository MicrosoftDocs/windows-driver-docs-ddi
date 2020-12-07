---
UID: NF:portcls.PcRegisterIoTimeout
title: PcRegisterIoTimeout function (portcls.h)
description: The PcRegisterIoTimeout function registers a driver-supplied I/O-timer callback routine for a specified device object.
old-location: audio\pcregisteriotimeout.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PcRegisterIoTimeout function"]
ms.keywords: PcRegisterIoTimeout, PcRegisterIoTimeout function [Audio Devices], audio.pcregisteriotimeout, audpc-routines_1a63a1fa-c80a-4fe4-87d6-95543e6e2f1d.xml, portcls/PcRegisterIoTimeout
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PcRegisterIoTimeout
 - portcls/PcRegisterIoTimeout
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcRegisterIoTimeout
---

# PcRegisterIoTimeout function


## -description

The <b>PcRegisterIoTimeout</b> function registers a driver-supplied I/O-timer callback routine for a specified device object.

Once registered, the port-class driver calls the timer callback approximately once per second for as long as the device remains active.
<div class="alert"><b>Note</b>  This function is deprecated for Windows 8 and later versions of Windows.  For Windows on Arm systems, this function is commented out in the PortCls class driver and is inaccessible.</div><div> </div>

## -parameters

### -param pDeviceObject 

[in]
Pointer to a device object representing a device on which I/O operations can time out. This parameter must point to a system structure of type <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>. When calling the I/O-timer callback routine, the port class driver passes this pointer as the first of two call parameters. For more information, see the following Remarks section.

### -param pTimerRoutine 

[in]
Pointer to the driver-supplied I/O-timer callback routine. For more information, see the following Remarks section.

### -param pContext 

[in]
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

The driver can disable the timer by calling <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcunregisteriotimeout">PcUnregisterIoTimeout</a>.

Only one timer callback with a particular combination of device object, I/O-timer callback routine, and context can be registered at a time.

The meaning of the <i>pContext</i> parameter is determined by the adapter driver, but the driver typically sets this parameter to point to an object such as the miniport, miniport-stream, or adapter object.

The <i>pTimerRoutine </i>parameter is of type PIO_TIMER_ROUTINE, which is defined in ntddk.h to be


```
  VOID
    (*PIO_TIMER_ROUTINE)(
      IN PDEVICE_OBJECT  DeviceObject,
      IN PVOID  Context
      );
```

The <i>DeviceObject</i> and <i>Context</i> parameters are the same values that the adapter driver previously passed as call parameters to <b>PcRegisterIoTimeout</b>. The port-class driver calls the timer routine at IRQL DISPATCH_LEVEL. The timer routine must not contain pageable code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcunregisteriotimeout">PcUnregisterIoTimeout</a>
