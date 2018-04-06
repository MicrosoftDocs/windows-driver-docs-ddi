---
UID: NS:iddcx.IDARG_OUT_MONITORARRIVAL
title: IDARG_OUT_MONITORARRIVAL
author: windows-driver-content
description: Gives information about the monitor that is exposed to the OS.
old-location: display\idarg_out_monitorarrival.htm
old-project: display
ms.assetid: 0e5c4b23-cb62-4320-9e55-d0da67b62aa1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IDARG_OUT_MONITORARRIVAL, IDARG_OUT_MONITORARRIVAL structure [Display Devices], display.idarg_out_monitorarrival, iddcx/IDARG_OUT_MONITORARRIVAL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
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
-	iddcx.h
api_name:
-	IDARG_OUT_MONITORARRIVAL
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_MONITORARRIVAL structure


## -description


Gives information about the monitor that is exposed to the OS.
             


## -struct-fields




### -field OsAdapterLuid


                     LUID of the adapter where this monitor is exposed to the OS
    . 

<div class="alert"><b>Note</b>  There are no API/DDI calls the driver can make with this information. Its only use is to pass it to companion applications so they can identify the monitor they control.</div>
<div> </div>

### -field OsTargetId


                     DMM VidPn target id of the target this monitor is exposed to the OS. 

<div class="alert"><b>Note</b>  There are no API/DDI calls the driver can make with this information. Its only use is to pass it to companion applications so they can identify the monitor they control.</div>
<div> </div>
<div class="alert"><b>Note</b>  Although this value is related to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt761950">IDDCX_MONITOR_INFO</a> value <b>ConnectorIndex</b> passed by the driver, the OS will perform internal mapping between the two that will change in future release. As such, the driver should not take any dependencies on this mapping and should use <b>OsAdapterLuid</b> &amp; <b>OsTargetId</b> instead.</div>
<div> </div>

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt761950">IDDCX_MONITOR_INFO</a>
 

 

