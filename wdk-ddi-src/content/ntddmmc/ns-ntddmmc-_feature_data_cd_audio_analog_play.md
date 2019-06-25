---
UID: NS:ntddmmc._FEATURE_DATA_CD_AUDIO_ANALOG_PLAY
title: _FEATURE_DATA_CD_AUDIO_ANALOG_PLAY (ntddmmc.h)
description: The FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure holds information about the CD Audio External Play feature.
old-location: storage\feature_data_cd_audio_analog_play.htm
tech.root: storage
ms.assetid: 01c34bb8-b164-425d-b81c-7eefc08296e2
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY, FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure [Storage Devices], PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY, PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure pointer [Storage Devices], _FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, ntddmmc/FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, ntddmmc/PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY, storage.feature_data_cd_audio_analog_play, structs-CD-ROM_87a067ea-0911-429b-808a-102f9600ecac.xml"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddmmc.h
api_name:
- FEATURE_DATA_CD_AUDIO_ANALOG_PLAY
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, *PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY
---

# _FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure


## -description


The FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure holds information about the CD Audio External Play feature.


## -struct-fields




### -field Header

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field SeperateVolume

Indicates, when set to zero, that all audio channels have the same volume level. When set to 1, it indicates that the volume of each audio channel can be set separately. 


### -field SeperateChannelMute

Indicates, when set to zero, that all audio channels are muted simultaneously. When set to 1, it indicates that each audio channel can be muted independently. 


### -field ScanSupported

Indicates, when set to 1, that the SCAN command is supported. See the <i>SCSI Multimedia 3 </i>(<i>MMC-3</i>) specification for a description of the SCAN command. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


### -field NumerOfVolumeLevels


## -remarks



This structure holds data for the feature named "CD Audio External Play" by the <i>MMC-3 </i>specification. Devices that support this feature can play CD audio data and channel it directly to an external output.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>
 

 

