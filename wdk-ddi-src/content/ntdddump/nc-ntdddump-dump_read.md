---
UID: NC:ntdddump.DUMP_READ
title: DUMP_READ (ntdddump.h)
description: The Dump_Read callback routine is called after the read from the dump port driver. The filter driver can access the dump data during the call to this routine.
old-location: storage\dump_read.htm
tech.root: storage
ms.assetid: 5F95D38C-8E11-49D4-82C4-718BD846A834
ms.date: 03/29/2018
ms.keywords: Dump_Read, Dump_Read routine [Storage Devices], PDUMP_READ, ntdddump/Dump_Read, storage.dump_read
ms.topic: callback
req.header: ntdddump.h
req.include-header: Ntdddump.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ntdddump.h
api_name:
- Dump_Read
product:
- Windows
targetos: Windows
req.typenames: 
---

# DUMP_READ callback function


## -description


The <i>Dump_Read</i> callback routine is called after the read from the dump port driver. The filter driver can access the dump data during the call to this routine.


## -parameters




### -param FilterExtension [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553862">FILTER_EXTENSION</a> structure.


### -param DiskByteOffset [in]

The value, in bytes, relative to the source partition for the crash dump or hibernation. Filter drivers should not modify this field.


### -param Mdl [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a> structure that describes the data buffer containing the dump data. Filter drivers should not modify this field.


## -returns



If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in <i>Ntstatus.h</i>.




## -remarks



Filter drivers can read the data that was read by the crashdump process. 

Filter drivers can modify the contents of the data buffer contained in <b>Mdl</b> to revert any changes made to the data when it was written to disk. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553709">Dump_Write</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553862">FILTER_EXTENSION</a>
 

 

