---
UID: NC:ks.PFNKSPINPOWER
title: PFNKSPINPOWER
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniPinPower routine is called for pin-centric pins when the device is waking or entering a sleep state.
old-location: stream\avstrminipinpower.htm
old-project: stream
ms.assetid: 6362ca08-cf8d-4e54-b144-10b2252f05c5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: NpdBrokerUninitialize
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
req.alt-api: AVStrMiniPinPower
req.alt-loc: ks.h
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
req.typenames: KEYWORDSELECTOR
---

# PFNKSPINPOWER callback



## -description
An AVStream minidriver's <i>AVStrMiniPinPower</i> routine is called for pin-centric pins when the device is waking or entering a sleep state.



## -prototype

````
PFNKSPINPOWER AVStrMiniPinPower;

void AVStrMiniPinPower(
  _In_ PKSPIN             Pin,
  _In_ DEVICE_POWER_STATE State
)
{ ... }
````


## -parameters

### -param Pin [in]

Points to a pin-centric <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which to register the callback.


### -param State [in]

Specifies the device power state being requested. Set this parameter to one of the following DEVICE_POWER_STATE enumeration values: <b>PowerDeviceD0</b>, <b>PowerDeviceD1</b>, <b>PowerDeviceD2</b>, or <b>PowerDeviceD3</b>.


## -returns
None


## -remarks
The minidriver specifies an address for routines of this type in the <i>Sleep </i>and/or <i>Wake </i>parameters of the <a href="..\ks\nf-ks-kspinregisterpowercallbacks.md">KsPinRegisterPowerCallbacks</a> routine.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-kspinregisterpowercallbacks.md">KsPinRegisterPowerCallbacks</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfilterregisterpowercallbacks.md">KsFilterRegisterPowerCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSPINPOWER routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

