---
UID: NI:sffdisk.IOCTL_SFFDISK_DEVICE_COMMAND
title: IOCTL_SFFDISK_DEVICE_COMMAND
author: windows-driver-content
description: User-mode applications use this IOCTL to send Secure Digital (SD) card commands to an SD card.
old-location: sd\ioctl_sffdisk_device_command.htm
old-project: SD
ms.assetid: ccf9e0a2-b891-474c-ac95-7b18112857c0
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
req.alt-api: IOCTL_SFFDISK_DEVICE_COMMAND
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

# IOCTL_SFFDISK_DEVICE_COMMAND IOCTL



## -description
User-mode applications use this IOCTL to send Secure Digital (SD) card commands to an SD card. For a description of these commands, see the <i>SD Memory Card Part 1 Physical Layer Specification</i>, and the <i>SD Memory Card Part 3 Security</i> specification.

The caller must fill in an <a href="https://msdn.microsoft.com/68205c17-5ff6-45a3-83c7-e106b314f9a5">SFFDISK_DEVICE_COMMAND_DATA</a> structure and pass it as a parameter to the call. 

To perform this operation, call the <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> function (described in the Microsoft Windows SDK documentation) with the following parameters.



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

<text></text>

### -input-buffer-length

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the operation succeeds, <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> returns a nonzero value.

If the operation fails, <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> returns zero. To get extended error information, call <b>GetLastError</b>.


## -remarks
