---
UID: NE:rilapitypes.RILEUTRAMRLPARAMMASK
title: RILEUTRAMRLPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILEUTRAMRLPARAMMASK.
old-location: netvista\rileutramrlparammask.htm
old-project: netvista
ms.assetid: 555dd967-ea38-45fa-8e7f-5318ca5c6dd2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILEUTRAMRLPARAMMASK, RILEUTRAMRLPARAMMASK
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
req.alt-api: RILEUTRAMRLPARAMMASK
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
req.typenames: RILEUTRAMRLPARAMMASK
req.product: Windows 10 or later.
---

# RILEUTRAMRLPARAMMASK enumeration



## -description

## -syntax

````
enum RILEUTRAMRLPARAMMASK {
  RIL_PARAM_EUTRAMRL_MCC         = 0x00000001, 
  RIL_PARAM_EUTRAMRL_MNC         = 0x00000002, 
  RIL_PARAM_EUTRAMRL_CELLID      = 0x00000004, 
  RIL_PARAM_EUTRAMRL_EARFCN      = 0x00000008, 
  RIL_PARAM_EUTRAMRL_PHYSCELLID  = 0x00000010, 
  RIL_PARAM_EUTRAMRL_TAC         = 0x00000020, 
  RIL_PARAM_EUTRAMRL_RSRP        = 0x00000040, 
  RIL_PARAM_EUTRAMRL_RSRQ        = 0x00000080, 
  RIL_PARAM_EUTRAMRL_ALL         = 0x000000ff 

};
````


## -enum-fields

### -field RIL_PARAM_EUTRAMRL_MCC


### -field RIL_PARAM_EUTRAMRL_MNC


### -field RIL_PARAM_EUTRAMRL_CELLID


### -field RIL_PARAM_EUTRAMRL_EARFCN


### -field RIL_PARAM_EUTRAMRL_PHYSCELLID


### -field RIL_PARAM_EUTRAMRL_TAC


### -field RIL_PARAM_EUTRAMRL_RSRP


### -field RIL_PARAM_EUTRAMRL_RSRQ


### -field RIL_PARAM_EUTRAMRL_ALL


## -remarks
Networks will vary, but the following table summarizes which items are returned for typical LTE networks. 

<b>Serving network</b>

MobileCountryCode

Yes

0 through 999



MobileNetworkCode

CellID

0 through 268,435,455

Global cell ID in the system information block; 28 bits

EARFCN

0 through 65,535

E-UTRA absolute radio frequency channel number of the serving cell 

PhysCellID

0 through 503

LTE serving cell ID 

TAC

RSRP

−44 through −140

The current reference signal receive power in dBm  

RSRQ

−3 through −20

Measured in dB  

<b>LTE neighbors</b> (subject to availability from network)

No

E-UTRA absolute radio frequency channel number of the serving cell

The current reference signal receive power in dBm

Measured in dB


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILEUTRAMRLPARAMMASK enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

