---
UID: NF:fwpsk.FwpsApplyModifiedLayerData0
title: FwpsApplyModifiedLayerData0 function
author: windows-driver-content
description: The FwpsApplyModifiedLayerData0 function applies changes to layer-specific data made after a call to FwpsAcquireWritableLayerDataPointer0.Note  FwpsApplyModifiedLayerData0 is a specific version of FwpsApplyModifiedLayerData.
old-location: netvista\fwpsapplymodifiedlayerdata0.htm
tech.root: netvista
ms.assetid: d32c19b6-462e-48e3-b22b-02542dca9cc4
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: FWPS_CLASSIFY_FLAG_REAUTHORIZE_IF_MODIFIED_BY_OTHERS, FwpsApplyModifiedLayerData0, FwpsApplyModifiedLayerData0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsApplyModifiedLayerData0, netvista.fwpsapplymodifiedlayerdata0, wfp_ref_2_funct_3_fwps_A-B_a7adbeec-b234-451e-9da0-d5e5b7cefc90.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsApplyModifiedLayerData0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsApplyModifiedLayerData0 function


## -description


The 
  <b>FwpsApplyModifiedLayerData0</b> function applies changes to layer-specific data made after a call to 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff550087">FwpsAcquireWritableLayerDataPointer0</a>.
<div class="alert"><b>Note</b>  <b>FwpsApplyModifiedLayerData0</b> is a specific version of <b>FwpsApplyModifiedLayerData</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param classifyHandle [in]

The classification handle that identifies the callout driver's processing at the current layer.
     This handle is obtained by calling 
     <a href="https://msdn.microsoft.com/7348d937-6541-47a7-ae70-7d851d41bc1a">
     FwpsAcquireClassifyHandle0</a>.


### -param modifiedLayerData [in]

The data buffer obtained by calling 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff550087">FwpsAcquireWritableLayerDataPointer0</a> with members modified by the callout driver. Supported data
     types are defined as structures.


### -param flags [in]


      The options to use with this function call. This flag can have the following
      value.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FWPS_CLASSIFY_FLAG_REAUTHORIZE_IF_MODIFIED_BY_OTHERS"></a><a id="fwps_classify_flag_reauthorize_if_modified_by_others"></a><dl>
<dt><b>FWPS_CLASSIFY_FLAG_REAUTHORIZE_IF_MODIFIED_BY_OTHERS</b></dt>
</dl>
</td>
<td width="60%">
When set, this flag specifies that data at the layer of the pended classify action should be reauthorized if another callout driver modifies the data before the classification is completed. Use this flag only with pended classify and not inline classify, as its use with inline classify can lead to indeterminate results. If you do call this API for inline classify, set flags to zero.

</td>
</tr>
</table>
 


## -returns



None.




## -remarks



<b>FwpsApplyModifiedLayerData0</b> should be called once for every call made to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff550087">FwpsAcquireWritableLayerDataPointer0</a>, even if the callout driver didn't modify any data.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551221">FWPS_BIND_REQUEST0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551231">FWPS_CONNECT_REQUEST0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550085">FwpsAcquireClassifyHandle0</a>



<a href="https://msdn.microsoft.com/79816d01-bf27-49d0-b6f1-083b7e87cc4e">
   FwpsAcquireWritableLayerDataPointer0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551208">FwpsReleaseClassifyHandle0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>
 

 

