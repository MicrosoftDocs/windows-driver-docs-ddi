---
UID: NS:ntddmmc._FEATURE_DATA_REMOVABLE_MEDIUM
title: "_FEATURE_DATA_REMOVABLE_MEDIUM"
author: windows-driver-content
description: The FEATURE_DATA_REMOVABLE_MEDIUM structure contains data for the removable medium feature.
old-location: storage\feature_data_removable_medium.htm
old-project: storage
ms.assetid: b25feb68-75bb-4a9d-b842-e15f619a18c4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddmmc/FEATURE_DATA_REMOVABLE_MEDIUM, ntddmmc/PFEATURE_DATA_REMOVABLE_MEDIUM, FEATURE_DATA_REMOVABLE_MEDIUM, storage.feature_data_removable_medium, FEATURE_DATA_REMOVABLE_MEDIUM structure [Storage Devices], *PFEATURE_DATA_REMOVABLE_MEDIUM, structs-CD-ROM_f9ce701e-11b7-478e-969e-c2744477d348.xml, _FEATURE_DATA_REMOVABLE_MEDIUM, PFEATURE_DATA_REMOVABLE_MEDIUM structure pointer [Storage Devices], PFEATURE_DATA_REMOVABLE_MEDIUM
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
-	FEATURE_DATA_REMOVABLE_MEDIUM
product: Windows
targetos: Windows
req.typenames: "*PFEATURE_DATA_REMOVABLE_MEDIUM, FEATURE_DATA_REMOVABLE_MEDIUM"
---

# _FEATURE_DATA_REMOVABLE_MEDIUM structure


## -description


The FEATURE_DATA_REMOVABLE_MEDIUM structure contains data for the removable medium feature. 


## -syntax


````
typedef struct _FEATURE_DATA_REMOVABLE_MEDIUM {
  FEATURE_HEADER Header;
  UCHAR          Lockable  :1;
  UCHAR          Reserved1  :1;
  UCHAR          DefaultToPrevent  :1;
  UCHAR          Eject  :1;
  UCHAR          Reserved2  :1;
  UCHAR          LoadingMechanism  :3;
  UCHAR          Reserved3[3];
} FEATURE_DATA_REMOVABLE_MEDIUM, *PFEATURE_DATA_REMOVABLE_MEDIUM;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Lockable

Indicates, when set to 1, that the initiator can lock the medium into the device. When set to zero, this bit indicates that the medium cannot be locked into the device. 


### -field DBML

 


### -field DefaultToPrevent

Indicates, when set to zero, that the prevent jumper is present. This overrides the lock command, so that locking the device shall not prevent the insertion of media.


### -field Eject

Indicates, when set to 1, that the device can eject the medium or magazine. When set to zero, this bit indicates that the device cannot eject the medium or magazine by means of the normal start/stop command sequence. 


### -field Load

 


### -field LoadingMechanism

Indicates the type of loading mechanism. See the <i>SCSI Multimedia - 4 (MMC-4)</i> specification for the list of values that this member can take. 


### -field Reserved3

Reserved. 


#### - Reserved1

Reserved. 


#### - Reserved2

Reserved. 


## -remarks


This structure holds data for the feature named "Removable Medium" by the <i>MMC-3 </i>specification. Devices that support this feature allow the medium to be removed from the device. They also can communicate to the initiator that the user wants to eject the medium or has inserted a new medium. 



## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_REMOVABLE_MEDIUM structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

