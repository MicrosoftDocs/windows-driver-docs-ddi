---
UID: NF:fwpsk.FwpsCompleteClassify0
title: FwpsCompleteClassify0 function
author: windows-driver-content
description: A callout driver calls FwpsCompleteClassify0 to asynchronously complete a pended classify request.
old-location: netvista\fwpscompleteclassify0.htm
old-project: netvista
ms.assetid: 995e86dc-fc26-4903-bc21-45475cb4e2bc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FwpsCompleteClassify0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCompleteClassify0, FwpsCompleteClassify0, netvista.fwpscompleteclassify0, wfp_ref_2_funct_3_fwps_C_32709694-e6b8-41b8-90ea-4c8ef187ab6f.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsCompleteClassify0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsCompleteClassify0 function


## -description


A callout driver calls 
  <b>FwpsCompleteClassify0</b> to asynchronously complete a pended classify request. The callout driver's 
  <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function must have previously
  called 
  <a href="..\fwpsk\nf-fwpsk-fwpspendclassify0.md">FwpsPendClassify0</a> to pend the classify
  request.
<div class="alert"><b>Note</b>  <b>FwpsCompleteClassify0</b> is a specific version of <b>FwpsCompleteClassify</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
void NTAPI FwpsCompleteClassify0(
  _In_           UINT64             classifyHandle,
  _In_           UINT32             flags,
  _In_opt_ const FWPS_CLASSIFY_OUT0 *classifyOut
);
````


## -parameters




#### - classifyHandle [in]

The classification handle that identifies the callout driver's processing at the current layer.
     This handle is obtained by calling 
     <mshelp:link keywords="netvista.fwpsacquireclassifyhandle0" tabindex="0"><b>
     FwpsAcquireClassifyHandle0</b></mshelp:link>.


#### - flags [in]


      This parameter is reserved for future use. Set to zero.
     


#### - classifyOut [in, optional]

A pointer to a deep copy of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure that was originally
     passed to the 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> call when the classification was pended. When classifying asynchronously, the members
     of this structure can be set the same way as they would be in the callout driver's 
     <i>classifyFn</i> function when classifying inline.
     

If this parameter is used, the classification is taken as the callout driver's final decision. If set
     to <b>NULL</b>, the indication will be reauthorized.


## -returns


None.



## -remarks


<b>FwpsCompleteClassify0</b> must be called after a callout driver has called 
    <a href="..\fwpsk\nf-fwpsk-fwpspendclassify0.md">FwpsPendClassify0</a> to remove the
    classification from its pended state.

After calling this function, 
    <a href="..\fwpsk\nf-fwpsk-fwpsreleaseclassifyhandle0.md">FwpsReleaseClassifyHandle0</a> must
    be called to free the system resources associated with the classification handle.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a>

<a href="..\fwpsk\nf-fwpsk-fwpspendclassify0.md">FwpsPendClassify0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsreleaseclassifyhandle0.md">FwpsReleaseClassifyHandle0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>

<a href="..\fwpsk\nf-fwpsk-fwpsacquireclassifyhandle0.md">FwpsAcquireClassifyHandle0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsCompleteClassify0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

