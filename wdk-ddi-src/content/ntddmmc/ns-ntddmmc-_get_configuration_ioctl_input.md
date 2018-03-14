---
UID: NS:ntddmmc._GET_CONFIGURATION_IOCTL_INPUT
title: "_GET_CONFIGURATION_IOCTL_INPUT"
author: windows-driver-content
description: The GET_CONFIGURATION_IOCTL_INPUT structure is used in conjunction with the IOCTL_CDROM_GET_CONFIGURATION request to specify the sort of feature data that the request retrieves.
old-location: storage\get_configuration_ioctl_input.htm
old-project: storage
ms.assetid: 6b8d9cbf-bb05-40a1-9129-52510befebe3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PGET_CONFIGURATION_IOCTL_INPUT, GET_CONFIGURATION_IOCTL_INPUT, GET_CONFIGURATION_IOCTL_INPUT structure [Storage Devices], PGET_CONFIGURATION_IOCTL_INPUT, PGET_CONFIGURATION_IOCTL_INPUT structure pointer [Storage Devices], _GET_CONFIGURATION_IOCTL_INPUT, ntddmmc/GET_CONFIGURATION_IOCTL_INPUT, ntddmmc/PGET_CONFIGURATION_IOCTL_INPUT, storage.get_configuration_ioctl_input, structs-CD-ROM_1bac7730-693e-4d41-b672-260f83765e35.xml"
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
-	GET_CONFIGURATION_IOCTL_INPUT
product: Windows
targetos: Windows
req.typenames: GET_CONFIGURATION_IOCTL_INPUT, *PGET_CONFIGURATION_IOCTL_INPUT
---

# _GET_CONFIGURATION_IOCTL_INPUT structure


## -description


The GET_CONFIGURATION_IOCTL_INPUT structure is used in conjunction with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_configuration.md">IOCTL_CDROM_GET_CONFIGURATION</a> request to specify the sort of feature data that the request retrieves.


## -syntax


````
typedef struct _GET_CONFIGURATION_IOCTL_INPUT {
  FEATURE_NUMBER Feature;
  ULONG          RequestType;
  PVOID          Reserved[2];
} GET_CONFIGURATION_IOCTL_INPUT, *PGET_CONFIGURATION_IOCTL_INPUT;
````


## -struct-fields




### -field Feature

Contains an enumerator value of type FEATURE_NUMBER that indicates the type of feature.


### -field RequestType

SCSI_GET_CONFIGURATION_REQUEST_TYPE_ALL - Instructs the device to report all of the profiles.

SCSI_GET_CONFIGURATION_REQUEST_TYPE_CURRENT - Instructs the device to report the current profile.

SCSI_GET_CONFIGURATION_REQUEST_TYPE_ONE - Instructs the device to report one and only one of the profiles.


### -field Reserved

Reserved.


## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_configuration.md">IOCTL_CDROM_GET_CONFIGURATION</a>



<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GET_CONFIGURATION_IOCTL_INPUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

