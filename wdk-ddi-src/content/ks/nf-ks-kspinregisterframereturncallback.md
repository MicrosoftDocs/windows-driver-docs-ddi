---
UID: NF:ks.KsPinRegisterFrameReturnCallback
title: KsPinRegisterFrameReturnCallback function
author: windows-driver-content
description: The KsPinRegisterFrameReturnCallback function registers a frame return callback with AVStream for a given pin.
old-location: stream\kspinregisterframereturncallback.htm
old-project: stream
ms.assetid: 480f33e7-6fe6-40a1-9e1b-351378b7e003
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KsPinRegisterFrameReturnCallback function [Streaming Media Devices], avfunc_16d1d4cd-f3ae-4cc0-b903-1db1f5b40a6f.xml, ks/KsPinRegisterFrameReturnCallback, KsPinRegisterFrameReturnCallback, stream.kspinregisterframereturncallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsPinRegisterFrameReturnCallback
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinRegisterFrameReturnCallback function


## -description


The<b> KsPinRegisterFrameReturnCallback </b>function registers a frame return callback with AVStream for a given pin.


## -syntax


````
void KsPinRegisterFrameReturnCallback(
  _In_ PKSPIN              Pin,
  _In_ PFNKSPINFRAMERETURN FrameReturn
);
````


## -parameters




### -param Pin [in]

A pointer to the AVStream <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure that you want to place into injection mode by registering a frame return callback.


### -param FrameReturn [in]

This parameter supplies the address of a minidriver-provided <a href="..\ks\nc-ks-pfnkspinframereturn.md">AVStrMiniFrameReturn</a> routine.


## -returns



None




## -remarks



If a pin has registered a frame return callback before transitioning from <b>KSSTATE_STOP</b> to KSSTATE_ACQUIRE, the pin is placed into injection mode. This indicates that the pin will not receive buffers and fill them, but rather manually inject data frames into the circuit using <b>KsPinSubmitFrame </b>or <b>KsPinSubmitFrameMdl</b>. When the data frame completes its travel around the circuit and returns to the pin on which it was submitted, AVStream recycles it by calling <a href="..\ks\nc-ks-pfnkspinframereturn.md">AVStrMiniFrameReturn</a>.

Minidrivers that call this function are directly responsible for injecting frames into the circuit; they do not receive buffers to fill and do not directly interact with the queue as do most minidrivers. Also note that the frame return callback should be registered before the kernel pipe section is created. The kernel pipe section is created when the pin transitions to KSSTATE_ACQUIRE. For more information, see <a href="https://msdn.microsoft.com/cdfb1763-92a8-4a60-8f49-2af34a8beca5">Frame Injection</a>.




## -see-also

<a href="..\ks\nc-ks-pfnkspinframereturn.md">AVStrMiniFrameReturn</a>



<a href="..\ks\nf-ks-kspinsubmitframemdl.md">KsPinSubmitFrameMdl</a>



<a href="..\ks\nf-ks-kspinsubmitframe.md">KsPinSubmitFrame</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinRegisterFrameReturnCallback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

