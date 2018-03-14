---
UID: NS:61883._UNIT_ISOCH_PARAMS
title: "_UNIT_ISOCH_PARAMS"
author: windows-driver-content
description: The UNIT_ISOCH_PARAMS structure is used to get or set the parameters that the IEC-61883 protocol driver uses when capturing or transmitting isochronous packets.
old-location: ieee\unit_isoch_params.htm
old-project: IEEE
ms.assetid: 1c661a35-8209-49c5-9987-b4b6e9e710b4
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PUNIT_ISOCH_PARAMS, 61883/PUNIT_ISOCH_PARAMS, 61883/UNIT_ISOCH_PARAMS, 61883_structures_eece3eb1-516b-40a8-9529-e4a3d8832f02.xml, IEEE.unit_isoch_params, PUNIT_ISOCH_PARAMS, PUNIT_ISOCH_PARAMS structure pointer [Buses], UNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS structure [Buses], _UNIT_ISOCH_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	UNIT_ISOCH_PARAMS
product: Windows
targetos: Windows
req.typenames: UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
---

# _UNIT_ISOCH_PARAMS structure


## -description


The UNIT_ISOCH_PARAMS structure is used to get or set the parameters that the IEC-61883 protocol driver uses when capturing or transmitting isochronous packets.


## -syntax


````
typedef struct _UNIT_ISOCH_PARAMS {
  ULONG RX_NumPackets;
  ULONG RX_NumDescriptors;
  ULONG TX_NumPackets;
  ULONG TX_NumDescriptors;
} UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS;
````


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



The UNIT_ISOCH_PARAMS structure can be used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a> to set the number of isochronous packets and descriptors used while transmitting or receiving data. Before setting isochronous parameters, a driver should send an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a> request to retrieve the current isochronous parameters and then make any necessary modifications with <b>Av61883_SetUnitInfo</b>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a>



 

 


