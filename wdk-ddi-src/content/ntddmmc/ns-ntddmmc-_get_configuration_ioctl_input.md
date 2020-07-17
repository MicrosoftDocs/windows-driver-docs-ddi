---
UID: NS:ntddmmc._GET_CONFIGURATION_IOCTL_INPUT
title: _GET_CONFIGURATION_IOCTL_INPUT (ntddmmc.h)
description: The GET_CONFIGURATION_IOCTL_INPUT structure is used in conjunction with the IOCTL_CDROM_GET_CONFIGURATION request to specify the sort of feature data that the request retrieves.
old-location: storage\get_configuration_ioctl_input.htm
tech.root: storage
ms.assetid: 6b8d9cbf-bb05-40a1-9129-52510befebe3
ms.date: 03/29/2018
keywords: ["_GET_CONFIGURATION_IOCTL_INPUT structure"]
ms.keywords: "*PGET_CONFIGURATION_IOCTL_INPUT, GET_CONFIGURATION_IOCTL_INPUT, GET_CONFIGURATION_IOCTL_INPUT structure [Storage Devices], PGET_CONFIGURATION_IOCTL_INPUT, PGET_CONFIGURATION_IOCTL_INPUT structure pointer [Storage Devices], _GET_CONFIGURATION_IOCTL_INPUT, ntddmmc/GET_CONFIGURATION_IOCTL_INPUT, ntddmmc/PGET_CONFIGURATION_IOCTL_INPUT, storage.get_configuration_ioctl_input, structs-CD-ROM_1bac7730-693e-4d41-b672-260f83765e35.xml"
f1_keywords:
 - "ntddmmc/GET_CONFIGURATION_IOCTL_INPUT"
 - "GET_CONFIGURATION_IOCTL_INPUT"
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
- GET_CONFIGURATION_IOCTL_INPUT
product:
- Windows
targetos: Windows
req.typenames: GET_CONFIGURATION_IOCTL_INPUT, *PGET_CONFIGURATION_IOCTL_INPUT
---

# _GET_CONFIGURATION_IOCTL_INPUT structure


## -description


The GET_CONFIGURATION_IOCTL_INPUT structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_configuration">IOCTL_CDROM_GET_CONFIGURATION</a> request to specify the sort of feature data that the request retrieves.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_configuration">IOCTL_CDROM_GET_CONFIGURATION</a>
 

 

