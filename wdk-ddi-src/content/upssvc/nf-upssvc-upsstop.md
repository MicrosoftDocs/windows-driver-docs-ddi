---
UID: NF:upssvc.UPSStop
title: UPSStop function (upssvc.h)
description: The UPSStop function causes a UPS minidriver to stop monitoring its UPS unit.
old-location: battery\upsstop.htm
tech.root: battery
ms.date: 02/15/2018
keywords: ["UPSStop function"]
ms.keywords: UPSStop, UPSStop function [Battery Devices], UPS_fns_60f920b5-6225-4569-a60a-dfb1c6b2538c.xml, battery.upsstop, upssvc/UPSStop
req.header: upssvc.h
req.include-header: Upssvc.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - UPSStop
 - upssvc/UPSStop
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Upssvc.h
api_name:
 - UPSStop
---

# UPSStop function


## -description

The <b>UPSStop</b> function causes a UPS minidriver to stop monitoring its UPS unit.

## -remarks

The <b>UPSStop</b> function must:

<ul>
<li>
Cancel all waiting calls to <a href="/windows-hardware/drivers/ddi/upssvc/nf-upssvc-upswaitforstatechange">UPSWaitForStateChange</a>.

</li>
<li>
Stop monitoring the UPS unit.

</li>
<li>
Close and release the UPS unit's COM port.

</li>
</ul>
After <b>UPSStop</b> returns, the only function the UPS service can call is <a href="/windows-hardware/drivers/ddi/upssvc/nf-upssvc-upsinit">UPSInit</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/upssvc/nf-upssvc-upsinit">UPSInit</a>
