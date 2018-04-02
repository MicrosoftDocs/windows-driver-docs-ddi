---
UID: NS:ntddmmc._FEATURE_DATA_WRITE_PROTECT
title: "_FEATURE_DATA_WRITE_PROTECT"
author: windows-driver-content
description: The FEATURE_DATA_WRITE_PROTECT structure contains information about the Write Protect feature.
old-location: storage\feature_data_write_protect.htm
old-project: storage
ms.assetid: 16582fce-179a-4a99-9e4c-6f7ca1d3ddef
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_WRITE_PROTECT, FEATURE_DATA_WRITE_PROTECT, FEATURE_DATA_WRITE_PROTECT structure [Storage Devices], PFEATURE_DATA_WRITE_PROTECT, PFEATURE_DATA_WRITE_PROTECT structure pointer [Storage Devices], _FEATURE_DATA_WRITE_PROTECT, ntddmmc/FEATURE_DATA_WRITE_PROTECT, ntddmmc/PFEATURE_DATA_WRITE_PROTECT, storage.feature_data_write_protect, structs-CD-ROM_67c6f24f-271e-4452-8b5f-fc6719c1d291.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_WRITE_PROTECT
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_WRITE_PROTECT, *PFEATURE_DATA_WRITE_PROTECT
---

# _FEATURE_DATA_WRITE_PROTECT structure


## -description


The FEATURE_DATA_WRITE_PROTECT structure contains information about the Write Protect feature. 


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field SupportsSWPPBit

Indicates, when set to 1, that the device supports set/release PWP status. If additionally <b>SupportsPersistentWriteProtect</b> is set to 1, the device supports the SEND DVD STRUCTURE command with Format = 0xC0. For more details on the write protect feature see the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. 


### -field SupportsPersistentWriteProtect

Indicates, when set to 1, that the device supports the persistent write protect bit of the time-out &amp; protect mode page. For more details on the write protect feature see the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. 


### -field WriteInhibitDCB


### -field DiscWriteProtectPAC


### -field Reserved01


### -field Reserved2

Reserved. 


## -remarks



This structure holds data for the feature named "Write Protect" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to change the write-protection state of the media programmatically. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

