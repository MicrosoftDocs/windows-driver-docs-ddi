---
UID: NI:sffdisk.IOCTL_SFFDISK_QUERY_DEVICE_PROTOCOL
title: IOCTL_SFFDISK_QUERY_DEVICE_PROTOCOL
author: windows-driver-content
description: User-mode applications use this IOCTL to retrieve a protocol value that identifies the card as either an SD card or an MMC card.
old-location: sd\ioctl_sffdisk_query_device_protocol.htm
old-project: SD
ms.assetid: 47eeb4a9-dece-4500-bbe7-891f64437eef
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: SFFDISK_DPCMD, SFFDISK_DPCMD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: sffdisk.h
req.include-header: Sffdisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SFFDISK_QUERY_DEVICE_PROTOCOL
req.alt-loc: sffdisk.h
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
req.typenames: SFFDISK_DPCMD
req.product: Windows 10 or later.
---

# IOCTL_SFFDISK_QUERY_DEVICE_PROTOCOL IOCTL



## -description
User-mode applications use this IOCTL to retrieve a protocol value that identifies the card as either an SD card or an MMC card. For a description of this command, see the <i>Secure Digital I/O (SDIO)</i> specification.

To perform this operation, call the <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> function (described in the Microsoft Windows SDK documentation) using the following parameters.



## -syntax

````
bRet = DeviceIoControl (
    (HANDLE)  hDevice, 
    (DWORD)  dwIoControlCode, 
    (PUCHAR)  lpInBuffer,
    (DWORD)  nInBufferSize, 
    (PUCHAR)  lpOutBuffer,
    (DWORD)  nOutBufferSize, 
    (LPDWORD)  lpBytesReturned,
    (LPOVERLAPPED)  lpOverlapped 
  );
````


## -ioctlparameters

### -input-buffer
TBD


### -input-buffer-length
TBD


### -output-buffer
TBD


### -output-buffer-length
TBD

TBD

TBD


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the operation succeeds, <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> returns a nonzero value.

If the operation fails, <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> returns zero. To get extended error information, call <b>GetLastError</b>.


## -remarks
