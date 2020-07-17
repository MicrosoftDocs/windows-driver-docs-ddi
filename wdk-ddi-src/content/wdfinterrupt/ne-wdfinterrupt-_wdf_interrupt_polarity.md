---
UID: NE:wdfinterrupt._WDF_INTERRUPT_POLARITY
title: _WDF_INTERRUPT_POLARITY (wdfinterrupt.h)
description: The WDF_INTERRUPT_POLARITY enumeration type is used to specify an interrupt signal's polarity.
old-location: wdf\wdf_interrupt_polarity.htm
tech.root: wdf
ms.assetid: 6621a1ec-1d4e-4801-9418-d09a0073686a
ms.date: 02/26/2018
keywords: ["_WDF_INTERRUPT_POLARITY enumeration"]
ms.keywords: "*PWDF_INTERRUPT_POLARITY, DFInterruptObjectRef_979c7766-edd8-421b-8885-8000d60da78d.xml, PWDF_INTERRUPT_POLARITY, PWDF_INTERRUPT_POLARITY enumeration pointer, WDF_INTERRUPT_POLARITY, WDF_INTERRUPT_POLARITY enumeration, WdfInterruptActiveHigh, WdfInterruptActiveLow, WdfInterruptPolarityUnknown, _WDF_INTERRUPT_POLARITY, kmdf.wdf_interrupt_polarity, wdf.wdf_interrupt_polarity, wdfinterrupt/PWDF_INTERRUPT_POLARITY, wdfinterrupt/WDF_INTERRUPT_POLARITY, wdfinterrupt/WdfInterruptActiveHigh, wdfinterrupt/WdfInterruptActiveLow, wdfinterrupt/WdfInterruptPolarityUnknown"
f1_keywords:
 - "wdfinterrupt/WDF_INTERRUPT_POLARITY"
 - "WDF_INTERRUPT_POLARITY"
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfinterrupt.h
api_name:
- WDF_INTERRUPT_POLARITY
product:
- Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_POLARITY, *PWDF_INTERRUPT_POLARITY
---

# _WDF_INTERRUPT_POLARITY enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_INTERRUPT_POLARITY</b> enumeration type is used to specify an interrupt signal's polarity.


## -enum-fields




### -field WdfInterruptPolarityUnknown

The interrupt signal's polarity is unknown.


### -field WdfInterruptActiveHigh

The interrupt signal is active when it is high.


### -field WdfInterruptActiveLow

The interrupt signal is active when it is low.


## -remarks



The <b>WDF_INTERRUPT_POLARITY</b> enumeration type is used to specify a member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_info">WDF_INTERRUPT_INFO</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_info">WDF_INTERRUPT_INFO</a>
 

 

