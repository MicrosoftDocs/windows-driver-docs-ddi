---
UID: NS:d3dkmddi._DXGKARG_QUERYADAPTERINFO
title: "_DXGKARG_QUERYADAPTERINFO"
author: windows-driver-content
description: The DXGKARG_QUERYADAPTERINFO structure contains parameters for a query.
old-location: display\dxgkarg_queryadapterinfo.htm
old-project: display
ms.assetid: 5992c846-93de-4f95-839a-81f14db709f7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKARG_QUERYADAPTERINFO, DXGKARG_QUERYADAPTERINFO structure [Display Devices], DmStructs_82a38a66-d65c-4b88-be6d-974590e9472a.xml, _DXGKARG_QUERYADAPTERINFO, d3dkmddi/DXGKARG_QUERYADAPTERINFO, display.dxgkarg_queryadapterinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_QUERYADAPTERINFO
product: Windows
targetos: Windows
req.typenames: DXGKARG_QUERYADAPTERINFO
---

# _DXGKARG_QUERYADAPTERINFO structure


## -description


The DXGKARG_QUERYADAPTERINFO structure contains parameters for a query.


## -struct-fields




### -field Type

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562010">DXGK_QUERYADAPTERINFOTYPE</a>-typed value that indicates the type of information to retrieve.


### -field pInputData

[in] A pointer to input information for the query. 

When <b>Type</b> specifies DXGKQAITYPE_UMDRIVERPRIVATE, <b>pInputData</b> points to a proprietary buffer that contains information about the query. When <b>Type</b> specifies DXGKQAITYPE_QUERYSEGMENT, <b>pInputData</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562015">DXGK_QUERYSEGMENTIN</a> structure. When <b>Type</b> specifies <b>DXGKQAITYPE_POWERCOMPONENTINFO</b>, <b>pInputData</b> points to an input buffer that contains the power component index.

An input buffer is not required when <b>Type</b> specifies the DXGKQAITYPE_DRIVERCAPS value.


### -field InputDataSize

[in] The size, in bytes, of the input data that <b>pInputData</b> points to.


### -field pOutputData

[out] A pointer to an output buffer that the display miniport driver fills with the required information.

<table>
<tr>
<th>Value of <b>Type</b></th>
<th>Contents of output buffer pointed to by <b>pOutputData</b></th>
</tr>
<tr>
<td><b>DXGKQAITYPE_UMDRIVERPRIVATE</b></td>
<td>Proprietary buffer</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_DRIVERCAPS</b></td>
<td>Populated <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_QUERYSEGMENT</b></td>
<td>Populated <a href="https://msdn.microsoft.com/library/windows/hardware/ff562018">DXGK_QUERYSEGMENTOUT</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_QUERYSEGMENT3</b></td>
<td>Populated <a href="https://msdn.microsoft.com/library/windows/hardware/hh464082">DXGK_QUERYSEGMENTOUT3</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_NUMPOWERCOMPONENTS</b></td>
<td>A UINT value that specifies the number of power components used by the display miniport driver</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_POWERCOMPONENTINFO</b></td>
<td>Populated <a href="https://msdn.microsoft.com/library/windows/hardware/hh464073">DXGK_POWER_RUNTIME_COMPONENT</a> structure that provides information about the <i>n</i>th power component, where <i>n</i> is the component index specified by  <b>pInputData</b> in a call to the <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function</td>
</tr>
</table>
 


### -field OutputDataSize

[in] The size, in bytes, of the output data that <b>pOutputData</b> points to.


### -field Flags

 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn268634">DXGK_POWER_P_COMPONENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464073">DXGK_POWER_RUNTIME_COMPONENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562010">DXGK_QUERYADAPTERINFOTYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562015">DXGK_QUERYSEGMENTIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562018">DXGK_QUERYSEGMENTOUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464082">DXGK_QUERYSEGMENTOUT3</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>
 

 

