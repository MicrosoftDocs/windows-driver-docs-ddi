---
UID: NF:upssvc.UPSStop
title: UPSStop function
author: windows-driver-content
description: The UPSStop function causes a UPS minidriver to stop monitoring its UPS unit.
old-location: battery\upsstop.htm
old-project: battery
ms.assetid: 55555e58-eaba-4c39-a771-9924da3fcfc4
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: UPSStop, UPSStop function [Battery Devices], UPS_fns_60f920b5-6225-4569-a60a-dfb1c6b2538c.xml, battery.upsstop, upssvc/UPSStop
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Upssvc.h
api_name:
-	UPSStop
product:
- Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# UPSStop function


## -description


The <b>UPSStop</b> function causes a UPS minidriver to stop monitoring its UPS unit.


## -parameters








## -returns



None




## -remarks



The <b>UPSStop</b> function must:

<ul>
<li>
Cancel all waiting calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536316">UPSWaitForStateChange</a>.

</li>
<li>
Stop monitoring the UPS unit.

</li>
<li>
Close and release the UPS unit's COM port.

</li>
</ul>
After <b>UPSStop</b> returns, the only function the UPS service can call is <a href="https://msdn.microsoft.com/library/windows/hardware/ff536313">UPSInit</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536313">UPSInit</a>
 

 

