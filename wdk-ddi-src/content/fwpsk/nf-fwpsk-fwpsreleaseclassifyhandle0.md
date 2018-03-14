---
UID: NF:fwpsk.FwpsReleaseClassifyHandle0
title: FwpsReleaseClassifyHandle0 function
author: windows-driver-content
description: A callout driver calls FwpsReleaseClassifyHandle0 to release a classification handle that was previously acquired through a call to FwpsAcquireClassifyHandle0.Note  FwpsReleaseClassifyHandle0 is a specific version of FwpsReleaseClassifyHandle.
old-location: netvista\fwpsreleaseclassifyhandle0.htm
old-project: netvista
ms.assetid: d61f9e04-e308-4844-9d46-d15faee04e75
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpsReleaseClassifyHandle0, FwpsReleaseClassifyHandle0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsReleaseClassifyHandle0, netvista.fwpsreleaseclassifyhandle0, wfp_ref_2_funct_3_fwps_R-Z_a488d8fc-0c0f-4580-a934-7dba9e2f98b9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 7.
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
-	FwpsReleaseClassifyHandle0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsReleaseClassifyHandle0 function


## -description


A callout driver calls 
  <b>FwpsReleaseClassifyHandle0</b> to release a classification handle that was previously acquired through a
  call to 
  <a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">
  FwpsAcquireClassifyHandle0</a>.
<div class="alert"><b>Note</b>  <b>FwpsReleaseClassifyHandle0</b> is a specific version of <b>FwpsReleaseClassifyHandle</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
void NTAPI FwpsReleaseClassifyHandle0(
  _In_ UINT64 classifyHandle
);
````


## -parameters




### -param classifyHandle [in]

The classification handle that identifies the callout driver's processing at the current layer.
     This handle is obtained by calling 
     <a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">
     FwpsAcquireClassifyHandle0</a>.


## -returns



None




## -remarks



Any time 
    <a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">FwpsAcquireClassifyHandle0</a> is
    called, a corresponding call to 
    <b>FwpsReleaseClassifyHandle0</b> must be made to free the system resources associated with the
    classification handle.




## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpspendclassify0.md">FwpsPendClassify0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>



<a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">FwpsAcquireClassifyHandle0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a>



<a href="..\fwpsk\nf-fwpsk-fwpscompleteclassify0.md">FwpsCompleteClassify0</a>



 

 


