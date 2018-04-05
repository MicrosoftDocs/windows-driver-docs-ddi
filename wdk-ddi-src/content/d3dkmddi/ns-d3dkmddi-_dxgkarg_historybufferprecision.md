---
UID: NS:d3dkmddi._DXGKARG_HISTORYBUFFERPRECISION
title: "_DXGKARG_HISTORYBUFFERPRECISION"
author: windows-driver-content
description: Indicates info about the precision of history buffer data used by the display miniport driver.
old-location: display\dxgkarg_historybufferprecision.htm
old-project: display
ms.assetid: D55A8B5A-4133-4CE8-AD08-F551A3AEA42C
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKARG_HISTORYBUFFERPRECISION, DXGKARG_HISTORYBUFFERPRECISION structure [Display Devices], _DXGKARG_HISTORYBUFFERPRECISION, d3dkmddi/DXGKARG_HISTORYBUFFERPRECISION, display.dxgkarg_historybufferprecision
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGKARG_HISTORYBUFFERPRECISION
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_HISTORYBUFFERPRECISION
---

# _DXGKARG_HISTORYBUFFERPRECISION structure


## -description


Indicates info about the precision of history buffer data used by the display miniport driver.


## -struct-fields




### -field PrecisionBits

The number of valid bits that are used in each time stamp. This number doesn't include bits used for junk values.

This precision value has three valid ranges:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
No bits contain useful data, and the  DirectX graphics kernel subsystem will call the <a href="https://msdn.microsoft.com/84417629-5C12-4CB5-B147-0A558A4F9090">DxgkDdiFormatHistoryBuffer</a> function to provide valid data to output to the Event Tracing for Windows (ETW) facility. When the driver processes this call, it sets a new precision value as the output parameter of the function.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>32</dt>
</dl>
</td>
<td width="60%">
The driver should log 32-bit time stamps using the full 32 bits of precision.



</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>33–64</dt>
</dl>
</td>
<td width="60%">
The driver should log 64-bit time stamps. This value defines the number of bits used to store data per time stamp.

To reduce the cost of formatting the data, the driver can include junk values in the 64-bit time stamps. For example, the driver could write 64-bit time stamps with 55 valid bits of precision. In this case the upper 9 bits are considered junk values and are stripped off by ETW.

</td>
</tr>
</table>
 

Values between 0 and 32 are unsupported and invalid.

If the hardware supports 64-bit time stamps but only 32 bits are usable, the driver must ensure that the data is presented correctly to the DirectX graphics kernel subsystem. If the driver has no other alternatives to present the data, it should provide the precision value when the <a href="https://msdn.microsoft.com/84417629-5C12-4CB5-B147-0A558A4F9090">DxgkDdiFormatHistoryBuffer</a> function is next called.


## -remarks



In a call to the <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function, the output data size,  <a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>.<b>OutputDataSize</b>, is:

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>sizeof(DXGKARG_HISTORYBUFFERPRECISION) * m_DriverCaps.GpuEngineTopology.NbAsymetricProcessingNodes</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/84417629-5C12-4CB5-B147-0A558A4F9090">DxgkDdiFormatHistoryBuffer</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>
 

 

