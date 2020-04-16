---
UID: NI:ntddvol.IOCTL_VOLUME_IS_CLUSTERED
title: IOCTL_VOLUME_IS_CLUSTERED (ntddvol.h)
description: Allows a driver or application to determine if a volume is clustered.
old-location: storage\ioctl_volume_is_clustered.htm
tech.root: storage
ms.assetid: aa8accf8-79c9-4868-b621-d468a121cb60
ms.date: 03/29/2018
keywords: ["IOCTL_VOLUME_IS_CLUSTERED IOCTL"]
ms.keywords: IOCTL_VOLUME_IS_CLUSTERED, IOCTL_VOLUME_IS_CLUSTERED control, IOCTL_VOLUME_IS_CLUSTERED control code [Storage Devices], k307_32e3c9a5-1828-4fbb-b7f1-9ddbd367f70f.xml, ntddvol/IOCTL_VOLUME_IS_CLUSTERED, storage.ioctl_volume_is_clustered
f1_keywords:
 - "ntddvol/IOCTL_VOLUME_IS_CLUSTERED"
req.header: ntddvol.h
req.include-header: Ntddvol.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows XP.
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
- Ntddvol.h
api_name:
- IOCTL_VOLUME_IS_CLUSTERED
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VOLUME_IS_CLUSTERED IOCTL


## -description


Allows  a driver or application to determine if a volume is clustered.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

 If the volume is clustered, the IOCTL returns <b>STATUS_SUCCESS</b>. If the volume is not clustered, the IOCTL returns  <b>STATUS_UNSUCCESSFUL</b>.


## -remarks



For an invalid disk type, such as dynamic disk, the disk management component will return <b>STATUS_INVALID_DEVICE_REQUEST</b>.



