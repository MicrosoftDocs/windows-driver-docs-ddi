---
UID: NF:mcd.ChangerClassDeviceControl
title: ChangerClassDeviceControl function
author: windows-driver-content
description: The ChangerClassDeviceControl routine is called by a changer minidriver to allow the class driver perform device-independent aspects of a device control operation.
old-location: storage\changerclassdevicecontrol.htm
old-project: storage
ms.assetid: 9107fa7b-b061-4505-aef7-be04587a4199
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ChangerClassDeviceControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ChangerClassDeviceControl
req.alt-loc: mcd.h
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
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerClassDeviceControl function



## -description
The <b>ChangerClassDeviceControl</b> routine is called by a changer minidriver to allow the class driver perform device-independent aspects of a device control operation. 



## -syntax

````
NTSTATUS ChangerClassDeviceControl(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the device object of the device. 


### -param Irp [in]

Pointer to the I/O request packet (IRP) that initiated the device control operation. 


## -returns
If the operation succeeds, the <b>ChangerClassDeviceControl</b> routine returns STATUS_SUCCESS. Otherwise the routine returns one of the following status values.
<dl>
<dt><b>STATUS_NO_SUCH_DEVICE</b></dt>
</dl>The device object does not have a properly initialized device extension.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The length of the output buffer indicated in the IRP is too small to hold the return data.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The length of the input buffer indicated in the IRP is too small to hold the input data that is necessary to complete the operation.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The length of the input buffer is zero.

 


## -remarks
