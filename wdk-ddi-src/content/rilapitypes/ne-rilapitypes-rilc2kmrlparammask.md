---
UID: NE:rilapitypes.RILC2KMRLPARAMMASK
title: RILC2KMRLPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILC2KMRLPARAMMASK.
old-location: netvista\rilc2kmrlparammask.htm
old-project: netvista
ms.assetid: 145300be-6db8-48fd-9b8a-3b6d8532a1b1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILC2KMRLPARAMMASK, RILC2KMRLPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILC2KMRLPARAMMASK
req.alt-loc: rilapitypes.h
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
req.typenames: RILC2KMRLPARAMMASK
req.product: Windows 10 or later.
---

# RILC2KMRLPARAMMASK enumeration



## -description

## -syntax

````
enum RILC2KMRLPARAMMASK {
  RIL_PARAM_C2KMRL_SERVING        = 0x00000001, 
  RIL_PARAM_C2KMRL_NID            = 0x00000002, 
  RIL_PARAM_C2KMRL_SID            = 0x00000004, 
  RIL_PARAM_C2KMRL_BSID           = 0x00000008, 
  RIL_PARAM_C2KMRL_BASELAT        = 0x00000010 , 
  RIL_PARAM_C2KMRL_BASELONG       = 0x00000020 , 
  RIL_PARAM_C2KMRL_REFPN          = 0x00000040 , 
  RIL_PARAM_C2KMRL_GPSSECONDS     = 0x00000080 , 
  RIL_PARAM_C2KMRL_PILOTSTRENGTH  = 0x000000100, 
  RIL_PARAM_C2KRML_ALL            = 0x000001ff  

};
````


## -enum-fields

### -field RIL_PARAM_C2KMRL_SERVING


### -field RIL_PARAM_C2KMRL_NID


### -field RIL_PARAM_C2KMRL_SID


### -field RIL_PARAM_C2KMRL_BSID


### -field RIL_PARAM_C2KMRL_BASELAT


### -field RIL_PARAM_C2KMRL_BASELONG


### -field RIL_PARAM_C2KMRL_REFPN


### -field RIL_PARAM_C2KMRL_GPSSECONDS


### -field RIL_PARAM_C2KMRL_PILOTSTRENGTH


### -field RIL_PARAM_C2KRML_ALL


## -remarks
Networks will vary, but the following table summarizes which items are returned for typical CDMA networks.

<b>Serving and neighbor networks</b> (subject to availability from network)

Serving

Yes

0 through 1

1 = serving; 0 = non-serving

NID

0 through 32,767

15 bits

SID

0 through 65,535

16 bits

BaseStationID

BaseLat

0 through 4,194,303

Base station latitude in units of 0.25 sec, expressed as a two's-complement signed number with positive numbers signifying north latitudes; 22 bits

BaseLong

0 through 8,388,607

Base station longitude in units of 0.25 sec, expressed as a two's-complement signed number with positive numbers signifying east longitude; 23 bits

RefPN

0 through 511

9 bits

GPSSeconds



CDMA system time from the "sync channel" when this set was acquired

PilotStrength

0 through 63


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILC2KMRLPARAMMASK enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

