---
UID: NC:ks.PFNKSFILTERVOID
title: PFNKSFILTERVOID
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniFilterReset routine is called when AVStream receives an IOCTL_KS_RESET_STATE to return the filter to the state it was in at Acquire-time.
old-location: stream\avstrminifilterreset.htm
old-project: stream
ms.assetid: 8259117b-87ef-410a-955b-6f99966574a6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.avstrminifilterreset, AVStrMiniFilterReset, AVStrMiniFilterReset routine [Streaming Media Devices], AVStrMiniFilterReset, PFNKSFILTERVOID, PFNKSFILTERVOID, ks/AVStrMiniFilterReset, avstclbk_71a3cd5d-faa7-4a7f-a341-deacfbcda051.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
-	UserDefined
apilocation:
-	ks.h
apiname:
-	AVStrMiniFilterReset
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSFILTERVOID callback


## -description


An AVStream minidriver's <i>AVStrMiniFilterReset</i> routine is called when AVStream receives an IOCTL_KS_RESET_STATE to return the filter to the state it was in at <i>Acquire</i>-time. This routine is also called when a queue associated with a pin on the filter is flushed. <i>This routine will only be called for a filter-centric filter</i>.


## -prototype


````
PFNKSFILTERVOID AVStrMiniFilterReset;

NTSTATUS AVStrMiniFilterReset(
  _In_ PKSFILTER Filter
)
{ ... }
````


## -parameters




### -param Filter [in]

Pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> to return to its previous state.


## -returns


AVStream does not currently use the return value.



## -remarks


For more information, see <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.

Note that it is not the filter in question, but rather a pin on this filter that actually receives the reset IOCTL.

The minidriver specifies this routine's address in the <b>Reset</b> member of its <a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a> structure.

The filter control mutex may be held during this function. See <a href="https://msdn.microsoft.com/402795a0-e567-4e7e-a7d8-b2ce29ffb8fd">Filter Control Mutex in AVStream</a>.

This routine is optional.



## -see-also

<a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSFILTERVOID routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

