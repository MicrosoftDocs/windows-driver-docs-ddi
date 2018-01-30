---
UID: NS:d3dkmddi._DXGKARG_QUERYADAPTERINFO
title: "_DXGKARG_QUERYADAPTERINFO"
author: windows-driver-content
description: The DXGKARG_QUERYADAPTERINFO structure contains parameters for a query.
old-location: display\dxgkarg_queryadapterinfo.htm
old-project: display
ms.assetid: 5992c846-93de-4f95-839a-81f14db709f7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DmStructs_82a38a66-d65c-4b88-be6d-974590e9472a.xml, DXGKARG_QUERYADAPTERINFO structure [Display Devices], d3dkmddi/DXGKARG_QUERYADAPTERINFO, _DXGKARG_QUERYADAPTERINFO, display.dxgkarg_queryadapterinfo, DXGKARG_QUERYADAPTERINFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_QUERYADAPTERINFO
product: Windows
targetos: Windows
req.typenames: DXGKARG_QUERYADAPTERINFO
---

# _DXGKARG_QUERYADAPTERINFO structure


## -description


The DXGKARG_QUERYADAPTERINFO structure contains parameters for a query.


## -syntax


````
typedef struct _DXGKARG_QUERYADAPTERINFO {
  DXGK_QUERYADAPTERINFOTYPE Type;
  VOID                      *pInputData;
  UINT                      InputDataSize;
  VOID                      *pOutputData;
  UINT                      OutputDataSize;
} DXGKARG_QUERYADAPTERINFO;
````


## -struct-fields




### -field Type

[in] A <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_queryadapterinfotype.md">DXGK_QUERYADAPTERINFOTYPE</a>-typed value that indicates the type of information to retrieve.


### -field pInputData

[in] A pointer to input information for the query. 

When <b>Type</b> specifies DXGKQAITYPE_UMDRIVERPRIVATE, <b>pInputData</b> points to a proprietary buffer that contains information about the query. When <b>Type</b> specifies DXGKQAITYPE_QUERYSEGMENT, <b>pInputData</b> points to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentin.md">DXGK_QUERYSEGMENTIN</a> structure. When <b>Type</b> specifies <b>DXGKQAITYPE_POWERCOMPONENTINFO</b>, <b>pInputData</b> points to an input buffer that contains the power component index.

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
<td>Populated <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_QUERYSEGMENT</b></td>
<td>Populated <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout.md">DXGK_QUERYSEGMENTOUT</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_QUERYSEGMENT3</b></td>
<td>Populated <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout3.md">DXGK_QUERYSEGMENTOUT3</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_NUMPOWERCOMPONENTS</b></td>
<td>A UINT value that specifies the number of power components used by the display miniport driver</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_POWERCOMPONENTINFO</b></td>
<td>Populated <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_power_runtime_component.md">DXGK_POWER_RUNTIME_COMPONENT</a> structure that provides information about the <i>n</i>th power component, where <i>n</i> is the component index specified by  <b>pInputData</b> in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function</td>
</tr>
</table> 


### -field OutputDataSize

[in] The size, in bytes, of the output data that <b>pOutputData</b> points to.


### -field Flags

 



## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout.md">DXGK_QUERYSEGMENTOUT</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentin.md">DXGK_QUERYSEGMENTIN</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_power_runtime_component.md">DXGK_POWER_RUNTIME_COMPONENT</a>

<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_queryadapterinfotype.md">DXGK_QUERYADAPTERINFOTYPE</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout3.md">DXGK_QUERYSEGMENTOUT3</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn268634">DXGK_POWER_P_COMPONENT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_QUERYADAPTERINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

