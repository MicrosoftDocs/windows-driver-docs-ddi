---
UID: NS:ntddtape._TAPE_ERASE
title: "_TAPE_ERASE"
author: windows-driver-content
description: The TAPE_ERASE structure is used in conjunction with the IOCTL_TAPE_ERASE request to erase the current tape partition.
old-location: storage\tape_erase.htm
tech.root: storage
ms.assetid: dc17efe6-9183-4908-8ca5-69c6ae38db6d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PTAPE_ERASE, PTAPE_ERASE, PTAPE_ERASE structure pointer [Storage Devices], TAPE_ERASE, TAPE_ERASE structure [Storage Devices], _TAPE_ERASE, ntddtape/PTAPE_ERASE, ntddtape/TAPE_ERASE, storage.tape_erase, structs-tape_56c14eca-358e-438f-9ff4-06345d2b2434.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddtape.h, Minitape.h
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
-	ntddtape.h
api_name:
-	TAPE_ERASE
product:
- Windows
targetos: Windows
req.typenames: TAPE_ERASE, *PTAPE_ERASE
---

# _TAPE_ERASE structure


## -description


The TAPE_ERASE structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560615">IOCTL_TAPE_ERASE</a> request to erase the current tape partition.


## -struct-fields




### -field Type

Indicates the type of erasure to perform. When this member is set to TAPE_ERASE_LONG, the tape partition is overwritten with a filler pattern. When it is set to TAPE_ERASE_SHORT, an end-of-recorded-data mark is written to the current position. 


### -field Immediate

Indicates that the target device should return status immediately, when set to <b>TRUE</b>. When this member is set to <b>FALSE</b>, the device should return status after the operation is complete. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560615">IOCTL_TAPE_ERASE</a>
 

 

