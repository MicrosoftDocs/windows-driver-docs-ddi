---
UID: NE:wwan._WWAN_PCO_TYPE
title: _WWAN_PCO_TYPE (wwan.h)
description: The WWAN_PCO_TYPE enumeration indicates whether the header of a PCO structure is partial, meaning only a subset of the complete PCO value from the network is being passed up to the host.
old-location: netvista\wwan_pco_type.htm
tech.root: netvista
ms.assetid: 0AD10F14-EBDB-45F8-A435-1D0A6D6FEFFF
ms.date: 05/02/2018
keywords: ["WWAN_PCO_TYPE enumeration"]
ms.keywords: "*PWWAN_PCO_TYPE, WWAN_PCO_TYPE, WWAN_PCO_TYPE enumeration [Network Drivers Starting with Windows Vista], WwanPcoTypeComplete, WwanPcoTypePartial, _WWAN_PCO_TYPE, netvista.wwan_pco_type, wwan/WWAN_PCO_TYPE, wwan/WwanPcoTypeComplete, wwan/WwanPcoTypePartial"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
targetos: Windows
req.typenames: WWAN_PCO_TYPE, *PWWAN_PCO_TYPE
f1_keywords:
 - _WWAN_PCO_TYPE
 - wwan/_WWAN_PCO_TYPE
 - PWWAN_PCO_TYPE
 - wwan/PWWAN_PCO_TYPE
 - WWAN_PCO_TYPE
 - wwan/WWAN_PCO_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_PCO_TYPE
---

# _WWAN_PCO_TYPE enumeration


## -description

The <b>WWAN_PCO_TYPE</b> enumeration indicates whether the header of a PCO structure is partial, meaning only a subset of the complete PCO value from the network is being passed up to the host. This type will help the upper edge logic know the validity of the header of the PCO structure.

## -enum-fields

### -field WwanPcoTypeComplete

Specifies that the complete PCO structure will be passed up as received from the network and the header realistically reflects the protocol in octet 3 of the PCO structure, defined in the 3GPP TS24.008 spec. To see the full PCO structure, see <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pco_value">WWAN_PCO_VALUE</a>.

### -field WwanPcoTypePartial

Specifies that the modem will only be passing up a subset of PCO structures that it received from the network. The header matches the 3GPP TS24.008 specification for the PCO structure, as shown on <b>WWAN_PCO_VALUE</b>, but the “Configuration protocol” of octet 3 may not be valid.

### -field WwanPcoTypeMax

The maximum value for this enumeration.

## -remarks

Currently, in Windows 10, version 1709, some modems can only pass up operator specific PCO elements. These will have the type is set as <b>WwanPcoTypePartial</b>, and the header should have the following:

<ul>
<li>Octet1: IEI = 27H</li>
<li>Octet2: PCO value length (total number of octets in the PCO structure -2)</li>
<li>Octet3: 0x80 for partial header </li>
</ul>
The OS will not check if the PCO data is valid and leaves the validation to the MO application.

## -see-also

<a href="/windows-hardware/drivers/network/mb-protocol-configuration-options-pco-operations">MB Protocol Configuration Options (PCO) operations</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pco_value">WWAN_PCO_VALUE</a>