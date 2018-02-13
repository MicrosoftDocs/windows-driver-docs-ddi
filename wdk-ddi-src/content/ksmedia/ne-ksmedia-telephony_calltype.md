---
UID: NE:ksmedia.TELEPHONY_CALLTYPE
title: TELEPHONY_CALLTYPE
author: windows-driver-content
description: The TELEPHONY_CALLTYPE enumeration defines constants that specify the type of phone call.
old-location: audio\telephony_calltype.htm
old-project: audio
ms.assetid: 8CF2CAF2-29F2-4B8B-B23F-B423392B2DAF
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: ksmedia/TELEPHONY_CALLTYPE_PACKETSWITCHED_LTE, audio.telephony_calltype, TELEPHONY_CALLTYPE enumeration [Audio Devices], ksmedia/TELEPHONY_CALLTYPE_PACKETSWITCHED_WLAN, TELEPHONY_CALLTYPE_CIRCUITSWITCHED, TELEPHONY_CALLTYPE_PACKETSWITCHED_LTE, ksmedia/TELEPHONY_CALLTYPE, ksmedia/TELEPHONY_CALLTYPE_CIRCUITSWITCHED, TELEPHONY_CALLTYPE_PACKETSWITCHED_WLAN, TELEPHONY_CALLTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
req.target-min-winversvr: None supported
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
-	ksmedia.h
apiname:
-	TELEPHONY_CALLTYPE
product: Windows
targetos: Windows
req.typenames: TELEPHONY_CALLTYPE
---

# TELEPHONY_CALLTYPE enumeration


## -description


The <b>TELEPHONY_CALLTYPE</b> enumeration defines constants that specify the type of phone call.


## -syntax


````
typedef enum  { 
  TELEPHONY_CALLTYPE_CIRCUITSWITCHED      = 0,
  TELEPHONY_CALLTYPE_PACKETSWITCHED_LTE   = 1,
  TELEPHONY_CALLTYPE_PACKETSWITCHED_WLAN  = 2
} TELEPHONY_CALLTYPE;
````


## -enum-fields




### -field TELEPHONY_CALLTYPE_CIRCUITSWITCHED

Specifies a circuit-switched phone call.


### -field TELEPHONY_CALLTYPE_PACKETSWITCHED_LTE

Specifies a packet-switched Long-Term Evolution (LTE) phone call.


### -field TELEPHONY_CALLTYPE_PACKETSWITCHED_WLAN

Specifies a packet-switched wireless LAN (WLAN) phone call.


## -see-also

<a href="..\ksmedia\ns-ksmedia-_tagkstelephony_callinfo.md">KSTELEPHONY_CALLINFO</a>



<a href="..\ksmedia\ns-ksmedia-_tagkstelephony_providerchange.md">KSTELEPHONY_PROVIDERCHANGE</a>



<a href="..\ksmedia\ns-ksmedia-_tagkstelephony_callcontrol.md">KSTELEPHONY_CALLCONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20TELEPHONY_CALLTYPE enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

