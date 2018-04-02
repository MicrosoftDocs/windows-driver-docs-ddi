---
UID: NS:ntddcdvd._AACS_SEND_CHALLENGE_KEY
title: "_AACS_SEND_CHALLENGE_KEY"
author: windows-driver-content
description: The AACS_SEND_CHALLENGE_KEY structure is defined as a challenge key that host software sends to an Advanced Access Content System (AACS) device.
old-location: storage\aacs_send_challenge_key.htm
old-project: storage
ms.assetid: 3985c396-7e85-46b6-8790-1ec45931a4ab
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PAACS_SEND_CHALLENGE_KEY, AACS_SEND_CHALLENGE_KEY, AACS_SEND_CHALLENGE_KEY structure [Storage Devices], PAACS_SEND_CHALLENGE_KEY, PAACS_SEND_CHALLENGE_KEY structure pointer [Storage Devices], _AACS_SEND_CHALLENGE_KEY, ntddcdvd/AACS_SEND_CHALLENGE_KEY, ntddcdvd/PAACS_SEND_CHALLENGE_KEY, storage.aacs_send_challenge_key, structs-DVD_f9e8ef67-414c-4a98-82ab-88674dabe24b.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdvd.h
api_name:
-	AACS_SEND_CHALLENGE_KEY
product: Windows
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

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff550108">AACS_CHALLENGE_KEY</a> that specifies the challenge key to retrieve.


## -remarks



Host software send this challenge key to an AACS-compliant device with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559302">IOCTL_AACS_SEND_CHALLENGE_KEY</a> request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550108">AACS_CHALLENGE_KEY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559302">IOCTL_AACS_SEND_CHALLENGE_KEY</a>
 

 

