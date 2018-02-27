---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE
title: IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE
author: windows-driver-content
description: This IO control function authenticates the magnetic stripe reader (MSR).
old-location: pos\ioctl_point_of_service_msr_authenticate_device.htm
old-project: pos
ms.assetid: fc6b719d-3e05-4ff5-9d81-1e9326ff4ad4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE, IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE, pos.ioctl_point_of_service_msr_authenticate_device
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pointofservicedriverinterface.h
apiname:
-	IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE
product: Windows
targetos: Windows
req.typenames: PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


This IO control function authenticates the magnetic stripe reader (MSR).


## -ioctlparameters




### -input-buffer

Pointer to the input buffer, a <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_authenticate_device.md">MSR_AUTHENTICATE_DEVICE</a> variable.


### -input-buffer-length

Size of the input buffer, in bytes. Set to sizeof(<b>MSR_AUTHENTICATE_DEVICE</b>).


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following are common error values:




#### -STATUS_ACCESS_DENIED

The device is currently claimed by another client.


#### -STATUS_NOT_SUPPORTED

The device does not support authentication.


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>




