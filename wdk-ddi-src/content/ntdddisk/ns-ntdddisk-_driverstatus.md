---
UID: NS:ntdddisk._DRIVERSTATUS
title: "_DRIVERSTATUS"
author: windows-driver-content
description: The DRIVERSTATUS structure is used in conjunction with the SENDCMDOUTPARAMS structure and the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.
old-location: storage\driverstatus.htm
old-project: storage
ms.assetid: de97322f-a756-49a8-a6e6-dab42f278388
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DRIVERSTATUS, LPDRIVERSTATUS, PDRIVERSTATUS, *PDRIVERSTATUS, ntdddisk/PDRIVERSTATUS, storage.driverstatus, structs-IDE_e49310ff-1d3c-44d5-a997-08b8f500ed13.xml, ntdddisk/LPDRIVERSTATUS, DRIVERSTATUS structure [Storage Devices], ntdddisk/DRIVERSTATUS, LPDRIVERSTATUS structure pointer [Storage Devices], _DRIVERSTATUS, PDRIVERSTATUS structure pointer [Storage Devices], *LPDRIVERSTATUS
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
-	DRIVERSTATUS
product: Windows
targetos: Windows
req.typenames: DRIVERSTATUS, *PDRIVERSTATUS, *LPDRIVERSTATUS
---

# _DRIVERSTATUS structure


## -description


The DRIVERSTATUS structure is used in conjunction with the <a href="..\ntdddisk\ns-ntdddisk-_sendcmdoutparams.md">SENDCMDOUTPARAMS</a> structure and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a> request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.


## -syntax


````
typedef struct _DRIVERSTATUS {
  UCHAR bDriverError;
  UCHAR bIDEError;
  UCHAR bReserved[2];
  ULONG dwReserved[2];
} DRIVERSTATUS, *PDRIVERSTATUS, *LPDRIVERSTATUS;
````


## -struct-fields




### -field bDriverError

Error code from driver, or 0 if no error.


### -field bIDEError

Contents of IDE Error register.


### -field bReserved

Reserved. 


### -field dwReserved

Reserved. 


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_sendcmdoutparams.md">SENDCMDOUTPARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DRIVERSTATUS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

