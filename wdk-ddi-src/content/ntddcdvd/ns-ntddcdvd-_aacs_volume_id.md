---
UID: NS:ntddcdvd._AACS_VOLUME_ID
title: "_AACS_VOLUME_ID"
author: windows-driver-content
description: The AACS_VOLUME_ID structure contains an Advanced Access Content System (AACS) volume ID and the corresponding message authentication code (MAC).
old-location: storage\aacs_volume_id.htm
old-project: storage
ms.assetid: 3ad7a253-cc55-4613-8086-b8d08d9bd54f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PAACS_VOLUME_ID structure pointer [Storage Devices], ntddcdvd/AACS_VOLUME_ID, _AACS_VOLUME_ID, AACS_VOLUME_ID, PAACS_VOLUME_ID, *PAACS_VOLUME_ID, structs-DVD_f65fe36a-a9a4-4540-a349-2ac9827b5a91.xml, storage.aacs_volume_id, AACS_VOLUME_ID structure [Storage Devices], ntddcdvd/PAACS_VOLUME_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	ntddcdvd.h
apiname:
-	AACS_VOLUME_ID
product: Windows
targetos: Windows
req.typenames: AACS_VOLUME_ID, *PAACS_VOLUME_ID
---

# _AACS_VOLUME_ID structure


## -description


The AACS_VOLUME_ID structure contains an Advanced Access Content System (AACS) volume ID and the corresponding message authentication code (MAC).


## -syntax


````
typedef struct _AACS_VOLUME_ID {
  UCHAR VolumeID[16];
  UCHAR MAC[16];
} AACS_VOLUME_ID, *PAACS_VOLUME_ID;
````


## -struct-fields




### -field VolumeID

The volume identifier.


### -field MAC

The message authentication code (MAC) that the client uses to verify that the volume identifier is for the current AACS authentication sequence.


## -remarks



Clients retrieve an AACS volume ID with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_volume_id.md">IOCTL_AACS_READ_VOLUME_ID</a> request.




## -see-also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_volume_id.md">IOCTL_AACS_READ_VOLUME_ID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_VOLUME_ID structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

