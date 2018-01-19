---
UID: NE:ksmedia.TELEPHONY_CALLSTATE
title: TELEPHONY_CALLSTATE
author: windows-driver-content
description: The TELEPHONY_CALLSTATE enumeration defines constants that specify the state of a phone call.
old-location: audio\telephony_callstate.htm
old-project: audio
ms.assetid: 8191418A-7139-4BF4-9869-F21AA54EA8B3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: TELEPHONY_CALLSTATE, TELEPHONY_CALLSTATE
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
req.alt-api: TELEPHONY_CALLSTATE
req.alt-loc: ksmedia.h
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
req.typenames: TELEPHONY_CALLSTATE
---

# TELEPHONY_CALLSTATE enumeration



## -description
The <b>TELEPHONY_CALLSTATE</b> enumeration defines constants that specify the state of a phone call.



## -syntax

````
typedef enum  { 
  TELEPHONY_CALLSTATE_DISABLED            = 0,
  TELEPHONY_CALLSTATE_ENABLED             = 1,
  TELEPHONY_CALLSTATE_HOLD                = 2,
  TELEPHONY_CALLSTATE_PROVIDERTRANSITION  = 3
} TELEPHONY_CALLSTATE;
````


## -enum-fields

### -field TELEPHONY_CALLSTATE_DISABLED

Specifies that the phone call is disabled.


### -field TELEPHONY_CALLSTATE_ENABLED

Specifies that the phone call is enabled. This constant is set in a number of situations. For example, it will be set by the audio driver when the provider change operation is <b>TELEPHONY_PROVIDERCHANGEOP_END</b> and when <b>TELEPHONY_CALLCONTROLOP_ENABLE</b> is received.


### -field TELEPHONY_CALLSTATE_HOLD

Specifies that the phone call is on hold.


### -field TELEPHONY_CALLSTATE_PROVIDERTRANSITION

Specifies that the phone call is disabled. This constant is set by the audio driver when the provider change operation is <b>TELEPHONY_PROVIDERCHANGEOP_BEGIN</b>.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ksmedia\ns-ksmedia-_tagkstelephony_callinfo.md">KSTELEPHONY_CALLINFO</a>
</dt>
<dt>
<a href="..\ksmedia\ne-ksmedia-telephony_providerchangeop.md">TELEPHONY_PROVIDERCHANGEOP</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20TELEPHONY_CALLSTATE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

