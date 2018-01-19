---
UID: NE:rilapitypes.RILUICCAPPTYPE
title: RILUICCAPPTYPE
author: windows-driver-content
description: This enumeration describes the RILUICCAPPTYPE.
old-location: netvista\riluiccapptype.htm
old-project: netvista
ms.assetid: cba1fcc3-74d0-44b7-b480-3e7d754f9efe
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCAPPTYPE, RILUICCAPPTYPE
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
req.alt-api: RILUICCAPPTYPE
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
req.typenames: RILUICCAPPTYPE
req.product: Windows 10 or later.
---

# RILUICCAPPTYPE enumeration



## -description

## -syntax

````
enum RILUICCAPPTYPE {
  RIL_UICCAPPTYPE_UNKNOWN  = 0x00000001, 
  RIL_UICCAPPTYPE_MF       = 0x00000002, 
  RIL_UICCAPPTYPE_MF_SIM   = 0x00000003, 
  RIL_UICCAPPTYPE_MF_RUIM  = 0x00000004, 
  RIL_UICCAPPTYPE_USIM     = 0x00000005, 
  RIL_UICCAPPTYPE_CSIM     = 0x00000006, 
  RIL_UICCAPPTYPE_ISIM     = 0x00000007 

};
````


## -enum-fields

### -field RIL_UICCAPPTYPE_UNKNOWN


### -field RIL_UICCAPPTYPE_MF


### -field RIL_UICCAPPTYPE_MF_SIM


### -field RIL_UICCAPPTYPE_MF_RUIM


### -field RIL_UICCAPPTYPE_USIM


### -field RIL_UICCAPPTYPE_CSIM


### -field RIL_UICCAPPTYPE_ISIM


## -remarks
Networks will vary, but the following table summarizes which items are returned for typical TD-SCDMA networks. 

<b>Serving network</b>

MobileCountryCode

Yes

0 through 999



MobileNetworkCode

LocationAreaCode

0 to 65535

CellID

0 through 268,435,455

May not always be available; 28 bits

UARFCN

0 through 16,383

Channel number

CellParameterID

0 through 127

TimingAdvance

0 through 8,191

By standards, the maximum range is 96 chips (0 to 96x8)

RSCP

−25 through −128

Received signal code power of serving cell in dBm  

PathLoss

No

46 through 158

Path loss of serving cell in dBs  

<b>TD-SCDMA neighbors</b> (subject to availability from network)


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCAPPTYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

