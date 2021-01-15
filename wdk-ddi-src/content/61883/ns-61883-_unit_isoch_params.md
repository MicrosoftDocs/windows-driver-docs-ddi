---
UID: NS:61883._UNIT_ISOCH_PARAMS
title: _UNIT_ISOCH_PARAMS (61883.h)
description: The UNIT_ISOCH_PARAMS structure is used to get or set the parameters that the IEC-61883 protocol driver uses when capturing or transmitting isochronous packets.
old-location: ieee\unit_isoch_params.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["UNIT_ISOCH_PARAMS structure"]
ms.keywords: "*PUNIT_ISOCH_PARAMS, 61883/PUNIT_ISOCH_PARAMS, 61883/UNIT_ISOCH_PARAMS, 61883_structures_eece3eb1-516b-40a8-9529-e4a3d8832f02.xml, IEEE.unit_isoch_params, PUNIT_ISOCH_PARAMS, PUNIT_ISOCH_PARAMS structure pointer [Buses], UNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS structure [Buses], _UNIT_ISOCH_PARAMS"
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
f1_keywords:
 - _UNIT_ISOCH_PARAMS
 - 61883/_UNIT_ISOCH_PARAMS
 - PUNIT_ISOCH_PARAMS
 - 61883/PUNIT_ISOCH_PARAMS
 - UNIT_ISOCH_PARAMS
 - 61883/UNIT_ISOCH_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 61883.h
api_name:
 - _UNIT_ISOCH_PARAMS
 - PUNIT_ISOCH_PARAMS
 - UNIT_ISOCH_PARAMS
---

# _UNIT_ISOCH_PARAMS structure


## -description

The UNIT_ISOCH_PARAMS structure is used to get or set the parameters that the IEC-61883 protocol driver uses when capturing or transmitting isochronous packets.

## -struct-fields

### -field RX_NumPackets

The number of isochronous packets per descriptor to be received.

### -field RX_NumDescriptors

The number of descriptors used for receiving isochronous data.

### -field TX_NumPackets

The number of isochronous packets per descriptor to be transmitted.

### -field TX_NumDescriptors

The number of descriptors used for transmitting isochronous data.

## -remarks

The UNIT_ISOCH_PARAMS structure can be used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a> to set the number of isochronous packets and descriptors used while transmitting or receiving data. Before setting isochronous parameters, a driver should send an <a href="/previous-versions/ff536983(v=vs.85)">Av61883_GetUnitInfo</a> request to retrieve the current isochronous parameters and then make any necessary modifications with <b>Av61883_SetUnitInfo</b>.

## -see-also

<a href="/previous-versions/ff536983(v=vs.85)">Av61883_GetUnitInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a>

