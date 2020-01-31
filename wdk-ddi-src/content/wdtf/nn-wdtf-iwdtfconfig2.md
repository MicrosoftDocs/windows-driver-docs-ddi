---
UID: NN:wdtf.IWDTFCONFIG2
title: IWDTFCONFIG2 (wdtf.h)
description: Defines operations that control WDTF objects within a test script.
old-location: dtf\iwdtfconfig2.htm
tech.root: dtf
ms.assetid: 7cc3775e-d116-4852-9b1a-606d909d878b
ms.date: 04/04/2018
ms.keywords: IWDTFCONFIG2, IWDTFCONFIG2 interface [Windows Device Testing Framework], IWDTFCONFIG2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFCONFIG2, dtf.iwdtfconfig2, wdtf/IWDTFCONFIG2
f1_keywords:
 - "wdtf/IWDTFCONFIG2"
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTF.Interop.metadata_dll.dll
api_name:
- IWDTFCONFIG2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFCONFIG2 interface


## -description


Defines operations that control <b>WDTF</b> objects within a test script.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFCONFIG2</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IWDTFCONFIG2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



<b>WDTF</b> object logging defaults to disabled. If object logging is enabled, 
each <b>WDTF</b> object writes to the test scripts log. If object logging is enabled, 
object error logging is enabled by default.

The following example shows the logging output for a call to 
<b>DeviceDepot.Query("Volume::")</b> when logging is enabled for an example system.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
[ Ouput ]

WDTF_TARGETS    : INFO  :  - Query("Volume::")
WDTF_TARGETS    : INFO  :          Target: Generic volume
WDTF_TARGETS    : INFO  :          Target: Generic volume
WDTF_TARGETS    : INFO  :          Target: HL-DT-ST RW/DVD MU10N ATA Device
WDTF_TARGETS    : INFO  :          Target: Generic volume
WDTF_TARGETS    : INFO  :          Target: Generic volume
WDTF_TARGETS    : INFO  :          Target: Generic volume
</pre>
</td>
</tr>
</table></span></div>


