---
UID: NS:ntdddisk._SENDCMDINPARAMS
title: "_SENDCMDINPARAMS"
author: windows-driver-content
description: The SENDCMDINPARAMS structure contains the input parameters for the SMART_SEND_DRIVE_COMMAND request.
old-location: storage\sendcmdinparams.htm
old-project: storage
ms.assetid: 4c02da7e-2d93-4e0c-9666-acb380c6d39a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntdddisk/SENDCMDINPARAMS, ntdddisk/LPSENDCMDINPARAMS, PSENDCMDINPARAMS, LPSENDCMDINPARAMS, PSENDCMDINPARAMS structure pointer [Storage Devices], storage.sendcmdinparams, SENDCMDINPARAMS structure [Storage Devices], _SENDCMDINPARAMS, *PSENDCMDINPARAMS, LPSENDCMDINPARAMS structure pointer [Storage Devices], ntdddisk/PSENDCMDINPARAMS, SENDCMDINPARAMS, *LPSENDCMDINPARAMS, structs-IDE_b80faf9d-dfcf-4eac-b0be-fb18964c4c2b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	ntdddisk.h
apiname:
-	SENDCMDINPARAMS
product: Windows
targetos: Windows
req.typenames: SENDCMDINPARAMS, *PSENDCMDINPARAMS, *LPSENDCMDINPARAMS
---

# _SENDCMDINPARAMS structure


## -description


The SENDCMDINPARAMS structure contains the input parameters for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a> request.


## -syntax


````
typedef struct _SENDCMDINPARAMS {
  ULONG   cBufferSize;
  IDEREGS irDriveRegs;
  UCHAR   bDriveNumber;
  UCHAR   bReserved[3];
  ULONG   dwReserved[4];
  UCHAR   bBuffer[1];
} SENDCMDINPARAMS, *PSENDCMDINPARAMS, *LPSENDCMDINPARAMS;
````


## -struct-fields




### -field cBufferSize

Contains the buffer size, in bytes.


### -field irDriveRegs

Contains a <a href="..\ntdddisk\ns-ntdddisk-_ideregs.md">IDEREGS</a> structure used to report the contents of the IDE controller registers.


### -field bDriveNumber

The <b>bDriveNumber</b> member is opaque. Do not use it. The operating system ignores this member, because the physical drive that receives the request depends on the handle that the caller uses when making the request.


### -field bReserved

Reserved. 


### -field dwReserved

Reserved. 


### -field bBuffer

Pointer to the input buffer. 


## -remarks


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a> is used to send a Self-Monitoring Analysis and Reporting Technology (SMART) commands to a device. 

The SENDCMDINPARAMS structure is also used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566204">SMART_RCV_DRIVE_DATA</a> request. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566204">SMART_RCV_DRIVE_DATA</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a>

<a href="..\ntdddisk\ns-ntdddisk-_sendcmdoutparams.md">SENDCMDOUTPARAMS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SENDCMDINPARAMS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

