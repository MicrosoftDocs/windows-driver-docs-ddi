---
UID: NS:ntddmmc._FEATURE_DATA_REAL_TIME_STREAMING
title: "_FEATURE_DATA_REAL_TIME_STREAMING"
author: windows-driver-content
description: The FEATURE_DATA_REAL_TIME_STREAMING structure holds information about the Real Time Streaming feature.
old-location: storage\feature_data_real_time_streaming.htm
old-project: storage
ms.assetid: 3b1b54cc-52a5-48ce-a637-70e289c1944e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_REAL_TIME_STREAMING, FEATURE_DATA_REAL_TIME_STREAMING, FEATURE_DATA_REAL_TIME_STREAMING structure [Storage Devices], PFEATURE_DATA_REAL_TIME_STREAMING, PFEATURE_DATA_REAL_TIME_STREAMING structure pointer [Storage Devices], _FEATURE_DATA_REAL_TIME_STREAMING, ntddmmc/FEATURE_DATA_REAL_TIME_STREAMING, ntddmmc/PFEATURE_DATA_REAL_TIME_STREAMING, storage.feature_data_real_time_streaming, structs-CD-ROM_2bd0a42c-a5b8-4a5b-958e-56e1a47a6499.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_REAL_TIME_STREAMING
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_REAL_TIME_STREAMING, *PFEATURE_DATA_REAL_TIME_STREAMING
---

# _FEATURE_DATA_REAL_TIME_STREAMING structure


## -description


The FEATURE_DATA_REAL_TIME_STREAMING structure holds information about the Real Time Streaming feature. 


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field StreamRecording

Indicates, when set to 1, that the device supports the stream recording operation. When set to zero, this bit indicates that the device might not support the stream recording operation. 


### -field WriteSpeedInGetPerf

Indicates, when set to 1, that the device supports the write speed data of the GET PERFORMANCE command and the WRC field of the SETSTREAMING command. 


### -field WriteSpeedInMP2A

Indicates, when set to 1, that the device supports CD/DVD capabilities &amp; mechanical status mode page.


### -field SetCDSpeed

Indicates, when set to 1, that the device supports the SET CD SPEED command. When set to zero, it indicates that the device does not support the SET CD SPEED command.


### -field ReadBufferCapacityBlock

Indicates, when set to 1, that the device supports the READ BUFFERCAPACITY command.


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


## -remarks



This structure holds data for the feature named "Real Time Streaming" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature allow the initiator to specify the performance level of the device within certain limits allowed by the device. These devices must also indicate to the initiator whether they support stream playback operations. 

When queried, devices supporting this feature must return the information indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

