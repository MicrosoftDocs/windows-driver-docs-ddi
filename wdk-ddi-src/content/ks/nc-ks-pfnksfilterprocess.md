---
UID: NC:ks.PFNKSFILTERPROCESS
title: PFNKSFILTERPROCESS
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniFilterProcess routine is called when the filter is meant to process frames. It is used to perform Filter-Centric Processing.
old-location: stream\avstrminifilterprocess.htm
old-project: stream
ms.assetid: f1998d68-1c9e-4527-a174-b22a8c301e63
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniFilterProcess, AVStrMiniFilterProcess routine [Streaming Media Devices], PFNKSFILTERPROCESS, avstclbk_220bff5f-a966-460b-9157-b512cfc9c336.xml, ks/AVStrMiniFilterProcess, stream.avstrminifilterprocess
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
req.irql: "(See Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	AVStrMiniFilterProcess
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSFILTERPROCESS callback


## -description


An AVStream minidriver's <i>AVStrMiniFilterProcess</i> routine is called when the filter is meant to process frames. It is used to perform <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.


## -prototype


````
PFNKSFILTERPROCESS AVStrMiniFilterProcess;

NTSTATUS AVStrMiniFilterProcess(
  _In_ PKSFILTER                Filter,
  _In_ PKSPROCESSPIN_INDEXENTRY ProcessPinsIndex
)
{ ... }
````


## -parameters




### -param Filter [in]

Pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure that must process frames.


### -param Index








#### - ProcessPinsIndex [in]

Pointer to an array of <a href="..\ks\ns-ks-_ksprocesspin_indexentry.md">KSPROCESSPIN_INDEXENTRY</a> structures that AVStream orders by pin ID.


## -returns



Return STATUS_SUCCESS to continue processing. Return STATUS_PENDING to stop processing until the next triggering event. The minidriver may return an error code, but this will be treated as described for STATUS_PENDING.




## -remarks



The minidriver specifies this routine's address in the <b>Process</b> member of its <a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a> structure.

The routine is called at either IRQL = DISPATCH_LEVEL or PASSIVE_LEVEL depending on the preference expressed in the filter descriptor. Filter descriptors that specify KSFILTER_FLAG_DISPATCH_LEVEL_PROCESSING may have their process callback at DISPATCH_LEVEL; filter descriptors that do not specify this flag will have their process callback at PASSIVE_LEVEL.

For more information, see <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a> and <a href="https://msdn.microsoft.com/f60d4dbd-61e6-4ae2-aa43-9edc8f36c3ff">Restarting Processing in AVStream</a>.

This routine is optional.




## -see-also

<a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a>



<a href="..\ks\ns-ks-_ksprocesspin_indexentry.md">KSPROCESSPIN_INDEXENTRY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSFILTERPROCESS routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

