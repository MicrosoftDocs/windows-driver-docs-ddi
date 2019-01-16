---
UID: NC:d3dumddi.PFND3DDDI_CHECKCOUNTER
title: PFND3DDDI_CHECKCOUNTER
description: Called by the Microsoft Direct3D runtime to retrieve info that describes a counter. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfncheckcounter.htm
tech.root: display
ms.assetid: 3A8B040D-7B48-4CDB-985B-906AE1762E22
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_CHECKCOUNTER, PFND3DDDI_CHECKCOUNTER callback, d3dumddi/pfnCheckCounter, display.pfncheckcounter, pfnCheckCounter, pfnCheckCounter callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dumddi.h
api_name:
-	pfnCheckCounter
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CHECKCOUNTER callback function


## -description


Called by the Microsoft Direct3D runtime to retrieve info that describes a counter. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -parameters




### -param hDevice 

[in] A handle to the display device (graphics context).


### -param Arg1

*Counter* [in]

A value of type <a href="https://msdn.microsoft.com/f80224c6-9046-4471-b6c6-eb14f02fc51f">D3DDDIQUERYTYPE</a> that identifies the counter identifier that info is retrieved for.

### -param *

*pType* [out]

A pointer to a variable that receives one of the following values from the <b>D3DDDI_COUNTER_TYPE</b> enumeration that identifies the data type that the counter outputs.

|Value|Meaning|
|:--|:--|
|D3DDDI_COUNTER_TYPE_FLOAT32|Single-precision float|
|D3DDDI_COUNTER_TYPE_UINT16|16-bit value|
|D3DDDI_COUNTER_TYPE_UINT32|32-bit value|
|D3DDDI_COUNTER_TYPE_UINT64|64-bit value|

### -param *

*pActiveCounters* [out]

A pointer to a variable that receives the number of simultaneously active counters that are allocated for the creation of the counter identifier that the <i>Counter</i> parameter identifies.

### -param Arg2

*pszName* [out, optional]

An optional pointer that the driver returns a <b>NULL</b>-terminated string to that contains the name of the counter identifier.

Can be <b>NULL</b>, in which case the app doesn't need the name.

### -param *pNameLength [in, out, optional]

An optional pointer to a variable that receives the size, in bytes, of the <b>NULL</b>-terminated string that the <i>pszName</i> parameter specifies.

Here are limitations on the values of the <i>pNameLength</i> and  <i>pszName</i> parameters:

<ul>
<li><i>pNameLength</i> can be <b>NULL</b>, in which case the app doesn't need the name or name length.</li>
<li> If <i>pszName</i> is <b>NULL</b> and <i>pNameLength</i> is not <b>NULL</b>, the input value of <i>pNameLength</i> is ignored, and the length of the string (including terminating <b>NULL</b> character) must be returned through the <i>pNameLength</i> parameter. </li>
<li>If both <i>pszName</i> and <i>pNameLength</i> are not <b>NULL</b>, the driver must check the input value of <i>pNameLength</i> to ensure that there's enough room in the allocated buffer, and then the length of the <i>pszName</i> string (including terminating <b>NULL</b> character) is passed out through the <i>pNameLength</i> parameter.</li>
</ul>

### -param Arg3

*pszUnits* [out, optional]

An optional pointer that the driver returns a <b>NULL</b>-terminated string to that contains the name of the units that the counter identifier measures.

Can be <b>NULL</b>, in which case the app doesn't need the units info. See more info in the explanation of the <i>pUnitsLength</i> parameter.

### -param *pUnitsLength [in, out, optional]

 An optional pointer to a variable that receives the size, in bytes, of the <b>NULL</b>-terminated string that the <i>pszUnits</i> parameter specifies.

Here are limitations on the values of the <i>pUnitsLength</i> and  <i>pszUnits</i> parameters:

<ul>
<li><i>pUnitsLength</i> can be <b>NULL</b>, in which case the app doesn't need the unit name or unit name length.</li>
<li> If <i>pszUnits</i> is <b>NULL</b> and <i>pUnitsLength</i> is not <b>NULL</b>, the input value of <i>pUnitsLength</i> is ignored, and the length of the string (including terminating <b>NULL</b> character) must be returned through the <i>pUnitsLength</i> parameter. </li>
<li>If both <i>pszUnits</i> and <i>pUnitsLength</i> are not <b>NULL</b>, the driver must check the input value of <i>pUnitsLength</i> to ensure that there's enough room in the allocated buffer, and then the length of the <i>pszUnits</i> string (including terminating <b>NULL</b> character) is passed out through the <i>pUnitsLength</i> parameter.</li>
</ul>

### -param Arg4

*pszDescription* [out, optional]

An optional pointer that the driver returns a <b>NULL</b>-terminated string to that contains the description of what the counter identifier measures.

Can be <b>NULL</b>, in which case the app doesn't need the description info. See more info in the explanation of the <i>pDescriptionLength</i> parameter.

### -param *pDescriptionLength [in, out, optional]

 An optional pointer to a variable that receives the size, in bytes, of the <b>NULL</b>-terminated string that the <i>pszDescription</i> parameter specifies.

Here are limitations on the values of the <i>pDescriptionLength</i> and  <i>pszDescription</i> parameters:

<ul>
<li><i>pDescriptionLength</i> can be <b>NULL</b>, in which case the app doesn't need the unit name or unit name length.</li>
<li> If <i>pszDescription</i> is <b>NULL</b> and <i>pDescriptionLength</i> is not <b>NULL</b>, the input value of <i>pDescriptionLength</i> is ignored, and the length of the string (including terminating <b>NULL</b> character) must be returned through the <i>pDescriptionLength</i> parameter. </li>
<li>If both <i>pszDescription</i> and <i>pDescriptionLength</i> are not <b>NULL</b>, the driver must check the input value of <i>pDescriptionLength</i> to ensure that there's enough room in the allocated buffer, and then the length of the <i>pszDescription</i> string (including terminating <b>NULL</b> character) is passed out through the <i>pDescriptionLength</i> parameter.</li>
</ul>



## -returns



If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code, including the following:

|Return code|Description|
|--- |--- |
|E_INVALIDARG|An out-of-range device-dependent counter is requested, or a string length is not large enough for a buffer to contain the entire string. <br/>Even though all strings used in this function are based on Unicode, they are always in the English locale and are not localized to other locales.|


## -remarks



This function should behave similarly to the <a href="https://msdn.microsoft.com/592a5146-a2fe-41d1-854b-df27a97bd513">CheckCounter</a> function that supports Microsoft Direct3D 10 and later.

Counters are typically used by tools that capture a frame and play it back multiple times. The pass that records accurate timing info is separate from other  passes. In later passes, a different set of counters is used each time.
The priority should be to obtain an accurate correlation of counter results to draw calls, and the overhead incurred during playback can be sacrificed. The driver must insert flush calls or wait-for-idle calls to ensure an accurate correlation.

Typically an app can simultaneously monitor only a small number of possible native counters, which might number in the hundreds. Additionally, the driver must indicate the number of active counters used by monitoring each supported counter ID from the <a href="https://msdn.microsoft.com/f80224c6-9046-4471-b6c6-eb14f02fc51f">D3DDDIQUERYTYPE</a> enumeration (both well-known counter IDs and device-specific counter IDs). For example, the driver can indicate that monitoring a <i>FillRateUtilized</i> variable requires 3 of the maximum 4 simultaneously active counters (indicated by the <i>pActiveCounters</i> parameter). The app can therefore also monitor another counter ID, as long as that counter ID requires one or fewer active counters.

If a counter ID can always be monitored (and it doesn't interfere with monitoring any other counter IDs), the number of simultaneous active counters required by the counter ID can be zero.




## -see-also




<a href="https://msdn.microsoft.com/592a5146-a2fe-41d1-854b-df27a97bd513">CheckCounter</a>



<a href="https://msdn.microsoft.com/f80224c6-9046-4471-b6c6-eb14f02fc51f">D3DDDIQUERYTYPE</a>
 

 

