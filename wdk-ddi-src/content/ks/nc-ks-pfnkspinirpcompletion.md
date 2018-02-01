---
UID: NC:ks.PFNKSPINIRPCOMPLETION
title: PFNKSPINIRPCOMPLETION
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniPinIrpCompletion routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.
old-location: stream\avstrminipinirpcompletion.htm
old-project: stream
ms.assetid: 46b29026-b3a9-49cc-8f3d-0318516526d2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.avstrminipinirpcompletion, AVStrMiniPinIrpCompletion, AVStrMiniPinIrpCompletion routine [Streaming Media Devices], AVStrMiniPinIrpCompletion, PFNKSPINIRPCOMPLETION, PFNKSPINIRPCOMPLETION, ks/AVStrMiniPinIrpCompletion, avstclbk_fabf9c16-a37b-4101-9468-dc247545aea0.xml
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	AVStrMiniPinIrpCompletion
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSPINIRPCOMPLETION callback


## -description


An AVStream minidriver's <i>AVStrMiniPinIrpCompletion</i> routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.


## -prototype


````
PFNKSPINIRPCOMPLETION AVStrMiniPinIrpCompletion;

void AVStrMiniPinIrpCompletion(
  _In_ PKSPIN Pin,
  _In_ PIRP   Irp
)
{ ... }
````


## -parameters




### -param Pin [in]

Points to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which the callback is registered.


### -param Irp [in]

Points to an <a href="..\wdm\ns-wdm-_irp.md">IRP</a> which originated from the circuit to which <i>Pin</i> belongs.


## -returns


None



## -remarks


The minidriver specifies this routine's address in the <i>IrpCompletion</i> parameter of a call to <a href="..\ks\nf-ks-kspinregisterirpcompletioncallback.md">KsPinRegisterIrpCompletionCallback</a>.



## -see-also

<a href="..\ks\nf-ks-kspinregisterirpcompletioncallback.md">KsPinRegisterIrpCompletionCallback</a>

<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSPINIRPCOMPLETION routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

