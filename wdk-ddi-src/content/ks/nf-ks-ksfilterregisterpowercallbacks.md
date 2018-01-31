---
UID: NF:ks.KsFilterRegisterPowerCallbacks
title: KsFilterRegisterPowerCallbacks function
author: windows-driver-content
description: The KsFilterRegisterPowerCallbacks function registers power management callbacks for Filter.
old-location: stream\ksfilterregisterpowercallbacks.htm
old-project: stream
ms.assetid: 9b4a7932-7371-48d2-95fb-1c3e3ca170be
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksfilterregisterpowercallbacks, avfunc_7c5322b7-f7e2-4641-b466-06f5d9ebfc34.xml, KsFilterRegisterPowerCallbacks function [Streaming Media Devices], KsFilterRegisterPowerCallbacks, ks/KsFilterRegisterPowerCallbacks
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
-	KsFilterRegisterPowerCallbacks
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterRegisterPowerCallbacks function


## -description


The<b> KsFilterRegisterPowerCallbacks </b>function registers power management callbacks for <i>Filter</i>.


## -syntax


````
void KsFilterRegisterPowerCallbacks(
  _In_     PKSFILTER        Filter,
  _In_opt_ PFNKSFILTERPOWER Sleep,
  _In_opt_ PFNKSFILTERPOWER Wake
);
````


## -parameters




#### - Filter [in]

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure for which to register power callbacks. In order to receive power notification messages, <i>Filter</i> must be filter-centric.


#### - Sleep [in, optional]

A pointer to a function that handles sleep requests for the device. If <b>NULL</b>, no sleep callback is registered. For more information, see the Remarks section below.


#### - Wake [in, optional]

A pointer to a function that handles wake requests for the device. If <b>NULL</b>, no wake callback is specified. For more information, see the Remarks section below.


## -returns


None



## -remarks


<div class="alert"><b>Warning</b>  <i>Do not attempt to obtain the filter control mutex</i> from within either the Sleep or Wake callback, or deadlock may occur. For more information about mutexes, read <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.</div><div> </div>The two callbacks should be prototyped as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void Sleep/Wake (IN PKSFILTER Filter, IN DEVICE_POWER_STATE State);</pre>
</td>
</tr>
</table></span></div>The <i>Sleep</i> callback is made if <i>Filter</i> is a filter-centric filter and the device is going to sleep. The <i>Wake</i> callback is made if <i>Filter</i> is a filter-centric filter and the device is waking.

For information about device power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543162">Device Power States</a>. 

Also see <a href="https://msdn.microsoft.com/666d6efb-93ec-43f3-87c5-ea1a3983bfd0">Initializing an AVStream Minidriver</a> and <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.



## -see-also

<a href="..\ks\nf-ks-kspinregisterpowercallbacks.md">KsPinRegisterPowerCallbacks</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterRegisterPowerCallbacks function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

