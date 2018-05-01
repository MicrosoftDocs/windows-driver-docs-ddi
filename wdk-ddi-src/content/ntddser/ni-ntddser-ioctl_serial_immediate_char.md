---
UID: NI:ntddser.IOCTL_SERIAL_IMMEDIATE_CHAR
title: IOCTL_SERIAL_IMMEDIATE_CHAR
author: windows-driver-content
description: The IOCTL_SERIAL_IMMEDIATE_CHAR request causes a specified character to be transmitted as soon as possible.
old-location: serports\ioctl_serial_immediate_char.htm
old-project: serports
ms.assetid: 1bbae06c-1279-41da-82d8-ccbfe13cde9a
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_IMMEDIATE_CHAR, IOCTL_SERIAL_IMMEDIATE_CHAR control, IOCTL_SERIAL_IMMEDIATE_CHAR control code [Serial Ports], ntddser/IOCTL_SERIAL_IMMEDIATE_CHAR, serports.ioctl_serial_immediate_char, serref_f0a61fcc-3e61-4344-940b-ef9aeabec64b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
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
-	Ntddser.h
api_name:
-	IOCTL_SERIAL_IMMEDIATE_CHAR
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_IMMEDIATE_CHAR IOCTL


## -description


The <b>IOCTL_SERIAL_IMMEDIATE_CHAR</b> request causes a specified character to be transmitted as soon as possible. The immediate character request completes immediately after any other write that might be in progress. Only one immediate character request can be pending at a time.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to the UCHAR value to transmit immediately.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a UCHAR.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a UCHAR. Otherwise, <b>Information</b> is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that a previous immediate character request is pending.

