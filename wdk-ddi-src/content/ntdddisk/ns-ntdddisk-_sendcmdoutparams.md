---
UID: NS:ntdddisk._SENDCMDOUTPARAMS
title: "_SENDCMDOUTPARAMS"
author: windows-driver-content
description: The SENDCMDOUTPARAMS structure is used in conjunction with the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.
old-location: storage\sendcmdoutparams.htm
old-project: storage
ms.assetid: e9fb6d5c-258c-46eb-ba3a-3f10008fdf68
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPSENDCMDOUTPARAMS, *PSENDCMDOUTPARAMS, LPSENDCMDOUTPARAMS, LPSENDCMDOUTPARAMS structure pointer [Storage Devices], PSENDCMDOUTPARAMS, PSENDCMDOUTPARAMS structure pointer [Storage Devices], SENDCMDOUTPARAMS, SENDCMDOUTPARAMS structure [Storage Devices], _SENDCMDOUTPARAMS, ntdddisk/LPSENDCMDOUTPARAMS, ntdddisk/PSENDCMDOUTPARAMS, ntdddisk/SENDCMDOUTPARAMS, storage.sendcmdoutparams, structs-IDE_d1a70016-0e77-465a-9368-665975369bdc.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntdddisk.h
api_name:
-	SENDCMDOUTPARAMS
product:
- Windows
targetos: Windows
req.typenames: SENDCMDOUTPARAMS, *PSENDCMDOUTPARAMS, *LPSENDCMDOUTPARAMS
---

# _SENDCMDOUTPARAMS structure


## -description


The SENDCMDOUTPARAMS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a> request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command. 


## -struct-fields




### -field cBufferSize

Contains the size in bytes of the buffer pointed to by <b>bBuffer</b>. 


### -field DriverStatus

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552658">DRIVERSTATUS</a> structure that indicates the driver status. 


### -field bBuffer

Pointer to a buffer in which to store the data read from the drive.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a> is used to send SMART commands to a device. 

The SENDCMDOUTPARAMS structure is also used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566204">SMART_RCV_DRIVE_DATA</a> request. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565401">SENDCMDINPARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566204">SMART_RCV_DRIVE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a>
 

 

