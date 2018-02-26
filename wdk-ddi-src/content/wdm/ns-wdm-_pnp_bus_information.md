---
UID: NS:wdm._PNP_BUS_INFORMATION
title: "_PNP_BUS_INFORMATION"
author: windows-driver-content
description: The PNP_BUS_INFORMATION structure describes a bus.
old-location: kernel\pnp_bus_information.htm
old-project: kernel
ms.assetid: 68372562-9af0-431d-90ae-c82678d9103e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PPNP_BUS_INFORMATION, ,, A, B, F, I, M, N, O, P, PNP_BUS_INFORMATION, PNP_BUS_INFORMATION structure [Kernel-Mode Driver Architecture], PPNP_BUS_INFORMATION, PPNP_BUS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], R, S, T, U, _, _PNP_BUS_INFORMATION, kernel.pnp_bus_information, kstruct_c_a62e40f6-081a-4d2e-859b-28c98c2216f3.xml, wdm/PNP_BUS_INFORMATION, wdm/PPNP_BUS_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	PNP_BUS_INFORMATION
product: Windows
targetos: Windows
req.typenames: PNP_BUS_INFORMATION, *PPNP_BUS_INFORMATION
req.product: Windows 10 or later.
---

# _PNP_BUS_INFORMATION structure


## -description


The <b>PNP_BUS_INFORMATION</b> structure describes a bus.


## -syntax


````
typedef struct _PNP_BUS_INFORMATION {
  GUID           BusTypeGuid;
  INTERFACE_TYPE LegacyBusType;
  INTERFACE_TYPE LegacyBusType;
  ULONG          BusNumber;
} PNP_BUS_INFORMATION, *PPNP_BUS_INFORMATION;
````


## -struct-fields




### -field BusTypeGuid


### -field LegacyBusType


### -field BusNumber


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551654">IRP_MN_QUERY_BUS_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PNP_BUS_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

