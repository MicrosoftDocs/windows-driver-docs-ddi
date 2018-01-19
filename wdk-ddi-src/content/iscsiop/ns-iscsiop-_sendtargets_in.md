---
UID: NS:iscsiop._SendTargets_IN
title: _SendTargets_IN
author: windows-driver-content
description: The SendTargets_IN structure holds the input data for the SendTargets method.
old-location: storage\sendtargets_in.htm
old-project: storage
ms.assetid: fa6af43c-4fbd-43b5-9c3d-61254dfe894f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SendTargets_IN, SendTargets_IN, *PSendTargets_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SendTargets_IN
req.alt-loc: iscsiop.h
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
req.typenames: SendTargets_IN, *PSendTargets_IN
---

# _SendTargets_IN structure



## -description
The SendTargets_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565526">SendTargets</a> method.



## -syntax

````
typedef struct _SendTargets_IN {
  ULONGLONG UniqueSessionId;
  WCHAR     SendTargetsText[223 + 1];
} SendTargets_IN, *PSendTargets_IN;
````


## -struct-fields

### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The LoginToTarget and AddConnectionToSession methods both return this value in their UniqueSessionId parameter.


### -field SendTargetsText

The authentication key text in the PDU.


## -remarks
You must implement this method.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565526">SendTargets</a>
</dt>
<dt>
<a href="..\iscsiop\ns-iscsiop-_sendtargets_out.md">SendTargets_OUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendTargets_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

