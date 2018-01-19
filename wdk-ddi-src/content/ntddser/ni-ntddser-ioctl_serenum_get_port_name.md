---
UID: NI:ntddser.IOCTL_SERENUM_GET_PORT_NAME
title: IOCTL_SERENUM_GET_PORT_NAME
author: windows-driver-content
description: The IOCTL_SERENUM_GET_PORT_NAME request returns the value of the PortName (or Identifier) entry value for the RS-232 port -- see Registry Settings for a Plug and Play Serial Device.
old-location: serports\ioctl_serenum_get_port_name.htm
old-project: serports
ms.assetid: c61bc594-91be-418f-9e40-ebe99e31304f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SdBusSubmitRequestAsync
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
req.alt-api: IOCTL_SERENUM_GET_PORT_NAME
req.alt-loc: ntddser.h
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
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERENUM_GET_PORT_NAME IOCTL



## -description

The IOCTL_SERENUM_GET_PORT_NAME request returns the value of the <b>PortName</b> (or <b>Identifier</b>) entry value for the RS-232 port -- see <a href="https://msdn.microsoft.com/57bd090a-20fe-41c6-b730-0479f6ae0982">Registry Settings for a Plug and Play Serial Device</a>.



The IOCTL_SERENUM_GET_PORT_NAME request returns the value of the <b>PortName</b> (or <b>Identifier</b>) entry value for the RS-232 port -- see <a href="https://msdn.microsoft.com/57bd090a-20fe-41c6-b730-0479f6ae0982">Registry Settings for a Plug and Play Serial Device</a>.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated buffer that Serenum uses to output the port name. The port name is a null-terminated Unicode string.


### -output-buffer-length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a client-allocated output buffer.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the <b>Information</b> member is set to the size in bytes of the null-terminated Unicode string that is returned in the client's output buffer.

The <b>Status</b> member is set to one of the following values:



The request completed successfully.

The output buffer is too small to hold the port name string.

An error occurred when opening the registry key for the device or reading the <b>PortName</b> (or <b>Identifier)</b> entry value.


## -remarks
