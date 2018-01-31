---
UID: NS:mpiowmi._GetPathConfiguration_OUT
title: "_GetPathConfiguration_OUT"
author: windows-driver-content
description: The GetPathConfiguration_OUT structure is used to report the output parameters that are associated with the GetPathConfiguration method.
old-location: storage\getpathconfiguration_out.htm
old-project: storage
ms.assetid: 055db46e-59fc-4eb9-93d7-16d680495220
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: GetPathConfiguration_OUT, structs-scsibus_4d2ebbae-67ff-42bc-8904-c33f914485cd.xml, _GetPathConfiguration_OUT, PGetPathConfiguration_OUT structure pointer [Storage Devices], GetPathConfiguration_OUT structure [Storage Devices], mpiowmi/GetPathConfiguration_OUT, storage.getpathconfiguration_out, PGetPathConfiguration_OUT, mpiowmi/PGetPathConfiguration_OUT, *PGetPathConfiguration_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
-	mpiowmi.h
apiname:
-	GetPathConfiguration_OUT
product: Windows
targetos: Windows
req.typenames: GetPathConfiguration_OUT, *PGetPathConfiguration_OUT
---

# _GetPathConfiguration_OUT structure


## -description


The GetPathConfiguration_OUT structure is used to report the output parameters that are associated with the GetPathConfiguration method.


## -syntax


````
typedef struct _GetPathConfiguration_OUT {
  ULONG     EntryCount;
  SCSI_ADDR Address[1];
} GetPathConfiguration_OUT, *PGetPathConfiguration_OUT;
````


## -struct-fields




#### - EntryCount

A 32-bitfield that indicates the number of entries contained in the array of SCSI addresses.


#### - Address

An array that returns information about the SCSI addresses. The number of elements in the array is given by EntryCount and each element of the array represents an instance of an SCSI_ADDR structure.

