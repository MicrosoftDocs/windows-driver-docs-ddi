---
UID: NI:ntddser.IOCTL_SERIAL_CONFIG_SIZE
title: IOCTL_SERIAL_CONFIG_SIZE
description: The IOCTL_SERIAL_CONFIG_SIZE request returns information about configuration size.
old-location: serports\ioctl_serial_config_size.htm
tech.root: serports
ms.assetid: 13229dcc-e698-4743-9ca2-303bef69304c
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_CONFIG_SIZE, IOCTL_SERIAL_CONFIG_SIZE control, IOCTL_SERIAL_CONFIG_SIZE control code [Serial Ports], ntddser/IOCTL_SERIAL_CONFIG_SIZE, serports.ioctl_serial_config_size, serref_c851a6c5-27c1-4690-bb2f-36bd458b6629.xml
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
-	IOCTL_SERIAL_CONFIG_SIZE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_CONFIG_SIZE IOCTL


## -description


The <b>IOCTL_SERIAL_CONFIG_SIZE</b> request returns information about configuration size.

Serial.sys always returns a configuration size of zero.

This request is obsolete and should not be used by new drivers for Microsoft Windows 2000 and later.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG buffer that Serial.sys uses to output configuration size information.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> is set to the size in bytes of a ULONG.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to the size in bytes of a ULONG.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.

