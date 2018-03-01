---
UID: NC:ks.PFNKSPINFRAMERETURN
title: PFNKSPINFRAMERETURN
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniFrameReturn routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed.
old-location: stream\avstrminiframereturn.htm
old-project: stream
ms.assetid: 842ed1ac-4043-41ce-90e5-94c9098e9da4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniFrameReturn, AVStrMiniFrameReturn routine [Streaming Media Devices], PFNKSPINFRAMERETURN, avstclbk_e7edb74a-8c38-4e7d-9978-849e5d88c153.xml, ks/AVStrMiniFrameReturn, stream.avstrminiframereturn
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniFrameReturn
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSPINFRAMERETURN callback


## -description


An AVStream minidriver's <i>AVStrMiniFrameReturn</i> routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed.


## -prototype


````
PFNKSPINFRAMERETURN AVStrMiniFrameReturn;

void AVStrMiniFrameReturn(
  _In_     PKSPIN   Pin,
  _In_opt_ PVOID    Data,
  _In_opt_ ULONG    Size,
  _In_opt_ PMDL     Mdl,
  _In_opt_ PVOID    Context,
  _In_     NTSTATUS Status
)
{ ... }
````


## -parameters




### -param Pin [in]

Pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure representing the pin on which the frame was injected.


### -param Data [in, optional]

Pointer to the buffer originally specified in the call to <a href="..\ks\nf-ks-kspinsubmitframe.md">KsPinSubmitFrame</a>.


### -param OPTIONAL


### -param Mdl [in, optional]

Pointer to a memory descriptor list describing the injected frame as in the call to <a href="..\ks\nf-ks-kspinsubmitframemdl.md">KsPinSubmitFrameMdl</a><b>.</b>


### -param Context [in, optional]

Pointer to the minidriver-supplied context buffer attached to the frame when the frame was injected into the circuit.


### -param Status [in]

Contains a copy of <i>Irp-&gt;IoStatus.Status</i> for the IRP to which the requested frame was attached.


#### - Size [in, optional]

Specifies the size in bytes of <i>Data</i> as originally specified in <a href="..\ks\nf-ks-kspinsubmitframe.md">KsPinSubmitFrame</a>.


## -returns



None




## -remarks



The minidriver specifies this routine's address in the <i>FrameReturn</i> parameter of a call to <a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>.




## -see-also

<a href="..\ks\nf-ks-kspinregisterframereturncallback.md">KsPinRegisterFrameReturnCallback</a>



<a href="..\ks\nf-ks-kspinsubmitframemdl.md">KsPinSubmitFrameMdl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSPINFRAMERETURN routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

