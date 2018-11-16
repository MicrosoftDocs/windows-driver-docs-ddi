---
UID: NC:d3dumddi.PFND3DDDI_GETCAPS
title: PFND3DDDI_GETCAPS
author: windows-driver-content
description: The GetCaps function queries for capabilities of the graphics adapter.
old-location: display\getcaps.htm
tech.root: display
ms.assetid: cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65
ms.date: 05/10/2018
ms.keywords: GetCaps, GetCaps callback function [Display Devices], PFND3DDDI_GETCAPS, PFND3DDDI_GETCAPS callback, UserModeDisplayDriver_Functions_2848e873-69ef-4b77-b8bc-8ae9f4abe2c9.xml, d3dumddi/GetCaps, display.getcaps
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	GetCaps
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_GETCAPS callback function


## -description


The <i>GetCaps</i> function queries for capabilities of the graphics adapter.


## -parameters




### -param hAdapter [in]

A handle that identifies the graphics adapter. 


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a> structure that describes the capabilities to retrieve.


## -returns



<i>GetCaps</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The capabilities were successfully retrieved.|
|E_OUTOFMEMORY|GetCaps could not allocate the required memory for it to complete.|
 




## -remarks



The data that is returned by the <i>GetCaps</i> function in the <b>pData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a> structure depends on the type of data that is requested (that is, the data depends on the <b>Type</b> member of <b>D3DDDIARG_GETCAPS</b> and sometimes on the <b>pInfo</b> member).

Here are examples of how to set up the <i>GetCaps</i> call depending on the value of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>.<i>Type</i>.

| **[D3DDDIARG_GETCAPS](https://msdn.microsoft.com/library/windows/hardware/ff543148) member** | **Member value—Example 1** | **Member value—Example 2** | 
|:--|:--|:--|
| **Type** | **D3DDDICAPS_DDRAW** | **D3DDDICAPS_GETFORMATCOUNT** | 
| **pInfo** | [in] `NULL` (no conditions are set) | [in] `NULL` (no conditions are set) | 
| **pData** | [out] `DDRAW_CAPS*`(unique pointer) | [out] UINT* (unique pointer) | 
| **DataSize** | `sizeof(DDRAW_CAPS)` | `sizeof(UINT)` | 
| **Notes** | Driver must fill in the [DDRAW_CAPS](https://msdn.microsoft.com/library/windows/hardware/ff550275)  structure pointed to by pDatawith Microsoft DirectDraw capabilities that it supports. | Driver must fill the buffer pointed to by pData with a UINT value that represents the number of [D3DDDIFORMAT](https://msdn.microsoft.com/library/windows/hardware/ff544312)  surface formats that the device supports. | 



See the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a> enumeration topic for explanations of other values for <b>D3DDDIARG_GETCAPS</b>.<b>Type</b> that are used for multiplane overlays.

<h3><a id="Simple_instancing"></a><a id="simple_instancing"></a><a id="SIMPLE_INSTANCING"></a>Simple instancing</h3>
If a Microsoft Direct3D Level 9 driver that supports Windows Display Driver Model (WDDM) 1.3 and later completes a call to <i>GetCaps</i> and returns <b>S_OK</b> but doesn't change the data in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a> structure, it indicates to the Direct3D runtime that the hardware and driver don't support simple instancing. For more info, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn465882">D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn465882">D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544355">D3DDDI_ADAPTERFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550275">DDRAW_CAPS</a>
 

 

