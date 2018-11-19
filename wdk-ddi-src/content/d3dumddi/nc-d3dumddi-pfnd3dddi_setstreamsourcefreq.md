---
UID: NC:d3dumddi.PFND3DDDI_SETSTREAMSOURCEFREQ
title: PFND3DDDI_SETSTREAMSOURCEFREQ
author: windows-driver-content
description: The SetStreamSourceFreq function sets the frequency divisor of a stream source that is bound to a vertex buffer.
old-location: display\setstreamsourcefreq.htm
tech.root: display
ms.assetid: 92cb270c-1548-4239-81cd-5b3483769fc8
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETSTREAMSOURCEFREQ, PFND3DDDI_SETSTREAMSOURCEFREQ callback, SetStreamSourceFreq, SetStreamSourceFreq callback function [Display Devices], UserModeDisplayDriver_Functions_4cb72b36-4cea-424f-b7a3-149435170f24.xml, d3dumddi/SetStreamSourceFreq, display.setstreamsourcefreq
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
-	SetStreamSourceFreq
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETSTREAMSOURCEFREQ callback function


## -description


The <i>SetStreamSourceFreq</i> function sets the frequency divisor of a stream source that is bound to a vertex buffer.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543356">D3DDDIARG_SETSTREAMSOURCEFREQ</a> structure that specifies how the frequency divisor for the stream source is set.


## -returns



<i>SetStreamSourceFreq</i> returns S_OK or an appropriate error result if the frequency divisor for the portion of the vertex stream source is not successfully set.




## -remarks



A user-mode display driver for a device that supports vertex shader version 3.0 and later must implement vertex stream frequency division. For version 2.0 and earlier models of vertex shader (including fixed function), the vertex shader is called once for each vertex. For each call, the input vertex registers are initialized with unique vertex elements from the vertex streams. However, if the driver uses vertex stream frequency division, the vertex shader (3.0 and later) can be called to initialize applicable input registers at a less frequent rate. 

After the stream's frequency divisor is set--for example, to 2--the driver must fetch data from the stream and pass this data into applicable input vertex registers every 2 vertices. This divisor affects each element in the stream. 

The driver uses the frequency divisor to compute the vertex offset into the vertex buffer according to the following formula: 

```cpp
VertexOffset = ((VertexIndex / Divider) * StreamStride) + StreamOffset
```

For each vertex stream that is used, if the driver receives a start-vertex value during a call to the driver's <a href="https://msdn.microsoft.com/1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9">DrawPrimitive</a> function, the driver also divides this start-vertex value by the frequency divisor and factors the result in the formula. This start-vertex value is provided in the <b>VStart</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543057">D3DDDIARG_DRAWPRIMITIVE</a> structure. The following formula includes the start-vertex value: 

```cpp
VertexOffset = (StartVertex / Divider) + 
       ((VertexIndex / Divider) * StreamStride) + StreamOffset 
```

Note that the preceding formulas use integer division. 

The driver ignores the setting of a stream's frequency divisor either for indexed primitives or if the driver supports only a vertex shader model that is earlier than version 3.0 (including fixed function). 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543057">D3DDDIARG_DRAWPRIMITIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543356">D3DDDIARG_SETSTREAMSOURCEFREQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9">DrawPrimitive</a>
 

 

