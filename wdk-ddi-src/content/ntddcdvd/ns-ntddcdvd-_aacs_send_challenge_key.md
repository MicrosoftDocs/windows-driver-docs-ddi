---
UID: NS:ntddcdvd._AACS_SEND_CHALLENGE_KEY
title: "_AACS_SEND_CHALLENGE_KEY"
author: windows-driver-content
description: The AACS_SEND_CHALLENGE_KEY structure is defined as a challenge key that host software sends to an Advanced Access Content System (AACS) device.
old-location: storage\aacs_send_challenge_key.htm
old-project: storage
ms.assetid: 3985c396-7e85-46b6-8790-1ec45931a4ab
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-DVD_f9e8ef67-414c-4a98-82ab-88674dabe24b.xml, *PAACS_SEND_CHALLENGE_KEY, ntddcdvd/PAACS_SEND_CHALLENGE_KEY, AACS_SEND_CHALLENGE_KEY structure [Storage Devices], _AACS_SEND_CHALLENGE_KEY, AACS_SEND_CHALLENGE_KEY, ntddcdvd/AACS_SEND_CHALLENGE_KEY, storage.aacs_send_challenge_key, PAACS_SEND_CHALLENGE_KEY, PAACS_SEND_CHALLENGE_KEY structure pointer [Storage Devices]
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
-	AACS_SEND_CHALLENGE_KEY
product: Windows
targetos: Windows
req.typenames: AACS_SEND_CHALLENGE_KEY, *PAACS_SEND_CHALLENGE_KEY
---

# _AACS_SEND_CHALLENGE_KEY structure


## -description


The AACS_SEND_CHALLENGE_KEY structure is defined as a challenge key that host software sends to an Advanced Access Content System (AACS) device.


## -syntax


````
typedef struct _AACS_SEND_CHALLENGE_KEY {
  DVD_SESSION_ID     SessionId;
  AACS_CHALLENGE_KEY ChallengeKey;
} AACS_SEND_CHALLENGE_KEY, *PAACS_SEND_CHALLENGE_KEY;
````


## -struct-fields




### -field SessionId

A value of type DVD_SESSION_ID that specifies an Authentication Grant Identifier (AGID).


### -field ChallengeKey

A structure of type <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_challenge_key.md">AACS_CHALLENGE_KEY</a> that specifies the challenge key to retrieve.


## -remarks


Host software send this challenge key to an AACS-compliant device with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_send_challenge_key.md">IOCTL_AACS_SEND_CHALLENGE_KEY</a> request.



## -see-also

<a href="..\ntddcdvd\ns-ntddcdvd-_aacs_challenge_key.md">AACS_CHALLENGE_KEY</a>

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_send_challenge_key.md">IOCTL_AACS_SEND_CHALLENGE_KEY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_SEND_CHALLENGE_KEY structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

