---
UID: NS:ntddk._WHEA_GENERIC_ERROR_BLOCKSTATUS
title: "_WHEA_GENERIC_ERROR_BLOCKSTATUS"
author: windows-driver-content
description: The WHEA_GENERIC_ERROR_BLOCKSTATUS union indicates what kind of error data is reported in a generic error status block.
old-location: whea\whea_generic_error_blockstatus.htm
old-project: whea
ms.assetid: 38c8422d-7307-4acd-81f0-931d2e128cb9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_GENERIC_ERROR_BLOCKSTATUS, PWHEA_GENERIC_ERROR_BLOCKSTATUS, PWHEA_GENERIC_ERROR_BLOCKSTATUS union pointer [WHEA Drivers and Applications], WHEA_GENERIC_ERROR_BLOCKSTATUS, WHEA_GENERIC_ERROR_BLOCKSTATUS union [WHEA Drivers and Applications], _WHEA_GENERIC_ERROR_BLOCKSTATUS, ntddk/PWHEA_GENERIC_ERROR_BLOCKSTATUS, ntddk/WHEA_GENERIC_ERROR_BLOCKSTATUS, whea.whea_generic_error_blockstatus, whearef_2137a60a-daff-4a33-a516-c9ae87e2f11c.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_GENERIC_ERROR_BLOCKSTATUS
product:
- Windows
targetos: Windows
req.typenames: WHEA_GENERIC_ERROR_BLOCKSTATUS, *PWHEA_GENERIC_ERROR_BLOCKSTATUS
---

# _WHEA_GENERIC_ERROR_BLOCKSTATUS structure


## -description


The WHEA_GENERIC_ERROR_BLOCKSTATUS union indicates what kind of error data is reported in a generic error status block.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field AsULONG

A ULONG representation of the contents of the WHEA_GENERIC_ERROR_BLOCKSTATUS union.


#### - CorrectableError

The generic error status block is reporting correctable error data.


#### - ErrorDataEntryCount

The number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560529">WHEA_GENERIC_ERROR_DATA_ENTRY</a> structures that are contained in the generic error status block.


#### - MultipleCorrectableErrors

The generic error status block is reporting multiple correctable errors.


#### - MultipleUncorrectableErrors

The generic error status block is reporting multiple uncorrectable errors.


#### - Reserved

Reserved for system use.


#### - UncorrectableError

The generic error status block is reporting uncorrectable error data.


## -remarks



A WHEA_GENERIC_ERROR_BLOCKSTATUS union is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560524">WHEA_GENERIC_ERROR</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560524">WHEA_GENERIC_ERROR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560529">WHEA_GENERIC_ERROR_DATA_ENTRY</a>
 

 

