---
UID: NS:ntdddisk._DRIVERSTATUS
title: _DRIVERSTATUS (ntdddisk.h)
description: The DRIVERSTATUS structure is used in conjunction with the SENDCMDOUTPARAMS structure and the SMART_SEND_DRIVE_COMMAND request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.
old-location: storage\driverstatus.htm
tech.root: storage
ms.assetid: de97322f-a756-49a8-a6e6-dab42f278388
ms.date: 03/29/2018
ms.keywords: "*LPDRIVERSTATUS, *PDRIVERSTATUS, DRIVERSTATUS, DRIVERSTATUS structure [Storage Devices], LPDRIVERSTATUS, LPDRIVERSTATUS structure pointer [Storage Devices], PDRIVERSTATUS, PDRIVERSTATUS structure pointer [Storage Devices], _DRIVERSTATUS, ntdddisk/DRIVERSTATUS, ntdddisk/LPDRIVERSTATUS, ntdddisk/PDRIVERSTATUS, storage.driverstatus, structs-IDE_e49310ff-1d3c-44d5-a997-08b8f500ed13.xml"
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
-	DRIVERSTATUS
product:
- Windows
targetos: Windows
req.typenames: DRIVERSTATUS, *PDRIVERSTATUS, *LPDRIVERSTATUS
---

# _DRIVERSTATUS structure


## -description


The DRIVERSTATUS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565405">SENDCMDOUTPARAMS</a> structure and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a> request to retrieve data returned by a Self-Monitoring Analysis and Reporting Technology (SMART) command.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565405">SENDCMDOUTPARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566206">SMART_SEND_DRIVE_COMMAND</a>
 

 

