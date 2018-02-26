---
UID: NS:ntddmmc._FEATURE_DATA_CD_AUDIO_ANALOG_PLAY
title: "_FEATURE_DATA_CD_AUDIO_ANALOG_PLAY"
author: windows-driver-content
description: The FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure holds information about the CD Audio External Play feature.
old-location: storage\feature_data_cd_audio_analog_play.htm
old-project: storage
ms.assetid: 01c34bb8-b164-425d-b81c-7eefc08296e2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY, ,, A, C, D, E, F, FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure [Storage Devices], G, I, L, N, O, P, PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY, PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure pointer [Storage Devices], R, T, U, Y, _, _FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, ntddmmc/FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, ntddmmc/PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY, storage.feature_data_cd_audio_analog_play, structs-CD-ROM_87a067ea-0911-429b-808a-102f9600ecac.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddmmc.h
apiname:
-	FEATURE_DATA_CD_AUDIO_ANALOG_PLAY
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, *PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY
---

# _FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure


## -description


The FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure holds information about the CD Audio External Play feature.


## -syntax


````
typedef struct _FEATURE_DATA_CD_AUDIO_ANALOG_PLAY {
  FEATURE_HEADER Header;
  UCHAR          SeperateVolume  :1;
  UCHAR          SeperateChannelMute  :1;
  UCHAR          ScanSupported  :1;
  UCHAR          Reserved1  :5;
  UCHAR          Reserved2;
  UCHAR          NumerOfVolumeLevels[2];
} FEATURE_DATA_CD_AUDIO_ANALOG_PLAY, *PFEATURE_DATA_CD_AUDIO_ANALOG_PLAY;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


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

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_CD_AUDIO_ANALOG_PLAY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

