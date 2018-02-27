---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE
title: IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE
author: windows-driver-content
description: The I/O control function claims the device for exclusive access.
old-location: pos\ioctl_point_of_service_claim_device.htm
old-project: pos
ms.assetid: e9dfa630-d3ac-4228-ae2a-02ff5a0fd558
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE, IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE, pos.ioctl_point_of_service_claim_device
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
-	IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE
product: Windows
targetos: Windows
req.typenames: PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The I/O control function claims the device for exclusive access.


## -ioctlparameters




### -input-buffer

Not used with this operation; set to <b>NULL</b>.


### -input-buffer-length

Not used with this operation; set to <b>0</b> (zero).


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

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values: 




#### -STATUS_ACCESS_DENIED

The claim could not be taken from the current claim owner.


#### -STATUS_DEVICE_NOT_READY

The POS library is not initialized.


#### -STATUS_PENDING

The claim request was queued.


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>


This IOCTL is handled by the PosCx library. The driver writer does not need to handle this IOCTL. Instead, call <a href="..\poscx\nf-poscx-poscxclaimdevice.md">PosCxClaimDevice</a>. If the POS device is already claimed by another client, then the POS device driver is responsible for notifying the claim owner using a <a href="https://msdn.microsoft.com/library/windows/hardware/dn790033">ReleaseDeviceRequested</a> event and waiting for the claim owner to retain its claim within 50 milliseconds. If the claim is not reaffirmed, then the current claim owner's claim is automatically revoked and granted to the challenging client. 



