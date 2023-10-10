---
UID: NC:d3dumddi.PFND3DDDI_CHECKCOUNTER
title: PFND3DDDI_CHECKCOUNTER (d3dumddi.h)
description: Learn more about the PFND3DDDI_CHECKCOUNTER callback function.
old-location: display\pfncheckcounter.htm
tech.root: display
ms.date: 10/05/2023
keywords: ["PFND3DDDI_CHECKCOUNTER callback function"]
ms.keywords: PFND3DDDI_CHECKCOUNTER, PFND3DDDI_CHECKCOUNTER callback, d3dumddi/pfnCheckCounter, display.pfncheckcounter, pfnCheckCounter, pfnCheckCounter callback function [Display Devices]
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_CHECKCOUNTER
 - d3dumddi/PFND3DDDI_CHECKCOUNTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dumddi.h
api_name:
 - PFND3DDDI_CHECKCOUNTER
---

# PFND3DDDI_CHECKCOUNTER callback function

## -description

**PFND3DDDI_CHECKCOUNTER** is called by the Direct3D runtime to retrieve info that describes a counter. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.

## -parameters

### -param hDevice

[in] A handle to the display device (graphics context).

### -param unnamedParam2

[in] **Counter** is a value of type [**D3DDDIQUERYTYPE**](ns-d3dumddi-_d3dddiarg_createquery.md) that identifies the counter identifier that info is retrieved for.

### -param unnamedParam3

[out] **pType** is a pointer to a variable that receives a [**D3DDDI_COUNTER_TYPE**](ne-d3dumddi-d3dddi_counter_type.md) enumeration value that identifies the data type that the counter outputs.

### -param unnamedParam4

*pActiveCounters* [out] **pActiveCounters** is a pointer to a variable that receives the number of simultaneously active counters that are allocated for the creation of the counter identifier that the **Counter** parameter identifies.

### -param unnamedParam5

[out, optional] **pszName** is an optional pointer that the driver returns a NULL-terminated string to that contains the name of the counter identifier.

Can be NULL, in which case the app doesn't need the name.

### -param pNameLength

[in, out, optional] An optional pointer to a variable that receives the size, in bytes, of the NULL-terminated string that the **pszName** parameter specifies.

Here are limitations on the values of the **pNameLength** and  **pszName** parameters:

* **pNameLength** can be NULL, in which case the app doesn't need the name or name length.
* If **pszName** is NULL and **pNameLength** is not NULL, the input value of **pNameLength** is ignored, and the length of the string (including terminating NULL character) must be returned through the **pNameLength** parameter.
* If both **pszName** and **pNameLength** are not NULL, the driver must check the input value of **pNameLength** to ensure that there's enough room in the allocated buffer, and then the length of the **pszName** string (including terminating NULL character) is passed out through the **pNameLength** parameter.

### -param unnamedParam7

[out, optional] **pszUnits** is an optional pointer that the driver returns a NULL-terminated string to that contains the name of the units that the counter identifier measures.

Can be NULL, in which case the app doesn't need the units info. See more info in the explanation of the **pUnitsLength** parameter.

### -param pUnitsLength

[in, out, optional] **pUnitsLength** is an optional pointer to a variable that receives the size, in bytes, of the NULL-terminated string that the **pszUnits** parameter specifies.

Here are limitations on the values of the **pUnitsLength** and  **pszUnits** parameters:

* **pUnitsLength** can be NULL, in which case the app doesn't need the unit name or unit name length.
* If **pszUnits** is NULL and **pUnitsLength** is not NULL, the input value of **pUnitsLength** is ignored, and the length of the string (including terminating NULL character) must be returned through the **pUnitsLength** parameter.
* If both **pszUnits** and **pUnitsLength** are not NULL, the driver must check the input value of **pUnitsLength** to ensure that there's enough room in the allocated buffer, and then the length of the **pszUnits** string (including terminating NULL character) is passed out through the **pUnitsLength** parameter.

### -param unnamedParam9

[out, optional] **pszDescription** is an optional pointer that the driver returns a NULL-terminated string to that contains the description of what the counter identifier measures.

Can be NULL, in which case the app doesn't need the description info. See more info in the explanation of the **pDescriptionLength** parameter.

### -param pDescriptionLength

[in, out, optional] **pDescriptionLength** is an optional pointer to a variable that receives the size, in bytes, of the NULL-terminated string that the **pszDescription** parameter specifies.

Here are limitations on the values of the **pDescriptionLength** and  **pszDescription** parameters:

* **pDescriptionLength** can be NULL, in which case the app doesn't need the unit name or unit name length.
* If **pszDescription** is NULL and **pDescriptionLength** is not NULL, the input value of **pDescriptionLength** is ignored, and the length of the string (including terminating NULL character) must be returned through the **pDescriptionLength** parameter.
* If both **pszDescription** and **pDescriptionLength** are not NULL, the driver must check the input value of **pDescriptionLength** to ensure that there's enough room in the allocated buffer, and then the length of the **pszDescription** string (including terminating NULL character) is passed out through the **pDescriptionLength** parameter.

## -returns

If this routine succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code, including the following:

|Return code|Description|
|--- |--- |
|E_INVALIDARG|An out-of-range device-dependent counter is requested, or a string length is not large enough for a buffer to contain the entire string. Even though all strings used in this function are based on Unicode, they are always in the English locale and are not localized to other locales.|

## -remarks

This function should behave similarly to the [**CheckCounter**](../d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkcounter.md) function that supports Microsoft Direct3D 10 and later.

Counters are typically used by tools that capture a frame and play it back multiple times. The pass that records accurate timing info is separate from other  passes. In later passes, a different set of counters is used each time.
The priority should be to obtain an accurate correlation of counter results to draw calls, and the overhead incurred during playback can be sacrificed. The driver must insert flush calls or wait-for-idle calls to ensure an accurate correlation.

Typically an app can simultaneously monitor only a small number of possible native counters, which might number in the hundreds. Additionally, the driver must indicate the number of active counters used by monitoring each supported counter ID from the [**D3DDDIQUERYTYPE**](ns-d3dumddi-_d3dddiarg_createquery.md) enumeration (both well-known counter IDs and device-specific counter IDs). For example, the driver can indicate that monitoring a **FillRateUtilized** variable requires 3 of the maximum 4 simultaneously active counters (indicated by the **pActiveCounters** parameter). The app can therefore also monitor another counter ID, as long as that counter ID requires one or fewer active counters.

If a counter ID can always be monitored (and it doesn't interfere with monitoring any other counter IDs), the number of simultaneous active counters required by the counter ID can be zero.

## -see-also

[**CheckCounter**](../d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_checkcounter.md)

[**D3DDDIQUERYTYPE**](ns-d3dumddi-_d3dddiarg_createquery.md)
