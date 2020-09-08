---
UID: NF:fwpsk.FwpsReleaseClassifyHandle0
title: FwpsReleaseClassifyHandle0 function (fwpsk.h)
description: A callout driver calls FwpsReleaseClassifyHandle0 to release a classification handle that was previously acquired through a call to FwpsAcquireClassifyHandle0.Note  FwpsReleaseClassifyHandle0 is a specific version of FwpsReleaseClassifyHandle.
old-location: netvista\fwpsreleaseclassifyhandle0.htm
tech.root: netvista
ms.assetid: d61f9e04-e308-4844-9d46-d15faee04e75
ms.date: 05/02/2018
keywords: ["FwpsReleaseClassifyHandle0 function"]
ms.keywords: FwpsReleaseClassifyHandle0, FwpsReleaseClassifyHandle0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsReleaseClassifyHandle0, netvista.fwpsreleaseclassifyhandle0, wfp_ref_2_funct_3_fwps_R-Z_a488d8fc-0c0f-4580-a934-7dba9e2f98b9.xml
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsReleaseClassifyHandle0
 - fwpsk/FwpsReleaseClassifyHandle0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsReleaseClassifyHandle0
---

# FwpsReleaseClassifyHandle0 function


## -description

A callout driver calls 
  <b>FwpsReleaseClassifyHandle0</b> to release a classification handle that was previously acquired through a
  call to 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0">
  FwpsAcquireClassifyHandle0</a>.
<div class="alert"><b>Note</b>  <b>FwpsReleaseClassifyHandle0</b> is a specific version of <b>FwpsReleaseClassifyHandle</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param classifyHandle 

[in]
The classification handle that identifies the callout driver's processing at the current layer.
     This handle is obtained by calling 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0">
     FwpsAcquireClassifyHandle0</a>.

## -remarks

Any time 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0">FwpsAcquireClassifyHandle0</a> is
    called, a corresponding call to 
    <b>FwpsReleaseClassifyHandle0</b> must be made to free the system resources associated with the
    classification handle.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0">FwpsAcquireClassifyHandle0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscompleteclassify0">FwpsCompleteClassify0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendclassify0">FwpsPendClassify0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>

