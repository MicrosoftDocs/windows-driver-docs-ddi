---
UID: NF:ks.KsPinRegisterPowerCallbacks
title: KsPinRegisterPowerCallbacks function
author: windows-driver-content
description: The KsPinRegisterPowerCallbacks function registers power management callbacks for Pin.
old-location: stream\kspinregisterpowercallbacks.htm
old-project: stream
ms.assetid: e498a907-8d20-4d00-9411-8e82030af223
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kspinregisterpowercallbacks, avfunc_2e133cdb-6afa-47a7-8d3b-8293b63428b5.xml, KsPinRegisterPowerCallbacks function [Streaming Media Devices], ks/KsPinRegisterPowerCallbacks, KsPinRegisterPowerCallbacks
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsPinRegisterPowerCallbacks
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinRegisterPowerCallbacks function


## -description


The<b> KsPinRegisterPowerCallbacks </b>function registers power management callbacks for <i>Pin</i>.


## -syntax


````
void KsPinRegisterPowerCallbacks(
  _In_     PKSPIN        Pin,
  _In_opt_ PFNKSPINPOWER Sleep,
  _In_opt_ PFNKSPINPOWER Wake
);
````


## -parameters




#### - Pin [in]

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which to register power callbacks. Note that the pin must actually process (be pin-centric) in order to receive power notification messages.


#### - Sleep [in, optional]

This parameter supplies the address of a <a href="..\ks\nc-ks-pfnkspinpower.md">AVStrMiniPinPower</a>  function that handles sleep requests for the device. Optional.


#### - Wake [in, optional]

This parameter supplies the address of a <a href="..\ks\nc-ks-pfnkspinpower.md">AVStrMiniPinPower</a>  function that handles wake requests for the device. Optional.


## -returns


None



## -remarks


<div class="alert"><b>Warning</b>  <i>Do not attempt to obtain the filter control mutex</i> from within either the Sleep or Wake callback, or deadlock may occur. For more information about mutexes, read <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.</div><div> </div>At least one of the callbacks must be specified when calling <b>KsPinRegisterPowerCallbacks</b>.



## -see-also

<a href="..\ks\nf-ks-ksfilterregisterpowercallbacks.md">KsFilterRegisterPowerCallbacks</a>

<a href="..\ks\nc-ks-pfnkspinpower.md">AVStrMiniPinPower</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinRegisterPowerCallbacks function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

