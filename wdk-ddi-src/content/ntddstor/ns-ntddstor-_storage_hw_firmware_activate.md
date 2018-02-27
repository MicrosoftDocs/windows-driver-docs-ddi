---
UID: NS:ntddstor._STORAGE_HW_FIRMWARE_ACTIVATE
title: "_STORAGE_HW_FIRMWARE_ACTIVATE"
author: windows-driver-content
description: This structure contains information about the downloaded firmware to activate.
old-location: storage\storage_hw_firmware_activate.htm
old-project: storage
ms.assetid: FCE1DE7B-CDFE-4533-90E7-A400EC236007
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSTORAGE_HW_FIRMWARE_ACTIVATE, PSTORAGE_HW_FIRMWARE_ACTIVATE, PSTORAGE_HW_FIRMWARE_ACTIVATE structure pointer [Storage Devices], STORAGE_HW_FIRMWARE_ACTIVATE, STORAGE_HW_FIRMWARE_ACTIVATE structure [Storage Devices], _STORAGE_HW_FIRMWARE_ACTIVATE, ntddstor/PSTORAGE_HW_FIRMWARE_ACTIVATE, ntddstor/STORAGE_HW_FIRMWARE_ACTIVATE, storage.storage_hw_firmware_activate"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	ntddstor.h
apiname:
-	STORAGE_HW_FIRMWARE_ACTIVATE
product: Windows
targetos: Windows
req.typenames: STORAGE_HW_FIRMWARE_ACTIVATE, *PSTORAGE_HW_FIRMWARE_ACTIVATE
---

# _STORAGE_HW_FIRMWARE_ACTIVATE structure


## -description


This structure contains information about the downloaded firmware to activate.


## -syntax


````
typedef struct _STORAGE_HW_FIRMWARE_ACTIVATE {
  ULONG Version;
  ULONG Size;
  ULONG Flags;
  UCHAR Slot;
  UCHAR Reserved0[3];
} STORAGE_HW_FIRMWARE_ACTIVATE, *PSTORAGE_HW_FIRMWARE_ACTIVATE;
````


## -struct-fields




### -field Version

The version of this structure. This should be set to sizeof(STORAGE_HW_FIRMWARE_ACTIVATE).


### -field Size

The size of this structure. This should be set to sizeof(STORAGE_HW_FIRMWARE_ACTIVATE).


### -field Flags

The flags associated with the activation request. The following are valid flags that can be set in this member.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>STORAGE_HW_FIRMWARE_REQUEST_FLAG_CONTROLLER</td>
<td>Indicates that the target of the request is a controller or adapter, different than the device handle or object itself (e.g. NVMe SSD or HBA).</td>
</tr>
<tr>
<td>STORAGE_HW_FIRMWARE_REQUEST_FLAG_SWITCH_TO_EXISTING_FIRMWARE  </td>
<td>Indicates that an existing firmware image in the specified slot should be activated. </td>
</tr>
</table>
 


### -field Slot

The slot with the firmware image that is to be activated.


### -field Reserved0

Reserved for future use.

