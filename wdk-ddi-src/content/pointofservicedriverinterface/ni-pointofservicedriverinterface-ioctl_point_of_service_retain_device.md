---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
title: IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
author: windows-driver-content
description: This I/O control function is used to keep a claim on a device when a client is notified that its claim on the device is being contested by another client.
old-location: pos\ioctl_point_of_service_retain_device.htm
old-project: pos
ms.assetid: c221862f-99db-4815-812f-8b22b46fff4a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE, IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE, pos.ioctl_point_of_service_retain_device
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pointofservicedriverinterface.h
api_name:
-	IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE
product:
- Windows
targetos: Windows
req.typenames: PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE IOCTL


## -description


This I/O control function is used to keep a claim on a device when a client is notified that its claim on the device is being contested by another client. 


## -ioctlparameters




### -input-buffer

Not used with this operation; set to <b>NULL</b>.


### -input-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero)


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values: 




#### -STATUS_ACCESS_DENIED

The device is currently claimed by another client.


#### -STATUS_DEVICE_NOT_READY

The POS library has not successfully initialized.


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>


This IOCTL only works if the client has previously called <a href="https://msdn.microsoft.com/library/windows/hardware/dn772093">IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE</a>.

When handling this IOCTL, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/mt593134">PosCxRetainDevice</a>. The driver writer does not need to handle claim contention because the PosCx library determines who gets the claim.



