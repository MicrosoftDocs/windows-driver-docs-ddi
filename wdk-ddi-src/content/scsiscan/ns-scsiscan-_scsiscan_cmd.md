---
UID: NS:scsiscan._SCSISCAN_CMD
title: "_SCSISCAN_CMD"
author: windows-driver-content
description: The SCSISCAN_CMD structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_SCSISCAN_CMD.
old-location: image\scsiscan_cmd.htm
old-project: image
ms.assetid: 412c35b2-eb08-43a3-b776-053645806f5d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: SCSISCAN_CMD structure [Imaging Devices], PSCSISCAN_CMD structure pointer [Imaging Devices], *PSCSISCAN_CMD, scsiscan/SCSISCAN_CMD, SCSISCAN_CMD, _SCSISCAN_CMD, image.scsiscan_cmd, scsiscan/PSCSISCAN_CMD, stifnc_2a67c5d9-7866-4dc5-8ce4-6bc832cbf7de.xml, PSCSISCAN_CMD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsiscan.h
req.include-header: Scsiscan.h, Srb.h, Scsi.h
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
-	scsiscan.h
apiname:
-	SCSISCAN_CMD
product: Windows
targetos: Windows
req.typenames: "*PSCSISCAN_CMD, SCSISCAN_CMD"
req.product: Windows 10 or later.
---

# _SCSISCAN_CMD structure


## -description


The SCSISCAN_CMD structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\scsiscan\ni-scsiscan-ioctl_scsiscan_cmd.md">IOCTL_SCSISCAN_CMD</a>.


## -syntax


````
typedef struct _SCSISCAN_CMD {
  ULONG  Reserved1;
  ULONG  Size;
  ULONG  SrbFlags;
  UCHAR  CdbLength;
  UCHAR  SenseLength;
  UCHAR  Reserved2;
  UCHAR  Reserved3;
  ULONG  TransferLength;
  UCHAR  Cdb[16];
  PUCHAR pSrbStatus;
  PUCHAR pSenseBuffer;
} SCSISCAN_CMD, *PSCSISCAN_CMD;
````


## -struct-fields




#### - Reserved1

Reserved. Do not use.


#### - Size

Caller-supplied size, in bytes, of the SCSISCAN_CMD structure.


#### - SrbFlags

Caller-supplied SRB_FLAGS-prefixed bit flag specifying the requested operation. Flags are defined in <i>srb.h</i>.


#### - CdbLength

Length, in bytes, of the <a href="https://msdn.microsoft.com/ac439eb8-b491-4215-877d-5ee177fbdb39">CDB</a> contained in the <b>Cdb</b> member.


#### - SenseLength

Length, in bytes, of the sense buffer the <b>pSenseBuffer</b> member points to.


#### - Reserved2

Reserved. Do not use.


#### - Reserved3

Reserved. Do not use.


#### - TransferLength

Length, in bytes, of the buffer to be transferred. This should match the value specified for the <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> function's <i>nOutBufferSize</i> parameter.


#### - Cdb

Caller-supplied <a href="https://msdn.microsoft.com/ac439eb8-b491-4215-877d-5ee177fbdb39">CDB</a> data. (The CDB structure is declared in <i>scsi.h</i>.)


#### - pSrbStatus

Caller-supplied pointer that will receive one of the SRB_STATUS-prefixed status values defined in <i>srb.h</i>.


#### - pSenseBuffer

Caller-supplied pointer to a request-sense buffer, to be filled in by the kernel-mode driver.

