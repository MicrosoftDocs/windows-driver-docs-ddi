---
UID: NC:d3d10umddi.PFND3D10DDI_CHECKCOUNTER
title: PFND3D10DDI_CHECKCOUNTER
author: windows-driver-content
description: The CheckCounter function retrieves information that describes a counter.
old-location: display\checkcounter.htm
old-project: display
ms.assetid: 592a5146-a2fe-41d1-854b-df27a97bd513
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CheckCounter, CheckCounter callback function [Display Devices], PFND3D10DDI_CHECKCOUNTER, UserModeDisplayDriverDx10_Functions_450a0976-fc56-4a5a-8a01-9c9d1041b628.xml, d3d10umddi/CheckCounter, display.checkcounter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CheckCounter
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CHECKCOUNTER callback


## -description


The <b>CheckCounter</b> function retrieves information that describes a counter. 


## -parameters




### -param Arg1


### -param Arg2


### -param *


### -param Arg3


### -param *pNameLength [in, out]

A pointer to a variable that receives the size, in bytes, of the NULL-terminated string that the <i>pName</i> parameter specifies.  


### -param Arg4


### -param *pUnitsLength [in, out]

 A pointer to a variable that receives the size, in bytes, of the NULL-terminated string that the <i>pUnits</i> parameter specifies. 


### -param Arg5


### -param *pDescriptionLength [in, out]

 A pointer to a variable that receives the size, in bytes, of the NULL-terminated string that the <i>pDescription</i> parameter specifies. 


#### - Query [in]

 A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541850">D3D10DDI_QUERY</a>-typed value that identifies the counter identifier that information is retrieved for.


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pActiveCounters [out]

A pointer to a variable that receives the number of simultaneously active counters that are allocated for the creation of the counter identifier that <i>Query</i> identifies. 


#### - pCounterType [out]

A pointer to a variable that receives one of the following values from the D3D10DDI_COUNTER_TYPE enumeration that identifies the data type that the counter outputs. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D10DDI_COUNTER_TYPE_FLOAT32

</td>
<td>
Single-precision float

</td>
</tr>
<tr>
<td>
D3D10DDI_COUNTER_TYPE_UINT16

</td>
<td>
16-bit value

</td>
</tr>
<tr>
<td>
D3D10DDI_COUNTER_TYPE_UINT32

</td>
<td>
32-bit value

</td>
</tr>
<tr>
<td>
D3D10DDI_COUNTER_TYPE_UINT64

</td>
<td>
64-bit value

</td>
</tr>
</table>
 


#### - pDescription [out]

A pointer that the driver returns a NULL-terminated string to that contains the description of what the counter identifier measures. 


#### - pName [out]

A pointer that the driver returns a NULL-terminated string to that contains the name of the counter identifier. 


#### - pUnits [out]

A pointer that the driver returns a NULL-terminated string to that contains the name of the units that the counter identifier measures. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver's <b>CheckCounter</b> function can call the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set the ERR_UNSUPPORTED error code if the <i>Query</i> parameter of <b>CheckCounter</b>specifies a well-known counter that the device does not support.

The driver must validate a device-dependent counter identifier to ensure the identifier is within range. The driver must also ensure that enough space exists to copy each counter string into each buffer that the Microsoft Direct3D runtime provides. The driver can call the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set the E_INVALIDARG error code if there is not enough space for any of the provided buffers.

The driver's <b>CheckCounter</b> function cannot call the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set the D3DDDIERR_DEVICEREMOVED error code because <b>CheckCounter</b> is a capability-check type of function. The driver must ensure that it has enough information after device creation to respond to a call to <b>CheckCounter</b>, even in the presence of D3DDDIERR_DEVICEREMOVED. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541850">D3D10DDI_QUERY</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

