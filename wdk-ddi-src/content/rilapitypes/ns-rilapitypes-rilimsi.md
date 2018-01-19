---
UID: NS:rilapitypes.RILIMSI
title: RILIMSI
author: windows-driver-content
description: This structure represents a RILIMSI.
old-location: netvista\rilimsi.htm
old-project: netvista
ms.assetid: e2dc6a60-b3a6-4b2a-8a6c-aa513ca9b87b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILIMSI, RILIMSI, *LPRILIMSI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILIMSI
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
req.typenames: RILIMSI, *LPRILIMSI
req.product: Windows 10 or later.
---

# RILIMSI structure



## -description

## -syntax

````
struct RILIMSI {
  DWORD cbSize;
  DWORD dwParams;
  WCHAR wszImsi[MAXLENGTH_IMSI];
  DWORD dwMcc;
  DWORD dwMnc;
};
````


## -struct-fields

### -field cbSize

The size of the structure in bytes.


### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilimsiparammask.md">RILIMSIPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field wszImsi

The IMSI as a null-terminated Unicode string.


### -field dwMcc

The mobile country code from the IMSI.


### -field dwMnc

The mobile network code from the IMSI.


## -remarks
The RIL driver is responsible for determining whether the MNC comprises two or three digits and extracting it accordingly. (For 3GPP, the number of digits in the MNC is specified by the fourth byte of EFAD as specified in 3GPP TS 31.102 section 4.2.18.)

For 3GPP2, the IMSI_T is returned if it is programmed; otherwise, the IMSI_M is returned. For the IMSI_T, dwMcc contains the MCC_Tp and dwMnc contains IMSI_T_11_12p. For the IMSI_M, dwMcc contains the MCC_Mp and dwMnc is not defined (that is, the RIL_PARAM_IMSI_MNC bit in dwParams is 0).


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILIMSI structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

