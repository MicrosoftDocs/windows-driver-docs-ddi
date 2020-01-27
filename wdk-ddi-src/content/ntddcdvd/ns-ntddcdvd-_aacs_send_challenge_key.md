---
UID: NS:ntddcdvd._AACS_SEND_CHALLENGE_KEY
title: _AACS_SEND_CHALLENGE_KEY (ntddcdvd.h)
description: The AACS_SEND_CHALLENGE_KEY structure is defined as a challenge key that host software sends to an Advanced Access Content System (AACS) device.
old-location: storage\aacs_send_challenge_key.htm
tech.root: storage
ms.assetid: 3985c396-7e85-46b6-8790-1ec45931a4ab
ms.date: 03/29/2018
ms.keywords: "*PAACS_SEND_CHALLENGE_KEY, AACS_SEND_CHALLENGE_KEY, AACS_SEND_CHALLENGE_KEY structure [Storage Devices], PAACS_SEND_CHALLENGE_KEY, PAACS_SEND_CHALLENGE_KEY structure pointer [Storage Devices], _AACS_SEND_CHALLENGE_KEY, ntddcdvd/AACS_SEND_CHALLENGE_KEY, ntddcdvd/PAACS_SEND_CHALLENGE_KEY, storage.aacs_send_challenge_key, structs-DVD_f9e8ef67-414c-4a98-82ab-88674dabe24b.xml"
f1_keywords:
 - "ntddcdvd/AACS_SEND_CHALLENGE_KEY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddcdvd.h
api_name:
- AACS_SEND_CHALLENGE_KEY
product:
- Windows
targetos: Windows
req.typenames: AACS_SEND_CHALLENGE_KEY, *PAACS_SEND_CHALLENGE_KEY
---

# _AACS_SEND_CHALLENGE_KEY structure


## -description


The AACS_SEND_CHALLENGE_KEY structure is defined as a challenge key that host software sends to an Advanced Access Content System (AACS) device.


## -struct-fields




### -field SessionId

A value of type DVD_SESSION_ID that specifies an Authentication Grant Identifier (AGID).


### -field ChallengeKey

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_challenge_key">AACS_CHALLENGE_KEY</a> that specifies the challenge key to retrieve.


## -remarks



Host software send this challenge key to an AACS-compliant device with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_send_challenge_key">IOCTL_AACS_SEND_CHALLENGE_KEY</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_challenge_key">AACS_CHALLENGE_KEY</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_send_challenge_key">IOCTL_AACS_SEND_CHALLENGE_KEY</a>
 

 

